---
categories: []
consumed_apis: []
description: Unified workflow capability for commerce operations on the Rithum / Dsco platform. Combines supplier and retailer workflows for order management, catalog synchronization, inventory updates, shipment tracking, invoice processing, and event streaming. Designed for commerce operations teams managing dropship and private marketplace integrations.
layout: capability
name: Rithum Commerce Operations
operations:
- description: List supplier orders available for fulfillment
  method: GET
  name: list-orders
  path: /v1/orders
- description: Submit a consumer order to the Dsco platform
  method: POST
  name: create-order
  path: /v1/orders
- description: Get a specific order by ID
  method: GET
  name: get-order
  path: /v1/orders/{orderId}
- description: Acknowledge receipt of an order
  method: POST
  name: acknowledge-order
  path: /v1/orders/{orderId}/acknowledge
- description: Cancel an order item
  method: POST
  name: cancel-order
  path: /v1/orders/{orderId}/cancel
- description: Update supplier product catalog items
  method: POST
  name: update-catalog
  path: /v1/catalog
- description: Update supplier inventory quantities
  method: POST
  name: update-inventory
  path: /v1/inventory
- description: Create a shipment record for a fulfilled order
  method: POST
  name: create-shipment
  path: /v1/shipments
- description: Submit an invoice for a fulfilled order
  method: POST
  name: create-invoice
  path: /v1/invoices
- description: List all event streams
  method: GET
  name: list-streams
  path: /v1/streams
- description: Create a new event stream
  method: POST
  name: create-stream
  path: /v1/streams
- description: Retrieve events from a stream
  method: GET
  name: get-stream-events
  path: /v1/streams/{streamId}/events
personas: []
provider_name: Rithum
provider_slug: rithum
search_terms:
- create shipment
- cancel order item
- invoice processing
- acknowledge receipt of an order
- create order
- list orders available for supplier fulfillment
- inventory level management
- retail
- list all event streams
- stream event consumption
- get stream events
- update catalog
- supply chain
- ecommerce
- update supplier inventory quantities
- update inventory
- retrieve events from a stream starting at a checkpoint position
- retrieve events from a stream
- dropship
- list streams
- create a shipment record for a fulfilled order with tracking
- order cancellation
- create a shipment record for a fulfilled order
- submit an invoice for a fulfilled order
- order acknowledgment
- get a specific order by id
- update supplier inventory quantities for catalog items
- create stream
- create retailer order
- list orders
- rithum
- create invoice
- individual order detail
- cancel order
- marketplace
- acknowledge order
- cancel an order item
- cancel an order item (supplier or retailer)
- list all event stream definitions for real-time data consumption
- submit a consumer order to the dsco platform
- submit a consumer dropship or marketplace order
- submit an invoice for a fulfilled supplier order
- list supplier orders available for fulfillment
- product catalog synchronization
- shipment management
- create a new event stream
- order management for retailers and suppliers
- event stream management for real-time data
- update supplier product catalog with new or changed items
- update supplier product catalog items
- acknowledge receipt of a supplier order
- commerce
- get order
- create a new event stream for order, inventory, or catalog events
slug: commerce-operations
source_filename: commerce-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Rithum Commerce Operations\n  description: Unified workflow capability for commerce operations on the Rithum / Dsco platform. Combines supplier and retailer\n    workflows for order management, catalog synchronization, inventory updates, shipment tracking, invoice processing, and\n    event streaming. Designed for commerce operations teams managing dropship and private marketplace integrations.\n  tags:\n  - Commerce\n  - Dropship\n  - Marketplace\n  - Ecommerce\n  - Rithum\n  - Supply Chain\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    DSCO_CLIENT_ID: DSCO_CLIENT_ID\n    DSCO_CLIENT_SECRET: DSCO_CLIENT_SECRET\ncapability:\n  consumes:\n  - type: http\n    namespace: dsco\n    baseUri: https://api.dsco.io/api/v3\n    description: Dsco Platform API for dropship and marketplace commerce integration\n    authentication:\n      type: bearer\n      token: '{{DSCO_ACCESS_TOKEN}}'\n    resources:\n\
  \    - name: authentication\n      path: /oauth2/token\n      description: OAuth2 token management\n      operations:\n      - name: get-access-token\n        method: POST\n        description: Obtain OAuth2 bearer token using client credentials\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: supplier-catalog\n      path: /supplier/catalog-in\n      description: Supplier catalog management\n      operations:\n      - name: supplier-update-catalog\n        method: POST\n        description: Create or update supplier product catalog items\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            items: '{{tools.items}}'\n    - name: supplier-inventory\n      path: /supplier/inventory-in\n      description:\
  \ Supplier inventory management\n      operations:\n      - name: supplier-update-inventory\n        method: POST\n        description: Update supplier inventory quantities\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            items: '{{tools.items}}'\n    - name: supplier-shipments\n      path: /supplier/shipment-in\n      description: Supplier shipment creation\n      operations:\n      - name: supplier-create-shipment\n        method: POST\n        description: Create shipment records for fulfilled orders\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            shipments: '{{tools.shipments}}'\n    - name: supplier-orders\n      path: /supplier/order-out\n\
  \      description: Supplier order retrieval\n      operations:\n      - name: supplier-list-orders\n        method: GET\n        description: List orders for supplier fulfillment\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter orders by status\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of orders to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: supplier-order-detail\n      path: /supplier/order-out/{orderId}\n      description: Supplier order detail retrieval\n      operations:\n      - name: supplier-get-order\n        method: GET\n        description: Get a specific order by ID\n        inputParameters:\n        - name: orderId\n          in: path\n          type: string\n          required:\
  \ true\n          description: The unique order identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: supplier-invoices\n      path: /supplier/invoice-in\n      description: Supplier invoice processing\n      operations:\n      - name: supplier-create-invoice\n        method: POST\n        description: Submit invoices for fulfilled orders\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            invoices: '{{tools.invoices}}'\n    - name: supplier-cancellations\n      path: /supplier/cancel-in\n      description: Supplier order cancellation\n      operations:\n      - name: supplier-cancel-order-item\n        method: POST\n        description: Cancel an order item\n        inputParameters: []\n        outputRawFormat: json\n   \
  \     outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            cancellations: '{{tools.cancellations}}'\n    - name: supplier-acknowledge\n      path: /supplier/acknowledge-order-in\n      description: Supplier order acknowledgment\n      operations:\n      - name: supplier-acknowledge-order\n        method: POST\n        description: Acknowledge receipt of orders\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            orderIds: '{{tools.orderIds}}'\n    - name: retailer-orders\n      path: /retailer/order-in\n      description: Retailer order submission\n      operations:\n      - name: retailer-create-order\n        method: POST\n        description: Submit consumer orders to the Dsco platform\n        inputParameters: []\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            orders: '{{tools.orders}}'\n    - name: retailer-cancellations\n      path: /retailer/cancel-in\n      description: Retailer order cancellation\n      operations:\n      - name: retailer-request-cancel\n        method: POST\n        description: Request cancellation of an order item\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            cancellations: '{{tools.cancellations}}'\n    - name: streams\n      path: /streams\n      description: Event stream management\n      operations:\n      - name: create-stream\n        method: POST\n        description: Create a new event stream\n        inputParameters: []\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            objectType: '{{tools.objectType}}'\n            queryParams: '{{tools.queryParams}}'\n      - name: list-streams\n        method: GET\n        description: List all event stream definitions\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stream-events\n      path: /streams/{streamId}/events\n      description: Stream event retrieval\n      operations:\n      - name: get-stream-events\n        method: GET\n        description: Retrieve events from a stream starting at a checkpoint\n        inputParameters:\n        - name: streamId\n          in: path\n          type: string\n          required: true\n          description: The stream identifier\n        - name: position\n          in: query\n       \
  \   type: string\n          required: false\n          description: Checkpoint position to start reading from\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of events to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: rithum-commerce-api\n    description: Unified REST API for Rithum commerce operations including orders, catalog, inventory, and shipments.\n    resources:\n    - path: /v1/orders\n      name: orders\n      description: Order management for retailers and suppliers\n      operations:\n      - method: GET\n        name: list-orders\n        description: List supplier orders available for fulfillment\n        call: dsco.supplier-list-orders\n        with:\n          status: rest.status\n          limit: rest.limit\n        outputParameters:\n   \
  \     - type: object\n          mapping: $.\n      - method: POST\n        name: create-order\n        description: Submit a consumer order to the Dsco platform\n        call: dsco.retailer-create-order\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders/{orderId}\n      name: order-detail\n      description: Individual order detail\n      operations:\n      - method: GET\n        name: get-order\n        description: Get a specific order by ID\n        call: dsco.supplier-get-order\n        with:\n          orderId: rest.orderId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders/{orderId}/acknowledge\n      name: order-acknowledge\n      description: Order acknowledgment\n      operations:\n      - method: POST\n        name: acknowledge-order\n        description: Acknowledge receipt of an order\n        call: dsco.supplier-acknowledge-order\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/orders/{orderId}/cancel\n      name: order-cancel\n      description: Order cancellation\n      operations:\n      - method: POST\n        name: cancel-order\n        description: Cancel an order item\n        call: dsco.supplier-cancel-order-item\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/catalog\n      name: catalog\n      description: Product catalog synchronization\n      operations:\n      - method: POST\n        name: update-catalog\n        description: Update supplier product catalog items\n        call: dsco.supplier-update-catalog\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/inventory\n      name: inventory\n      description: Inventory level management\n      operations:\n      - method: POST\n        name: update-inventory\n        description: Update supplier inventory quantities\n        call: dsco.supplier-update-inventory\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/shipments\n      name: shipments\n      description: Shipment management\n      operations:\n      - method: POST\n        name: create-shipment\n        description: Create a shipment record for a fulfilled order\n        call: dsco.supplier-create-shipment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices\n      name: invoices\n      description: Invoice processing\n      operations:\n      - method: POST\n        name: create-invoice\n        description: Submit an invoice for a fulfilled order\n        call: dsco.supplier-create-invoice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/streams\n      name: streams\n      description: Event stream management for real-time data\n      operations:\n      - method: GET\n        name: list-streams\n        description: List all event streams\n        call: dsco.list-streams\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: POST\n        name: create-stream\n        description: Create a new event stream\n        call: dsco.create-stream\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/streams/{streamId}/events\n      name: stream-events\n      description: Stream event consumption\n      operations:\n      - method: GET\n        name: get-stream-events\n        description: Retrieve events from a stream\n        call: dsco.get-stream-events\n        with:\n          streamId: rest.streamId\n          position: rest.position\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: rithum-commerce-mcp\n    transport: http\n    description: MCP server for AI-assisted Rithum commerce operations.\n    tools:\n    - name: list-orders\n      description: List orders available for supplier fulfillment\n      hints:\n\
  \        readOnly: true\n        openWorld: false\n      call: dsco.supplier-list-orders\n      with:\n        status: tools.status\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-order\n      description: Get a specific order by ID\n      hints:\n        readOnly: true\n        openWorld: false\n      call: dsco.supplier-get-order\n      with:\n        orderId: tools.orderId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-retailer-order\n      description: Submit a consumer dropship or marketplace order\n      hints:\n        readOnly: false\n        destructive: false\n      call: dsco.retailer-create-order\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: acknowledge-order\n      description: Acknowledge receipt of a supplier order\n      hints:\n        readOnly: false\n        destructive: false\n      call: dsco.supplier-acknowledge-order\n     \
  \ outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-order-item\n      description: Cancel an order item (supplier or retailer)\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: dsco.supplier-cancel-order-item\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-catalog\n      description: Update supplier product catalog with new or changed items\n      hints:\n        readOnly: false\n        destructive: false\n      call: dsco.supplier-update-catalog\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-inventory\n      description: Update supplier inventory quantities for catalog items\n      hints:\n        readOnly: false\n        destructive: false\n      call: dsco.supplier-update-inventory\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-shipment\n      description: Create a shipment record\
  \ for a fulfilled order with tracking\n      hints:\n        readOnly: false\n        destructive: false\n      call: dsco.supplier-create-shipment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-invoice\n      description: Submit an invoice for a fulfilled supplier order\n      hints:\n        readOnly: false\n        destructive: false\n      call: dsco.supplier-create-invoice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-streams\n      description: List all event stream definitions for real-time data consumption\n      hints:\n        readOnly: true\n        openWorld: false\n      call: dsco.list-streams\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-stream\n      description: Create a new event stream for order, inventory, or catalog events\n      hints:\n        readOnly: false\n        destructive: false\n      call: dsco.create-stream\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-stream-events\n      description: Retrieve events from a stream starting at a checkpoint position\n      hints:\n        readOnly: true\n        openWorld: false\n      call: dsco.get-stream-events\n      with:\n        streamId: tools.streamId\n        position: tools.position\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/rithum/refs/heads/main/capabilities/commerce-operations.yaml
tags:
- Commerce
- Dropship
- Marketplace
- Ecommerce
- Rithum
- Supply Chain
tools:
- description: List orders available for supplier fulfillment
  hints:
    openWorld: false
    readOnly: true
  name: list-orders
- description: Get a specific order by ID
  hints:
    openWorld: false
    readOnly: true
  name: get-order
- description: Submit a consumer dropship or marketplace order
  hints:
    destructive: false
    readOnly: false
  name: create-retailer-order
- description: Acknowledge receipt of a supplier order
  hints:
    destructive: false
    readOnly: false
  name: acknowledge-order
- description: Cancel an order item (supplier or retailer)
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-order-item
- description: Update supplier product catalog with new or changed items
  hints:
    destructive: false
    readOnly: false
  name: update-catalog
- description: Update supplier inventory quantities for catalog items
  hints:
    destructive: false
    readOnly: false
  name: update-inventory
- description: Create a shipment record for a fulfilled order with tracking
  hints:
    destructive: false
    readOnly: false
  name: create-shipment
- description: Submit an invoice for a fulfilled supplier order
  hints:
    destructive: false
    readOnly: false
  name: create-invoice
- description: List all event stream definitions for real-time data consumption
  hints:
    openWorld: false
    readOnly: true
  name: list-streams
- description: Create a new event stream for order, inventory, or catalog events
  hints:
    destructive: false
    readOnly: false
  name: create-stream
- description: Retrieve events from a stream starting at a checkpoint position
  hints:
    openWorld: false
    readOnly: true
  name: get-stream-events
---
