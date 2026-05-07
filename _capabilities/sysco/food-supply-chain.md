---
categories: []
consumed_apis: []
description: Unified food supply chain capability for Sysco food distribution operations. Combines product catalog browsing, order management, delivery tracking, and pricing into a cohesive workflow for restaurants, food service operators, and supply chain integration partners.
layout: capability
name: Sysco Food Supply Chain
operations:
- description: Browse the Sysco food product catalog with category and keyword filtering.
  method: GET
  name: list-products
  path: /v1/products
- description: Get detailed product information including nutrition and availability.
  method: GET
  name: get-product
  path: /v1/products
- description: List food distribution orders with status filtering.
  method: GET
  name: list-orders
  path: /v1/orders
- description: Create a new food distribution order.
  method: POST
  name: create-order
  path: /v1/orders
- description: Get details for a specific order.
  method: GET
  name: get-order
  path: /v1/orders
- description: List scheduled and completed deliveries with tracking information.
  method: GET
  name: list-deliveries
  path: /v1/deliveries
- description: Get tracking details for a specific delivery.
  method: GET
  name: get-delivery
  path: /v1/deliveries
- description: Retrieve contract pricing for food products.
  method: GET
  name: list-pricing
  path: /v1/pricing
personas: []
provider_name: Sysco
provider_slug: sysco
search_terms:
- get tracking details and estimated arrival for a specific sysco delivery.
- create order
- list delivery schedules and tracking information for sysco orders.
- get product
- get details for a specific order.
- list food distribution orders with optional status and date filtering.
- list products
- browse the sysco food product catalog with category and keyword filtering.
- sysco
- order management
- supply chain
- list deliveries
- list food distribution orders with status filtering.
- get the status and details of a specific sysco order.
- fortune 100
- get detailed product information including nutrition and availability.
- food distribution
- get detailed information about a sysco food product by product id.
- browse the sysco food product catalog by category, keyword, or brand.
- food service
- create a new food distribution order.
- food distribution orders.
- list orders
- get delivery
- wholesale
- delivery tracking and scheduling.
- list pricing
- contract pricing.
- food product catalog.
- list scheduled and completed deliveries with tracking information.
- get tracking details for a specific delivery.
- retrieve contract pricing for sysco food products.
- retrieve contract pricing for food products.
- delivery tracking
- get order
- place a new sysco food distribution order with products and delivery date.
slug: food-supply-chain
source_filename: food-supply-chain.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Sysco Food Supply Chain\n  description: Unified food supply chain capability for Sysco food distribution operations. Combines product catalog browsing,\n    order management, delivery tracking, and pricing into a cohesive workflow for restaurants, food service operators, and\n    supply chain integration partners.\n  tags:\n  - Sysco\n  - Food Distribution\n  - Supply Chain\n  - Food Service\n  - Order Management\n  - Delivery Tracking\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SYSCO_API_TOKEN: SYSCO_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: sysco-food-distribution\n    baseUri: https://api.sysco.com\n    description: Sysco food distribution REST API.\n    authentication:\n      type: bearer\n      token: '{{SYSCO_API_TOKEN}}'\n    resources:\n    - name: products\n      path: /products\n      description: Sysco product catalog operations.\n      operations:\n  \
  \    - name: list-products\n        method: GET\n        description: Retrieves products from the Sysco catalog with filtering.\n        inputParameters:\n        - name: category\n          in: query\n          type: string\n          required: false\n        - name: keyword\n          in: query\n          type: string\n          required: false\n        - name: brand\n          in: query\n          type: string\n          required: false\n        - name: page\n          in: query\n          type: integer\n          required: false\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-product\n        method: GET\n        description: Retrieves detailed product information including nutrition and packaging.\n        inputParameters:\n        - name: productId\n          in: path\n          type: string\n\
  \          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders\n      path: /orders\n      description: Order management operations.\n      operations:\n      - name: list-orders\n        method: GET\n        description: Retrieves orders with status and delivery information.\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n        - name: dateFrom\n          in: query\n          type: string\n          required: false\n        - name: dateTo\n          in: query\n          type: string\n          required: false\n        - name: page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-order\n        method: POST\n        description: Creates\
  \ a new food distribution order.\n        inputParameters:\n        - name: deliveryDate\n          in: body\n          type: string\n          required: true\n        - name: specialInstructions\n          in: body\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            deliveryDate: '{{tools.deliveryDate}}'\n            specialInstructions: '{{tools.specialInstructions}}'\n      - name: get-order\n        method: GET\n        description: Retrieves details for a specific order.\n        inputParameters:\n        - name: orderId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cancel-order\n        method: DELETE\n        description: Cancels\
  \ a pending order.\n        inputParameters:\n        - name: orderId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deliveries\n      path: /deliveries\n      description: Delivery tracking operations.\n      operations:\n      - name: list-deliveries\n        method: GET\n        description: Retrieves scheduled and completed deliveries with tracking.\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n        - name: dateFrom\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-delivery\n        method: GET\n        description: Retrieves tracking details for a specific delivery.\n        inputParameters:\n\
  \        - name: deliveryId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pricing\n      path: /pricing\n      description: Contract pricing operations.\n      operations:\n      - name: list-pricing\n        method: GET\n        description: Retrieves contract pricing for products.\n        inputParameters:\n        - name: productId\n          in: query\n          type: string\n          required: false\n        - name: category\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sysco-supply-chain-api\n    description: Unified REST API for Sysco food distribution and supply chain operations.\n    resources:\n    - path:\
  \ /v1/products\n      name: products\n      description: Food product catalog.\n      operations:\n      - method: GET\n        name: list-products\n        description: Browse the Sysco food product catalog with category and keyword filtering.\n        call: sysco-food-distribution.list-products\n        with:\n          category: rest.category\n          keyword: rest.keyword\n          brand: rest.brand\n          page: rest.page\n          pageSize: rest.pageSize\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-product\n        description: Get detailed product information including nutrition and availability.\n        call: sysco-food-distribution.get-product\n        with:\n          productId: rest.productId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders\n      name: orders\n      description: Food distribution orders.\n      operations:\n      - method: GET\n    \
  \    name: list-orders\n        description: List food distribution orders with status filtering.\n        call: sysco-food-distribution.list-orders\n        with:\n          status: rest.status\n          dateFrom: rest.dateFrom\n          dateTo: rest.dateTo\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-order\n        description: Create a new food distribution order.\n        call: sysco-food-distribution.create-order\n        with:\n          deliveryDate: rest.deliveryDate\n          specialInstructions: rest.specialInstructions\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-order\n        description: Get details for a specific order.\n        call: sysco-food-distribution.get-order\n        with:\n          orderId: rest.orderId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/deliveries\n\
  \      name: deliveries\n      description: Delivery tracking and scheduling.\n      operations:\n      - method: GET\n        name: list-deliveries\n        description: List scheduled and completed deliveries with tracking information.\n        call: sysco-food-distribution.list-deliveries\n        with:\n          status: rest.status\n          dateFrom: rest.dateFrom\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-delivery\n        description: Get tracking details for a specific delivery.\n        call: sysco-food-distribution.get-delivery\n        with:\n          deliveryId: rest.deliveryId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pricing\n      name: pricing\n      description: Contract pricing.\n      operations:\n      - method: GET\n        name: list-pricing\n        description: Retrieve contract pricing for food products.\n        call: sysco-food-distribution.list-pricing\n\
  \        with:\n          productId: rest.productId\n          category: rest.category\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: sysco-supply-chain-mcp\n    transport: http\n    description: MCP server for AI-assisted food supply chain management using Sysco APIs.\n    tools:\n    - name: list-products\n      description: Browse the Sysco food product catalog by category, keyword, or brand.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: sysco-food-distribution.list-products\n      with:\n        category: tools.category\n        keyword: tools.keyword\n        brand: tools.brand\n        page: tools.page\n        pageSize: tools.pageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-product\n      description: Get detailed information about a Sysco food product by product ID.\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: sysco-food-distribution.get-product\n      with:\n        productId: tools.productId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-orders\n      description: List food distribution orders with optional status and date filtering.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: sysco-food-distribution.list-orders\n      with:\n        status: tools.status\n        dateFrom: tools.dateFrom\n        dateTo: tools.dateTo\n        page: tools.page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-order\n      description: Place a new Sysco food distribution order with products and delivery date.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: sysco-food-distribution.create-order\n      with:\n        deliveryDate: tools.deliveryDate\n\
  \        specialInstructions: tools.specialInstructions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-order\n      description: Get the status and details of a specific Sysco order.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: sysco-food-distribution.get-order\n      with:\n        orderId: tools.orderId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-deliveries\n      description: List delivery schedules and tracking information for Sysco orders.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: sysco-food-distribution.list-deliveries\n      with:\n        status: tools.status\n        dateFrom: tools.dateFrom\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-delivery\n      description: Get tracking details and estimated arrival for a specific Sysco delivery.\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: sysco-food-distribution.get-delivery\n      with:\n        deliveryId: tools.deliveryId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-pricing\n      description: Retrieve contract pricing for Sysco food products.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: sysco-food-distribution.list-pricing\n      with:\n        productId: tools.productId\n        category: tools.category\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sysco/refs/heads/main/capabilities/food-supply-chain.yaml
tags:
- Sysco
- Food Distribution
- Supply Chain
- Food Service
- Order Management
- Delivery Tracking
tools:
- description: Browse the Sysco food product catalog by category, keyword, or brand.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-products
- description: Get detailed information about a Sysco food product by product ID.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-product
- description: List food distribution orders with optional status and date filtering.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-orders
- description: Place a new Sysco food distribution order with products and delivery date.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-order
- description: Get the status and details of a specific Sysco order.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-order
- description: List delivery schedules and tracking information for Sysco orders.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-deliveries
- description: Get tracking details and estimated arrival for a specific Sysco delivery.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-delivery
- description: Retrieve contract pricing for Sysco food products.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-pricing
---
