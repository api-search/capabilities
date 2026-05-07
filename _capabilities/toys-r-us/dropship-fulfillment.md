---
categories: []
consumed_apis: []
description: Unified dropship fulfillment workflow for Toys R Us supplier integrations. Combines order retrieval, acknowledgement, shipment notification, invoice submission, and product catalog synchronization for end-to-end dropship vendor operations.
layout: capability
name: Toys R Us Dropship Fulfillment
operations:
- description: Retrieve purchase orders awaiting fulfillment
  method: GET
  name: get-orders
  path: /v1/orders
- description: Retrieve a single purchase order
  method: GET
  name: get-order
  path: /v1/orders/{key}
- description: Submit an order acknowledgement
  method: POST
  name: create-acknowledgement
  path: /v1/acknowledgements
- description: Retrieve shipment notifications
  method: GET
  name: get-shipments
  path: /v1/shipments
- description: Submit a shipment notification
  method: POST
  name: create-shipment
  path: /v1/shipments
- description: Retrieve invoices
  method: GET
  name: get-invoices
  path: /v1/invoices
- description: Submit an invoice for fulfilled order
  method: POST
  name: create-invoice
  path: /v1/invoices
- description: Retrieve product catalog items
  method: GET
  name: get-products
  path: /v1/products
- description: Create or update a product catalog item
  method: POST
  name: create-product
  path: /v1/products
personas: []
provider_name: Toys R Us
provider_slug: toys-r-us
search_terms:
- create shipment
- get orders
- retrieve open purchase orders for fulfillment
- create product
- retail
- get invoices
- retrieve toys r us product catalog items
- fulfillment
- supply chain
- order management
- retrieve shipment notifications
- dropship
- submit order acknowledgements
- retrieve a specific order by key
- retrieve a specific toys r us purchase order by key
- submit an invoice for fulfilled toys r us order items
- create invoice
- sync product
- submit a shipment notification
- e-commerce
- submit an order acknowledgement
- create or update a product catalog item
- retrieve toys r us shipment notifications
- submit an invoice for fulfilled order
- retrieve invoices
- get shipments
- create acknowledgement
- retrieve toys r us invoices
- create or update a product in the toys r us catalog
- submit invoices for fulfilled orders
- product catalog synchronization
- retrieve a single purchase order
- submit shipment notifications
- retrieve toys r us purchase orders pending fulfillment
- submit a shipment notification for a fulfilled toys r us order
- get products
- retrieve purchase orders awaiting fulfillment
- commerce
- retrieve product catalog items
- get order
- submit an order acknowledgement for a toys r us purchase order
slug: dropship-fulfillment
source_filename: dropship-fulfillment.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Toys R Us Dropship Fulfillment\n  description: Unified dropship fulfillment workflow for Toys R Us supplier integrations. Combines order retrieval, acknowledgement,\n    shipment notification, invoice submission, and product catalog synchronization for end-to-end dropship vendor operations.\n  tags:\n  - Commerce\n  - Dropship\n  - E-Commerce\n  - Fulfillment\n  - Order Management\n  - Retail\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TOYS_R_US_API_KEY: TOYS_R_US_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: toys-r-us-commerce\n    baseUri: https://commerceapi.io\n    description: LogicBroker Commerce API for Toys R Us supplier integrations\n    authentication:\n      type: apikey\n      key: subscription-key\n      value: '{{TOYS_R_US_API_KEY}}'\n      placement: header\n    resources:\n    - name: orders\n      path: /api/v2/orders\n      description: Purchase order\
  \ management\n      operations:\n      - name: get-orders\n        method: GET\n        description: Retrieve a list of purchase orders\n        inputParameters:\n        - name: status\n          in: query\n          type: integer\n          required: false\n          description: Filter by status code\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Records per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-order\n        method: GET\n        description: Retrieve a single purchase order by key\n        inputParameters:\n        - name: key\n          in: path\n          type: integer\n          required: true\n          description: Unique document key\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: acknowledgements\n      path: /api/v2/acknowledgements\n      description: Order acknowledgement workflows\n      operations:\n      - name: get-acknowledgements\n        method: GET\n        description: Retrieve a list of order acknowledgements\n        inputParameters:\n        - name: status\n          in: query\n          type: integer\n          required: false\n          description: Filter by status code\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-acknowledgement\n        method: POST\n        description: Submit an order acknowledgement\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n        body:\n          type: json\n          data:\n            PartnerPO: '{{tools.partner_po}}'\n            Lines: '{{tools.lines}}'\n    - name: shipments\n      path: /api/v2/shipments\n      description: Shipment notification management\n      operations:\n      - name: get-shipments\n        method: GET\n        description: Retrieve a list of shipment notifications\n        inputParameters:\n        - name: status\n          in: query\n          type: integer\n          required: false\n          description: Filter by status code\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-shipment\n        method: POST\n        description: Submit a shipment notification\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            PartnerPO: '{{tools.partner_po}}'\n            ShipDate: '{{tools.ship_date}}'\n            Carrier: '{{tools.carrier}}'\n            Packages: '{{tools.packages}}'\n    - name: invoices\n      path: /api/v2/invoices\n      description: Invoice processing\n      operations:\n      - name: get-invoices\n        method: GET\n        description: Retrieve a list of invoices\n        inputParameters:\n        - name: status\n          in: query\n          type: integer\n          required: false\n          description: Filter by status code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-invoice\n        method: POST\n        description: Submit an invoice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n \
  \         value: $.\n        body:\n          type: json\n          data:\n            PartnerPO: '{{tools.partner_po}}'\n            InvoiceNumber: '{{tools.invoice_number}}'\n            InvoiceDate: '{{tools.invoice_date}}'\n            Lines: '{{tools.lines}}'\n    - name: products\n      path: /api/v2/products\n      description: Product catalog synchronization\n      operations:\n      - name: get-products\n        method: GET\n        description: Retrieve a list of product catalog items\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-product\n        method: POST\n        description: Create or update a product catalog item\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n        body:\n          type: json\n          data:\n            SupplierSKU: '{{tools.supplier_sku}}'\n            Description: '{{tools.description}}'\n            UnitPrice: '{{tools.unit_price}}'\n            InStock: '{{tools.in_stock}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: dropship-fulfillment-api\n    description: Unified REST API for Toys R Us dropship fulfillment workflows.\n    resources:\n    - path: /v1/orders\n      name: orders\n      description: Retrieve open purchase orders for fulfillment\n      operations:\n      - method: GET\n        name: get-orders\n        description: Retrieve purchase orders awaiting fulfillment\n        call: toys-r-us-commerce.get-orders\n        with:\n          status: rest.status\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders/{key}\n      name: order\n      description: Retrieve a specific order by key\n      operations:\n\
  \      - method: GET\n        name: get-order\n        description: Retrieve a single purchase order\n        call: toys-r-us-commerce.get-order\n        with:\n          key: rest.key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/acknowledgements\n      name: acknowledgements\n      description: Submit order acknowledgements\n      operations:\n      - method: POST\n        name: create-acknowledgement\n        description: Submit an order acknowledgement\n        call: toys-r-us-commerce.create-acknowledgement\n        with:\n          partner_po: rest.PartnerPO\n          lines: rest.Lines\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/shipments\n      name: shipments\n      description: Submit shipment notifications\n      operations:\n      - method: GET\n        name: get-shipments\n        description: Retrieve shipment notifications\n        call: toys-r-us-commerce.get-shipments\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: POST\n        name: create-shipment\n        description: Submit a shipment notification\n        call: toys-r-us-commerce.create-shipment\n        with:\n          partner_po: rest.PartnerPO\n          ship_date: rest.ShipDate\n          carrier: rest.Carrier\n          packages: rest.Packages\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices\n      name: invoices\n      description: Submit invoices for fulfilled orders\n      operations:\n      - method: GET\n        name: get-invoices\n        description: Retrieve invoices\n        call: toys-r-us-commerce.get-invoices\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-invoice\n        description: Submit an invoice for fulfilled order\n        call: toys-r-us-commerce.create-invoice\n        with:\n          partner_po: rest.PartnerPO\n          invoice_number:\
  \ rest.InvoiceNumber\n          invoice_date: rest.InvoiceDate\n          lines: rest.Lines\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products\n      name: products\n      description: Product catalog synchronization\n      operations:\n      - method: GET\n        name: get-products\n        description: Retrieve product catalog items\n        call: toys-r-us-commerce.get-products\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-product\n        description: Create or update a product catalog item\n        call: toys-r-us-commerce.create-product\n        with:\n          supplier_sku: rest.SupplierSKU\n          description: rest.Description\n          unit_price: rest.UnitPrice\n          in_stock: rest.InStock\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: dropship-fulfillment-mcp\n    transport:\
  \ http\n    description: MCP server for AI-assisted Toys R Us dropship fulfillment operations.\n    tools:\n    - name: get-orders\n      description: Retrieve Toys R Us purchase orders pending fulfillment\n      hints:\n        readOnly: true\n        openWorld: false\n      call: toys-r-us-commerce.get-orders\n      with:\n        status: tools.status\n        page: tools.page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-order\n      description: Retrieve a specific Toys R Us purchase order by key\n      hints:\n        readOnly: true\n        openWorld: false\n      call: toys-r-us-commerce.get-order\n      with:\n        key: tools.key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-acknowledgement\n      description: Submit an order acknowledgement for a Toys R Us purchase order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: toys-r-us-commerce.create-acknowledgement\n\
  \      with:\n        partner_po: tools.partner_po\n        lines: tools.lines\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-shipments\n      description: Retrieve Toys R Us shipment notifications\n      hints:\n        readOnly: true\n        openWorld: false\n      call: toys-r-us-commerce.get-shipments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-shipment\n      description: Submit a shipment notification for a fulfilled Toys R Us order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: toys-r-us-commerce.create-shipment\n      with:\n        partner_po: tools.partner_po\n        ship_date: tools.ship_date\n        carrier: tools.carrier\n        packages: tools.packages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-invoices\n      description: Retrieve Toys R Us invoices\n      hints:\n        readOnly: true\n\
  \        openWorld: false\n      call: toys-r-us-commerce.get-invoices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-invoice\n      description: Submit an invoice for fulfilled Toys R Us order items\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: toys-r-us-commerce.create-invoice\n      with:\n        partner_po: tools.partner_po\n        invoice_number: tools.invoice_number\n        invoice_date: tools.invoice_date\n        lines: tools.lines\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-products\n      description: Retrieve Toys R Us product catalog items\n      hints:\n        readOnly: true\n        openWorld: false\n      call: toys-r-us-commerce.get-products\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sync-product\n      description: Create or update a product in the Toys R Us catalog\n      hints:\n     \
  \   readOnly: false\n        destructive: false\n        idempotent: true\n      call: toys-r-us-commerce.create-product\n      with:\n        supplier_sku: tools.supplier_sku\n        description: tools.description\n        unit_price: tools.unit_price\n        in_stock: tools.in_stock\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/toys-r-us/refs/heads/main/capabilities/dropship-fulfillment.yaml
tags:
- Commerce
- Dropship
- E-Commerce
- Fulfillment
- Order Management
- Retail
tools:
- description: Retrieve Toys R Us purchase orders pending fulfillment
  hints:
    openWorld: false
    readOnly: true
  name: get-orders
- description: Retrieve a specific Toys R Us purchase order by key
  hints:
    openWorld: false
    readOnly: true
  name: get-order
- description: Submit an order acknowledgement for a Toys R Us purchase order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-acknowledgement
- description: Retrieve Toys R Us shipment notifications
  hints:
    openWorld: false
    readOnly: true
  name: get-shipments
- description: Submit a shipment notification for a fulfilled Toys R Us order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-shipment
- description: Retrieve Toys R Us invoices
  hints:
    openWorld: false
    readOnly: true
  name: get-invoices
- description: Submit an invoice for fulfilled Toys R Us order items
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-invoice
- description: Retrieve Toys R Us product catalog items
  hints:
    openWorld: false
    readOnly: true
  name: get-products
- description: Create or update a product in the Toys R Us catalog
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: sync-product
---
