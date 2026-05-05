---
api_specs:
- filename: toys-r-us-commerce-openapi.yml
  format: yaml
  label: toys-r-us-commerce
  slug: toys-r-us-commerce
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/toys-r-us/refs/heads/main/openapi/toys-r-us-commerce-openapi.yml
categories: []
consumed_apis:
- toys-r-us-commerce
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
- create product
- retrieve purchase orders awaiting fulfillment
- retrieve shipment notifications
- create or update a product in the toys r us catalog
- sync product
- e-commerce
- submit shipment notifications
- retrieve toys r us invoices
- retrieve product catalog items
- commerce
- submit a shipment notification for a fulfilled toys r us order
- get products
- submit an invoice for fulfilled order
- get order
- create invoice
- product catalog synchronization
- submit order acknowledgements
- submit invoices for fulfilled orders
- retrieve a specific order by key
- get orders
- create acknowledgement
- submit a shipment notification
- retrieve invoices
- supply chain
- retail
- retrieve open purchase orders for fulfillment
- get shipments
- retrieve a specific toys r us purchase order by key
- dropship
- get invoices
- retrieve toys r us purchase orders pending fulfillment
- submit an invoice for fulfilled toys r us order items
- retrieve toys r us shipment notifications
- submit an order acknowledgement
- order management
- fulfillment
- submit an order acknowledgement for a toys r us purchase order
- create shipment
- retrieve a single purchase order
- create or update a product catalog item
- retrieve toys r us product catalog items
slug: dropship-fulfillment
source_filename: dropship-fulfillment.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Toys R Us Dropship Fulfillment\"\n  description: \"Unified dropship fulfillment workflow for Toys R Us supplier integrations. Combines order retrieval, acknowledgement, shipment notification, invoice submission, and product catalog synchronization for end-to-end dropship vendor operations.\"\n  tags:\n    - Commerce\n    - Dropship\n    - E-Commerce\n    - Fulfillment\n    - Order Management\n    - Retail\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TOYS_R_US_API_KEY: TOYS_R_US_API_KEY\n\ncapability:\n  consumes:\n    - import: toys-r-us-commerce\n      location: ./shared/toys-r-us-commerce.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: dropship-fulfillment-api\n      description: \"Unified REST API for Toys R Us dropship fulfillment workflows.\"\n      resources:\n        - path: /v1/orders\n          name: orders\n          description: \"Retrieve\
  \ open purchase orders for fulfillment\"\n          operations:\n            - method: GET\n              name: get-orders\n              description: \"Retrieve purchase orders awaiting fulfillment\"\n              call: \"toys-r-us-commerce.get-orders\"\n              with:\n                status: \"rest.status\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/orders/{key}\n          name: order\n          description: \"Retrieve a specific order by key\"\n          operations:\n            - method: GET\n              name: get-order\n              description: \"Retrieve a single purchase order\"\n              call: \"toys-r-us-commerce.get-order\"\n              with:\n                key: \"rest.key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/acknowledgements\n          name: acknowledgements\n\
  \          description: \"Submit order acknowledgements\"\n          operations:\n            - method: POST\n              name: create-acknowledgement\n              description: \"Submit an order acknowledgement\"\n              call: \"toys-r-us-commerce.create-acknowledgement\"\n              with:\n                partner_po: \"rest.PartnerPO\"\n                lines: \"rest.Lines\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/shipments\n          name: shipments\n          description: \"Submit shipment notifications\"\n          operations:\n            - method: GET\n              name: get-shipments\n              description: \"Retrieve shipment notifications\"\n              call: \"toys-r-us-commerce.get-shipments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-shipment\n              description:\
  \ \"Submit a shipment notification\"\n              call: \"toys-r-us-commerce.create-shipment\"\n              with:\n                partner_po: \"rest.PartnerPO\"\n                ship_date: \"rest.ShipDate\"\n                carrier: \"rest.Carrier\"\n                packages: \"rest.Packages\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/invoices\n          name: invoices\n          description: \"Submit invoices for fulfilled orders\"\n          operations:\n            - method: GET\n              name: get-invoices\n              description: \"Retrieve invoices\"\n              call: \"toys-r-us-commerce.get-invoices\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-invoice\n              description: \"Submit an invoice for fulfilled order\"\n              call: \"toys-r-us-commerce.create-invoice\"\
  \n              with:\n                partner_po: \"rest.PartnerPO\"\n                invoice_number: \"rest.InvoiceNumber\"\n                invoice_date: \"rest.InvoiceDate\"\n                lines: \"rest.Lines\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/products\n          name: products\n          description: \"Product catalog synchronization\"\n          operations:\n            - method: GET\n              name: get-products\n              description: \"Retrieve product catalog items\"\n              call: \"toys-r-us-commerce.get-products\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-product\n              description: \"Create or update a product catalog item\"\n              call: \"toys-r-us-commerce.create-product\"\n              with:\n                supplier_sku: \"rest.SupplierSKU\"\
  \n                description: \"rest.Description\"\n                unit_price: \"rest.UnitPrice\"\n                in_stock: \"rest.InStock\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: dropship-fulfillment-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Toys R Us dropship fulfillment operations.\"\n      tools:\n        - name: get-orders\n          description: \"Retrieve Toys R Us purchase orders pending fulfillment\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"toys-r-us-commerce.get-orders\"\n          with:\n            status: \"tools.status\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-order\n          description: \"Retrieve a specific Toys R Us purchase order by key\"\n          hints:\n   \
  \         readOnly: true\n            openWorld: false\n          call: \"toys-r-us-commerce.get-order\"\n          with:\n            key: \"tools.key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-acknowledgement\n          description: \"Submit an order acknowledgement for a Toys R Us purchase order\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"toys-r-us-commerce.create-acknowledgement\"\n          with:\n            partner_po: \"tools.partner_po\"\n            lines: \"tools.lines\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-shipments\n          description: \"Retrieve Toys R Us shipment notifications\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"toys-r-us-commerce.get-shipments\"\n          outputParameters:\n     \
  \       - type: object\n              mapping: \"$.\"\n        - name: create-shipment\n          description: \"Submit a shipment notification for a fulfilled Toys R Us order\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"toys-r-us-commerce.create-shipment\"\n          with:\n            partner_po: \"tools.partner_po\"\n            ship_date: \"tools.ship_date\"\n            carrier: \"tools.carrier\"\n            packages: \"tools.packages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-invoices\n          description: \"Retrieve Toys R Us invoices\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"toys-r-us-commerce.get-invoices\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-invoice\n          description: \"Submit an invoice\
  \ for fulfilled Toys R Us order items\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"toys-r-us-commerce.create-invoice\"\n          with:\n            partner_po: \"tools.partner_po\"\n            invoice_number: \"tools.invoice_number\"\n            invoice_date: \"tools.invoice_date\"\n            lines: \"tools.lines\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-products\n          description: \"Retrieve Toys R Us product catalog items\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"toys-r-us-commerce.get-products\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: sync-product\n          description: \"Create or update a product in the Toys R Us catalog\"\n          hints:\n            readOnly: false\n            destructive: false\n\
  \            idempotent: true\n          call: \"toys-r-us-commerce.create-product\"\n          with:\n            supplier_sku: \"tools.supplier_sku\"\n            description: \"tools.description\"\n            unit_price: \"tools.unit_price\"\n            in_stock: \"tools.in_stock\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
