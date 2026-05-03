---
categories: []
consumed_apis:
- ti-store
- ti-product-info
description: Unified semiconductor procurement capability for electronics engineers, procurement teams, and supply chain managers. Combines TI's Store API and Product Information API to enable part research, inventory checking, order placement, shipment tracking, and invoice retrieval from a single interface.
layout: capability
name: Texas Instruments Semiconductor Procurement
operations:
- description: Get inventory and pricing for a TI part number
  method: GET
  name: get-product-inventory
  path: /v1/products/{partNumber}
- description: Get parametric and technical specifications
  method: GET
  name: get-product-specs
  path: /v1/products/{partNumber}/specs
- description: Get quality certifications and reliability data
  method: GET
  name: get-product-quality
  path: /v1/products/{partNumber}/quality
- description: Get full product catalog
  method: GET
  name: get-catalog
  path: /v1/catalog
- description: Place a new order
  method: POST
  name: create-order
  path: /v1/orders
- description: Get order details
  method: GET
  name: get-order
  path: /v1/orders/{orderNumber}
- description: Get shipment tracking information
  method: GET
  name: get-shipments
  path: /v1/shipments
- description: Get invoices for an order
  method: GET
  name: get-invoices
  path: /v1/invoices
personas: []
provider_name: Texas Instruments
provider_slug: texas-instruments
search_terms:
- supply chain
- get quality certifications and reliability data
- ti part quality and reliability certifications
- ti part lookup with inventory, pricing, and specifications
- create order
- full ti product catalog
- get product quality
- get order status
- financial documents and invoices
- get invoices for an order
- place order
- get full product catalog
- get shipment tracking information and carrier details for a ti order
- inventory
- get inventory and pricing for a ti part number
- place a new order
- place a new order for ti semiconductors with specified line items
- get quality certifications (rohs, aec-q100, msl) and reliability data for a ti part
- texas instruments
- get product specifications
- retrieve invoices and financial documents for a ti order
- ordering
- get order
- get product quality certifications
- electronics
- semiconductors
- get shipment tracking information
- order status and details
- get shipments
- get parametric and technical specifications
- get order details
- procurement
- get product specs
- shipment tracking via asn
- ti store order management
- get real-time inventory availability and pricing breaks for a ti part number
- get invoices
- track shipment
- check the status and details of a placed ti order
- get technical parametric specifications for a ti semiconductor part
- get catalog
- ti part technical specifications and parametric data
- get product inventory
slug: semiconductor-procurement
source_filename: semiconductor-procurement.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Texas Instruments Semiconductor Procurement\"\n  description: >-\n    Unified semiconductor procurement capability for electronics engineers,\n    procurement teams, and supply chain managers. Combines TI's Store API\n    and Product Information API to enable part research, inventory checking,\n    order placement, shipment tracking, and invoice retrieval from a single\n    interface.\n  tags:\n    - Texas Instruments\n    - Procurement\n    - Supply Chain\n    - Semiconductors\n    - Ordering\n    - Inventory\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TI_ACCESS_TOKEN: TI_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: ti-store\n      location: ./shared/ti-store.yaml\n    - import: ti-product-info\n      location: ./shared/ti-product-information.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: ti-procurement-api\n      description: \"Unified\
  \ REST API for TI semiconductor procurement workflows.\"\n      resources:\n        - path: /v1/products/{partNumber}\n          name: product\n          description: \"TI part lookup with inventory, pricing, and specifications\"\n          operations:\n            - method: GET\n              name: get-product-inventory\n              description: \"Get inventory and pricing for a TI part number\"\n              call: \"ti-store.get-product-inventory\"\n              with:\n                partNumber: \"rest.partNumber\"\n                currency: \"rest.currency\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/products/{partNumber}/specs\n          name: product-specs\n          description: \"TI part technical specifications and parametric data\"\n          operations:\n            - method: GET\n              name: get-product-specs\n              description: \"Get parametric and technical specifications\"\
  \n              call: \"ti-product-info.get-product-information\"\n              with:\n                partNumber: \"rest.partNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/products/{partNumber}/quality\n          name: product-quality\n          description: \"TI part quality and reliability certifications\"\n          operations:\n            - method: GET\n              name: get-product-quality\n              description: \"Get quality certifications and reliability data\"\n              call: \"ti-product-info.get-product-information-extended\"\n              with:\n                partNumber: \"rest.partNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/catalog\n          name: catalog\n          description: \"Full TI product catalog\"\n          operations:\n            - method: GET\n              name: get-catalog\n\
  \              description: \"Get full product catalog\"\n              call: \"ti-store.get-catalog\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/orders\n          name: orders\n          description: \"TI store order management\"\n          operations:\n            - method: POST\n              name: create-order\n              description: \"Place a new order\"\n              call: \"ti-store.create-order\"\n              with:\n                checkoutProfileId: \"rest.checkoutProfileId\"\n                poNumber: \"rest.poNumber\"\n                lineItems: \"rest.lineItems\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/orders/{orderNumber}\n          name: order\n          description: \"Order status and details\"\n          operations:\n            - method: GET\n              name: get-order\n              description: \"\
  Get order details\"\n              call: \"ti-store.get-order\"\n              with:\n                orderNumber: \"rest.orderNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/shipments\n          name: shipments\n          description: \"Shipment tracking via ASN\"\n          operations:\n            - method: GET\n              name: get-shipments\n              description: \"Get shipment tracking information\"\n              call: \"ti-store.get-ship-notices\"\n              with:\n                orderNumber: \"rest.orderNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/invoices\n          name: invoices\n          description: \"Financial documents and invoices\"\n          operations:\n            - method: GET\n              name: get-invoices\n              description: \"Get invoices for an order\"\n             \
  \ call: \"ti-store.get-financial-documents\"\n              with:\n                orderNumber: \"rest.orderNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: ti-procurement-mcp\n      transport: http\n      description: \"MCP server for AI-assisted TI semiconductor procurement.\"\n      tools:\n        - name: get-product-inventory\n          description: \"Get real-time inventory availability and pricing breaks for a TI part number\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"ti-store.get-product-inventory\"\n          with:\n            partNumber: \"tools.partNumber\"\n            currency: \"tools.currency\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-product-specifications\n          description: \"Get technical parametric specifications for a TI semiconductor\
  \ part\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"ti-product-info.get-product-information\"\n          with:\n            partNumber: \"tools.partNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-product-quality-certifications\n          description: \"Get quality certifications (RoHS, AEC-Q100, MSL) and reliability data for a TI part\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"ti-product-info.get-product-information-extended\"\n          with:\n            partNumber: \"tools.partNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: place-order\n          description: \"Place a new order for TI semiconductors with specified line items\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n   \
  \       call: \"ti-store.create-order\"\n          with:\n            checkoutProfileId: \"tools.checkoutProfileId\"\n            poNumber: \"tools.poNumber\"\n            lineItems: \"tools.lineItems\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-order-status\n          description: \"Check the status and details of a placed TI order\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"ti-store.get-order\"\n          with:\n            orderNumber: \"tools.orderNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: track-shipment\n          description: \"Get shipment tracking information and carrier details for a TI order\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"ti-store.get-ship-notices\"\n          with:\n            orderNumber: \"tools.orderNumber\"\n     \
  \     outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-invoices\n          description: \"Retrieve invoices and financial documents for a TI order\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"ti-store.get-financial-documents\"\n          with:\n            orderNumber: \"tools.orderNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/texas-instruments/refs/heads/main/capabilities/semiconductor-procurement.yaml
tags:
- Texas Instruments
- Procurement
- Supply Chain
- Semiconductors
- Ordering
- Inventory
tools:
- description: Get real-time inventory availability and pricing breaks for a TI part number
  hints:
    openWorld: false
    readOnly: true
  name: get-product-inventory
- description: Get technical parametric specifications for a TI semiconductor part
  hints:
    openWorld: false
    readOnly: true
  name: get-product-specifications
- description: Get quality certifications (RoHS, AEC-Q100, MSL) and reliability data for a TI part
  hints:
    openWorld: false
    readOnly: true
  name: get-product-quality-certifications
- description: Place a new order for TI semiconductors with specified line items
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: place-order
- description: Check the status and details of a placed TI order
  hints:
    openWorld: false
    readOnly: true
  name: get-order-status
- description: Get shipment tracking information and carrier details for a TI order
  hints:
    openWorld: false
    readOnly: true
  name: track-shipment
- description: Retrieve invoices and financial documents for a TI order
  hints:
    openWorld: false
    readOnly: true
  name: get-invoices
---
