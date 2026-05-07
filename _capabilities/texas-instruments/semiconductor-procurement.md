---
categories: []
consumed_apis: []
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
- get product specifications
- track shipment
- get invoices for an order
- procurement
- ti part technical specifications and parametric data
- get product inventory
- create order
- order status and details
- get real-time inventory availability and pricing breaks for a ti part number
- get shipment tracking information
- get invoices
- supply chain
- ordering
- ti part quality and reliability certifications
- get quality certifications (rohs, aec-q100, msl) and reliability data for a ti part
- inventory
- semiconductors
- check the status and details of a placed ti order
- retrieve invoices and financial documents for a ti order
- get product quality certifications
- get product specs
- place a new order for ti semiconductors with specified line items
- texas instruments
- get shipment tracking information and carrier details for a ti order
- get shipments
- place a new order
- ti part lookup with inventory, pricing, and specifications
- get quality certifications and reliability data
- get order details
- shipment tracking via asn
- get parametric and technical specifications
- place order
- get order status
- get inventory and pricing for a ti part number
- financial documents and invoices
- electronics
- get technical parametric specifications for a ti semiconductor part
- full ti product catalog
- get catalog
- get full product catalog
- ti store order management
- get order
- get product quality
slug: semiconductor-procurement
source_filename: semiconductor-procurement.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Texas Instruments Semiconductor Procurement\n  description: Unified semiconductor procurement capability for electronics engineers, procurement teams, and supply chain\n    managers. Combines TI's Store API and Product Information API to enable part research, inventory checking, order placement,\n    shipment tracking, and invoice retrieval from a single interface.\n  tags:\n  - Texas Instruments\n  - Procurement\n  - Supply Chain\n  - Semiconductors\n  - Ordering\n  - Inventory\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TI_ACCESS_TOKEN: TI_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: ti-store\n    baseUri: https://transact.ti.com/v2/store\n    description: Texas Instruments store ordering and inventory API\n    authentication:\n      type: bearer\n      token: '{{TI_ACCESS_TOKEN}}'\n    resources:\n    - name: products\n      path: /products/{partNumber}\n     \
  \ description: Get inventory and pricing for a TI part\n      operations:\n      - name: get-product-inventory\n        method: GET\n        description: Get real-time inventory and pricing for a part number\n        inputParameters:\n        - name: partNumber\n          in: path\n          type: string\n          required: true\n          description: TI orderable part number\n        - name: currency\n          in: query\n          type: string\n          required: false\n          description: 'Currency code (default: USD)'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: catalog\n      path: /products/catalog\n      description: Full product catalog\n      operations:\n      - name: get-catalog\n        method: GET\n        description: Get full product catalog with pricing (rate limited to 6/day)\n        inputParameters:\n        - name: currency\n          in: query\n          type: string\n\
  \          required: false\n          description: Currency code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders\n      path: /orders\n      description: Create store orders\n      operations:\n      - name: create-order\n        method: POST\n        description: Create a new TI store order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            checkoutProfileId: '{{tools.checkoutProfileId}}'\n            customerPurchaseOrderNumber: '{{tools.poNumber}}'\n            lineItems: '{{tools.lineItems}}'\n    - name: order\n      path: /orders/{orderNumber}\n      description: Retrieve order details\n      operations:\n      - name: get-order\n        method: GET\n        description: Get order status and details\n        inputParameters:\n        - name:\
  \ orderNumber\n          in: path\n          type: string\n          required: true\n          description: TI order number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: asn\n      path: /advanced-ship-notices\n      description: Shipment tracking via ASN\n      operations:\n      - name: get-ship-notices\n        method: GET\n        description: Get advanced ship notice for an order\n        inputParameters:\n        - name: orderNumber\n          in: query\n          type: string\n          required: true\n          description: TI order number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: financial-documents\n      path: /financial-documents\n      description: Invoice and financial document retrieval\n      operations:\n      - name: get-financial-documents\n        method: GET\n        description:\
  \ Get invoices for an order\n        inputParameters:\n        - name: orderNumber\n          in: query\n          type: string\n          required: false\n          description: TI order number\n        - name: financialDocumentNumber\n          in: query\n          type: string\n          required: false\n          description: Financial document number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: ti-product-info\n    baseUri: https://transact.ti.com/v1\n    description: Texas Instruments product information and parametric data API\n    authentication:\n      type: bearer\n      token: '{{TI_ACCESS_TOKEN}}'\n    resources:\n    - name: products\n      path: /products/{partNumber}\n      description: Get product details and parametric data\n      operations:\n      - name: get-product-information\n        method: GET\n        description: Get basic product details and parametric\
  \ data (3000/day limit)\n        inputParameters:\n        - name: partNumber\n          in: path\n          type: string\n          required: true\n          description: TI part number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: products-extended\n      path: /products-extended/{partNumber}\n      description: Get comprehensive product data including quality/reliability\n      operations:\n      - name: get-product-information-extended\n        method: GET\n        description: Get comprehensive product data including quality/reliability (1500/day limit)\n        inputParameters:\n        - name: partNumber\n          in: path\n          type: string\n          required: true\n          description: TI part number\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number (0-indexed)\n        outputRawFormat: json\n  \
  \      outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ti-procurement-api\n    description: Unified REST API for TI semiconductor procurement workflows.\n    resources:\n    - path: /v1/products/{partNumber}\n      name: product\n      description: TI part lookup with inventory, pricing, and specifications\n      operations:\n      - method: GET\n        name: get-product-inventory\n        description: Get inventory and pricing for a TI part number\n        call: ti-store.get-product-inventory\n        with:\n          partNumber: rest.partNumber\n          currency: rest.currency\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products/{partNumber}/specs\n      name: product-specs\n      description: TI part technical specifications and parametric data\n      operations:\n      - method: GET\n        name: get-product-specs\n        description:\
  \ Get parametric and technical specifications\n        call: ti-product-info.get-product-information\n        with:\n          partNumber: rest.partNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products/{partNumber}/quality\n      name: product-quality\n      description: TI part quality and reliability certifications\n      operations:\n      - method: GET\n        name: get-product-quality\n        description: Get quality certifications and reliability data\n        call: ti-product-info.get-product-information-extended\n        with:\n          partNumber: rest.partNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/catalog\n      name: catalog\n      description: Full TI product catalog\n      operations:\n      - method: GET\n        name: get-catalog\n        description: Get full product catalog\n        call: ti-store.get-catalog\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/orders\n      name: orders\n      description: TI store order management\n      operations:\n      - method: POST\n        name: create-order\n        description: Place a new order\n        call: ti-store.create-order\n        with:\n          checkoutProfileId: rest.checkoutProfileId\n          poNumber: rest.poNumber\n          lineItems: rest.lineItems\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders/{orderNumber}\n      name: order\n      description: Order status and details\n      operations:\n      - method: GET\n        name: get-order\n        description: Get order details\n        call: ti-store.get-order\n        with:\n          orderNumber: rest.orderNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/shipments\n      name: shipments\n      description: Shipment tracking via ASN\n      operations:\n      - method: GET\n        name: get-shipments\n\
  \        description: Get shipment tracking information\n        call: ti-store.get-ship-notices\n        with:\n          orderNumber: rest.orderNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices\n      name: invoices\n      description: Financial documents and invoices\n      operations:\n      - method: GET\n        name: get-invoices\n        description: Get invoices for an order\n        call: ti-store.get-financial-documents\n        with:\n          orderNumber: rest.orderNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: ti-procurement-mcp\n    transport: http\n    description: MCP server for AI-assisted TI semiconductor procurement.\n    tools:\n    - name: get-product-inventory\n      description: Get real-time inventory availability and pricing breaks for a TI part number\n      hints:\n        readOnly: true\n        openWorld: false\n      call:\
  \ ti-store.get-product-inventory\n      with:\n        partNumber: tools.partNumber\n        currency: tools.currency\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-product-specifications\n      description: Get technical parametric specifications for a TI semiconductor part\n      hints:\n        readOnly: true\n        openWorld: false\n      call: ti-product-info.get-product-information\n      with:\n        partNumber: tools.partNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-product-quality-certifications\n      description: Get quality certifications (RoHS, AEC-Q100, MSL) and reliability data for a TI part\n      hints:\n        readOnly: true\n        openWorld: false\n      call: ti-product-info.get-product-information-extended\n      with:\n        partNumber: tools.partNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: place-order\n      description: Place a\
  \ new order for TI semiconductors with specified line items\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ti-store.create-order\n      with:\n        checkoutProfileId: tools.checkoutProfileId\n        poNumber: tools.poNumber\n        lineItems: tools.lineItems\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-order-status\n      description: Check the status and details of a placed TI order\n      hints:\n        readOnly: true\n        openWorld: false\n      call: ti-store.get-order\n      with:\n        orderNumber: tools.orderNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: track-shipment\n      description: Get shipment tracking information and carrier details for a TI order\n      hints:\n        readOnly: true\n        openWorld: false\n      call: ti-store.get-ship-notices\n      with:\n        orderNumber: tools.orderNumber\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-invoices\n      description: Retrieve invoices and financial documents for a TI order\n      hints:\n        readOnly: true\n        openWorld: false\n      call: ti-store.get-financial-documents\n      with:\n        orderNumber: tools.orderNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
