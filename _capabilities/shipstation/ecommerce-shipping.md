---
categories: []
consumed_apis: []
description: Unified ecommerce shipping workflow combining order management, multi-carrier rate shopping, label generation, warehouse management, and store integration. Designed for ecommerce operations teams managing shipping across multiple selling channels.
layout: capability
name: ShipStation Ecommerce Shipping
operations:
- description: List orders with status and date filtering
  method: GET
  name: list-orders
  path: /v1/orders
- description: Import an order from a selling channel
  method: POST
  name: create-order
  path: /v1/orders
- description: List shipments with carrier and tracking info
  method: GET
  name: list-shipments
  path: /v1/shipments
- description: Purchase a carrier shipping label for an order
  method: POST
  name: create-label
  path: /v1/labels
- description: Get carrier rates for a package route
  method: POST
  name: get-rates
  path: /v1/rates
- description: List all available carriers
  method: GET
  name: list-carriers
  path: /v1/carriers
- description: List all warehouse locations
  method: GET
  name: list-warehouses
  path: /v1/warehouses
- description: Add a new warehouse location
  method: POST
  name: create-warehouse
  path: /v1/warehouses
- description: List all connected stores
  method: GET
  name: list-stores
  path: /v1/stores
- description: List customers
  method: GET
  name: list-customers
  path: /v1/customers
- description: List products with shipping settings
  method: GET
  name: list-products
  path: /v1/products
- description: List third-party fulfillments
  method: GET
  name: list-fulfillments
  path: /v1/fulfillments
personas: []
provider_name: ShipStation
provider_slug: shipstation
search_terms:
- get shipping rates
- logistics
- list shipments with carrier and tracking info
- manage product shipping configurations
- list third-party fulfillments
- list shipstation orders with filters for status, date range, and store
- void shipping label
- import a new order into shipstation from a selling channel
- create warehouse
- create label
- list shipments with carrier, tracking, and cost information
- list all warehouse locations
- track all shipments and their status
- list available services for a specific carrier
- list customer records and their shipping history
- list all connected selling channels (shopify, amazon, ebay, etc.)
- import an order from a selling channel
- compare carrier rates for shipments
- get carrier rates for a package route
- list stores
- list products with shipping settings
- list all carrier accounts connected to shipstation
- compare carrier rates for a shipment by postal code and package weight
- labels
- add a new warehouse location
- list fulfillments
- track third-party fulfillment orders
- void a shipping label that should not be used
- list all available carriers
- manage warehouse fulfillment locations
- list warehouses
- generate shipping labels from multiple carriers
- ecommerce
- shipping
- list carriers
- list all configured warehouse fulfillment locations
- manage selling channel connections
- create order
- view connected carrier accounts
- list orders
- list customers
- list carrier services
- add a new warehouse ship-from location
- get rates
- access customer shipping history
- list products
- warehousing
- list orders with status and date filtering
- create shipping label
- generate a shipping label for an order using a selected carrier and service
- order management
- list products with their default shipping configurations
- list shipments
- manage ecommerce orders from all channels
- list all connected stores
- purchase a carrier shipping label for an order
slug: ecommerce-shipping
source_filename: ecommerce-shipping.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: ShipStation Ecommerce Shipping\n  description: Unified ecommerce shipping workflow combining order management, multi-carrier rate shopping, label generation,\n    warehouse management, and store integration. Designed for ecommerce operations teams managing shipping across multiple\n    selling channels.\n  tags:\n  - Ecommerce\n  - Labels\n  - Logistics\n  - Order Management\n  - Shipping\n  - Warehousing\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SHIPSTATION_API_KEY: SHIPSTATION_API_KEY\n    SHIPSTATION_API_SECRET: SHIPSTATION_API_SECRET\ncapability:\n  consumes:\n  - type: http\n    namespace: shipstation\n    baseUri: https://ssapi.shipstation.com\n    description: ShipStation V1 shipping API\n    authentication:\n      type: basic\n      username: '{{SHIPSTATION_API_KEY}}'\n      password: '{{SHIPSTATION_API_SECRET}}'\n    resources:\n    - name: orders\n      path: /orders\n      description:\
  \ Manage ecommerce orders\n      operations:\n      - name: list-orders\n        method: GET\n        description: List orders with filtering\n        inputParameters:\n        - name: orderStatus\n          in: query\n          type: string\n          required: false\n          description: Filter by order status\n        - name: orderNumber\n          in: query\n          type: string\n          required: false\n          description: Filter by order number\n        - name: createDateStart\n          in: query\n          type: string\n          required: false\n          description: Filter by create date start\n        - name: createDateEnd\n          in: query\n          type: string\n          required: false\n          description: Filter by create date end\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n\
  \          description: Results per page (max 500)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-order\n        method: POST\n        description: Create a new order in ShipStation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            orderNumber: '{{tools.order_number}}'\n            orderDate: '{{tools.order_date}}'\n            orderStatus: '{{tools.order_status}}'\n            shipTo: '{{tools.ship_to}}'\n            items: '{{tools.items}}'\n    - name: shipments\n      path: /shipments\n      description: Manage shipments\n      operations:\n      - name: list-shipments\n        method: GET\n        description: List shipments with filtering\n        inputParameters:\n        - name: orderNumber\n          in: query\n          type: string\n\
  \          required: false\n          description: Filter by order number\n        - name: trackingNumber\n          in: query\n          type: string\n          required: false\n          description: Filter by tracking number\n        - name: carrierCode\n          in: query\n          type: string\n          required: false\n          description: Filter by carrier\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-label\n        method: POST\n        description: Create a shipping label for an order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            orderId: '{{tools.order_id}}'\n            carrierCode: '{{tools.carrier_code}}'\n\
  \            serviceCode: '{{tools.service_code}}'\n            packageCode: '{{tools.package_code}}'\n            shipDate: '{{tools.ship_date}}'\n            weight: '{{tools.weight}}'\n      - name: get-rates\n        method: POST\n        description: Get shipping rates for a shipment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            carrierCode: '{{tools.carrier_code}}'\n            fromPostalCode: '{{tools.from_postal_code}}'\n            toPostalCode: '{{tools.to_postal_code}}'\n            toCountry: '{{tools.to_country}}'\n            weight: '{{tools.weight}}'\n      - name: void-label\n        method: POST\n        description: Void a shipping label\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n    \
  \        shipmentId: '{{tools.shipment_id}}'\n    - name: carriers\n      path: /carriers\n      description: Manage carrier connections\n      operations:\n      - name: list-carriers\n        method: GET\n        description: List all connected carriers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-carrier-services\n        method: GET\n        description: List services for a carrier\n        inputParameters:\n        - name: carrierCode\n          in: query\n          type: string\n          required: true\n          description: Carrier code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customers\n      path: /customers\n      description: Manage customer records\n      operations:\n      - name: list-customers\n        method: GET\n        description: List customers\n        inputParameters:\n\
  \        - name: countryCode\n          in: query\n          type: string\n          required: false\n          description: Filter by country\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: products\n      path: /products\n      description: Manage product records\n      operations:\n      - name: list-products\n        method: GET\n        description: List products\n        inputParameters:\n        - name: sku\n          in: query\n          type: string\n          required: false\n          description: Filter by SKU\n        - name: name\n          in: query\n          type: string\n          required: false\n          description: Filter by product name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: warehouses\n      path: /warehouses\n      description: Manage warehouse locations\n      operations:\n      - name: list-warehouses\n        method: GET\n        description: List all warehouses\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-warehouse\n        method: POST\n        description: Add a new warehouse location\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            warehouseName: '{{tools.warehouse_name}}'\n            originAddress: '{{tools.origin_address}}'\n    - name: stores\n      path: /stores\n      description: Manage marketplace store connections\n      operations:\n      - name: list-stores\n        method: GET\n        description: List connected marketplace stores\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fulfillments\n      path: /fulfillments\n      description: Manage third-party fulfillments\n      operations:\n      - name: list-fulfillments\n        method: GET\n        description: List fulfillments\n        inputParameters:\n        - name: orderId\n          in: query\n          type: integer\n          required: false\n          description: Filter by order ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: shipstation-ecommerce-api\n    description: Unified REST API for ecommerce shipping operations across multiple channels.\n    resources:\n    - path: /v1/orders\n      name: orders\n      description: Manage ecommerce orders from all channels\n      operations:\n      - method: GET\n        name: list-orders\n        description:\
  \ List orders with status and date filtering\n        call: shipstation.list-orders\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-order\n        description: Import an order from a selling channel\n        call: shipstation.create-order\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/shipments\n      name: shipments\n      description: Track all shipments and their status\n      operations:\n      - method: GET\n        name: list-shipments\n        description: List shipments with carrier and tracking info\n        call: shipstation.list-shipments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/labels\n      name: labels\n      description: Generate shipping labels from multiple carriers\n      operations:\n      - method: POST\n        name: create-label\n        description: Purchase a carrier shipping label for an order\n    \
  \    call: shipstation.create-label\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/rates\n      name: rates\n      description: Compare carrier rates for shipments\n      operations:\n      - method: POST\n        name: get-rates\n        description: Get carrier rates for a package route\n        call: shipstation.get-rates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/carriers\n      name: carriers\n      description: View connected carrier accounts\n      operations:\n      - method: GET\n        name: list-carriers\n        description: List all available carriers\n        call: shipstation.list-carriers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/warehouses\n      name: warehouses\n      description: Manage warehouse fulfillment locations\n      operations:\n      - method: GET\n        name: list-warehouses\n        description: List all warehouse\
  \ locations\n        call: shipstation.list-warehouses\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-warehouse\n        description: Add a new warehouse location\n        call: shipstation.create-warehouse\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stores\n      name: stores\n      description: Manage selling channel connections\n      operations:\n      - method: GET\n        name: list-stores\n        description: List all connected stores\n        call: shipstation.list-stores\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/customers\n      name: customers\n      description: Access customer shipping history\n      operations:\n      - method: GET\n        name: list-customers\n        description: List customers\n        call: shipstation.list-customers\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/products\n      name: products\n      description: Manage product shipping configurations\n      operations:\n      - method: GET\n        name: list-products\n        description: List products with shipping settings\n        call: shipstation.list-products\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/fulfillments\n      name: fulfillments\n      description: Track third-party fulfillment orders\n      operations:\n      - method: GET\n        name: list-fulfillments\n        description: List third-party fulfillments\n        call: shipstation.list-fulfillments\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: shipstation-ecommerce-mcp\n    transport: http\n    description: MCP server for AI-assisted ecommerce order fulfillment and shipping operations.\n    tools:\n    - name: list-orders\n      description: List ShipStation orders with filters for\
  \ status, date range, and store\n      hints:\n        readOnly: true\n        openWorld: true\n      call: shipstation.list-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-order\n      description: Import a new order into ShipStation from a selling channel\n      hints:\n        readOnly: false\n      call: shipstation.create-order\n      with:\n        order_number: tools.order_number\n        order_date: tools.order_date\n        order_status: tools.order_status\n        ship_to: tools.ship_to\n        items: tools.items\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-shipping-rates\n      description: Compare carrier rates for a shipment by postal code and package weight\n      hints:\n        readOnly: true\n      call: shipstation.get-rates\n      with:\n        carrier_code: tools.carrier_code\n        from_postal_code: tools.from_postal_code\n        to_postal_code: tools.to_postal_code\n      \
  \  to_country: tools.to_country\n        weight: tools.weight\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-shipping-label\n      description: Generate a shipping label for an order using a selected carrier and service\n      hints:\n        readOnly: false\n      call: shipstation.create-label\n      with:\n        order_id: tools.order_id\n        carrier_code: tools.carrier_code\n        service_code: tools.service_code\n        package_code: tools.package_code\n        ship_date: tools.ship_date\n        weight: tools.weight\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: void-shipping-label\n      description: Void a shipping label that should not be used\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: shipstation.void-label\n      with:\n        shipment_id: tools.shipment_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    -\
  \ name: list-shipments\n      description: List shipments with carrier, tracking, and cost information\n      hints:\n        readOnly: true\n      call: shipstation.list-shipments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-carriers\n      description: List all carrier accounts connected to ShipStation\n      hints:\n        readOnly: true\n      call: shipstation.list-carriers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-carrier-services\n      description: List available services for a specific carrier\n      hints:\n        readOnly: true\n      call: shipstation.list-carrier-services\n      with:\n        carrierCode: tools.carrier_code\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-warehouses\n      description: List all configured warehouse fulfillment locations\n      hints:\n        readOnly: true\n      call: shipstation.list-warehouses\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: create-warehouse\n      description: Add a new warehouse ship-from location\n      hints:\n        readOnly: false\n      call: shipstation.create-warehouse\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-stores\n      description: List all connected selling channels (Shopify, Amazon, eBay, etc.)\n      hints:\n        readOnly: true\n      call: shipstation.list-stores\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-customers\n      description: List customer records and their shipping history\n      hints:\n        readOnly: true\n      call: shipstation.list-customers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-products\n      description: List products with their default shipping configurations\n      hints:\n        readOnly: true\n      call: shipstation.list-products\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/shipstation/refs/heads/main/capabilities/ecommerce-shipping.yaml
tags:
- Ecommerce
- Labels
- Logistics
- Order Management
- Shipping
- Warehousing
tools:
- description: List ShipStation orders with filters for status, date range, and store
  hints:
    openWorld: true
    readOnly: true
  name: list-orders
- description: Import a new order into ShipStation from a selling channel
  hints:
    readOnly: false
  name: create-order
- description: Compare carrier rates for a shipment by postal code and package weight
  hints:
    readOnly: true
  name: get-shipping-rates
- description: Generate a shipping label for an order using a selected carrier and service
  hints:
    readOnly: false
  name: create-shipping-label
- description: Void a shipping label that should not be used
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: void-shipping-label
- description: List shipments with carrier, tracking, and cost information
  hints:
    readOnly: true
  name: list-shipments
- description: List all carrier accounts connected to ShipStation
  hints:
    readOnly: true
  name: list-carriers
- description: List available services for a specific carrier
  hints:
    readOnly: true
  name: list-carrier-services
- description: List all configured warehouse fulfillment locations
  hints:
    readOnly: true
  name: list-warehouses
- description: Add a new warehouse ship-from location
  hints:
    readOnly: false
  name: create-warehouse
- description: List all connected selling channels (Shopify, Amazon, eBay, etc.)
  hints:
    readOnly: true
  name: list-stores
- description: List customer records and their shipping history
  hints:
    readOnly: true
  name: list-customers
- description: List products with their default shipping configurations
  hints:
    readOnly: true
  name: list-products
---
