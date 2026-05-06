---
categories:
- procurement-supply-chain
consumed_apis: []
description: Unified procure-to-pay capability combining purchase orders, invoices, requisitions, suppliers, and receipts. Used by procurement teams and AP automation workflows.
layout: capability
name: SAP Ariba Procure-to-Pay
operations:
- description: List purchase orders
  method: GET
  name: list-purchase-orders
  path: /v1/purchase-orders
- description: Create a purchase order
  method: POST
  name: create-purchase-order
  path: /v1/purchase-orders
personas: []
provider_name: SAP Ariba
provider_slug: sap-ariba
search_terms:
- list receipts
- cancel purchase order
- approve an invoice for payment
- update purchase order
- get invoice details
- update a purchase order
- purchase order management
- approve invoice
- get purchase order details
- get invoice
- get purchase order
- reject invoice
- list requisitions
- list line items
- create a requisition
- procure-to-pay
- get requisition details
- contract management
- b2b
- create purchase order
- get supplier
- create invoice
- supply chain
- get supplier profile
- create receipt
- list suppliers
- cancel a purchase order
- spend analysis
- supplier management
- sap
- create a purchase order
- get requisition
- list receipts for an order
- list line items for an order
- ariba
- create a receipt
- create requisition
- list invoices
- create an invoice
- list purchase orders
- reject an invoice
- sourcing
- procurement
slug: procure-to-pay
source_filename: procure-to-pay.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SAP Ariba Procure-to-Pay\n  description: Unified procure-to-pay capability combining purchase orders, invoices, requisitions, suppliers, and receipts.\n    Used by procurement teams and AP automation workflows.\n  tags:\n  - SAP\n  - Ariba\n  - Procurement\n  - Procure-to-Pay\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ARIBA_OAUTH_TOKEN: ARIBA_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: procurement\n    baseUri: https://openapi.ariba.com/api/procurement/v1\n    description: SAP Ariba Procurement API for procure-to-pay lifecycle.\n    authentication:\n      type: bearer\n      token: '{{ARIBA_OAUTH_TOKEN}}'\n    resources:\n    - name: orders\n      path: /orders\n      description: Purchase order operations\n      operations:\n      - name: list-purchase-orders\n        method: GET\n        description: List purchase orders\n        outputRawFormat: json\n       \
  \ outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-purchase-order\n        method: POST\n        description: Create a purchase order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-purchase-order\n        method: GET\n        description: Get purchase order details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-purchase-order\n        method: PATCH\n        description: Update a purchase order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cancel-purchase-order\n        method: POST\n        description: Cancel a purchase order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n      - name: list-line-items\n        method: GET\n        description: List line items for an order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-line-item\n        method: GET\n        description: Get a specific line item\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invoices\n      path: /invoices\n      description: Invoice operations\n      operations:\n      - name: list-invoices\n        method: GET\n        description: List invoices\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-invoice\n        method: POST\n        description: Create an invoice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: get-invoice\n        method: GET\n        description: Get invoice details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: approve-invoice\n        method: POST\n        description: Approve an invoice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: reject-invoice\n        method: POST\n        description: Reject an invoice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: suppliers\n      path: /suppliers\n      description: Supplier management\n      operations:\n      - name: list-suppliers\n        method: GET\n        description: List suppliers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-supplier\n\
  \        method: GET\n        description: Get supplier profile\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: requisitions\n      path: /requisitions\n      description: Requisition management\n      operations:\n      - name: list-requisitions\n        method: GET\n        description: List requisitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-requisition\n        method: POST\n        description: Create a requisition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-requisition\n        method: GET\n        description: Get requisition details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: receipts\n\
  \      path: /orders/{orderId}/receipts\n      description: Receipt operations\n      operations:\n      - name: list-receipts\n        method: GET\n        description: List receipts for an order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-receipt\n        method: POST\n        description: Create a receipt\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: procure-to-pay-api\n    description: Unified REST API for SAP Ariba procure-to-pay operations.\n    resources:\n    - path: /v1/purchase-orders\n      name: purchase-orders\n      description: Purchase order management\n      operations:\n      - method: GET\n        name: list-purchase-orders\n        description: List purchase orders\n        call: procurement.list-purchase-orders\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: POST\n        name: create-purchase-order\n        description: Create a purchase order\n        call: procurement.create-purchase-order\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: procure-to-pay-mcp\n    transport: http\n    description: MCP server for AI-assisted SAP Ariba procure-to-pay operations.\n    tools:\n    - name: list-purchase-orders\n      description: List purchase orders\n      hints:\n        readOnly: true\n        openWorld: true\n      call: procurement.list-purchase-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-purchase-order\n      description: Get purchase order details\n      hints:\n        readOnly: true\n      call: procurement.get-purchase-order\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-purchase-order\n      description: Create a\
  \ purchase order\n      call: procurement.create-purchase-order\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-purchase-order\n      description: Update a purchase order\n      call: procurement.update-purchase-order\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-purchase-order\n      description: Cancel a purchase order\n      hints:\n        destructive: true\n      call: procurement.cancel-purchase-order\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-line-items\n      description: List line items for an order\n      hints:\n        readOnly: true\n      call: procurement.list-line-items\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-invoices\n      description: List invoices\n      hints:\n        readOnly: true\n        openWorld: true\n      call: procurement.list-invoices\n      outputParameters:\n      - type: object\n  \
  \      mapping: $.\n    - name: get-invoice\n      description: Get invoice details\n      hints:\n        readOnly: true\n      call: procurement.get-invoice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-invoice\n      description: Create an invoice\n      call: procurement.create-invoice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: approve-invoice\n      description: Approve an invoice for payment\n      call: procurement.approve-invoice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: reject-invoice\n      description: Reject an invoice\n      call: procurement.reject-invoice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-suppliers\n      description: List suppliers\n      hints:\n        readOnly: true\n        openWorld: true\n      call: procurement.list-suppliers\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: get-supplier\n      description: Get supplier profile\n      hints:\n        readOnly: true\n      call: procurement.get-supplier\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-requisitions\n      description: List requisitions\n      hints:\n        readOnly: true\n      call: procurement.list-requisitions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-requisition\n      description: Create a requisition\n      call: procurement.create-requisition\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-requisition\n      description: Get requisition details\n      hints:\n        readOnly: true\n      call: procurement.get-requisition\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-receipts\n      description: List receipts for an order\n      hints:\n        readOnly: true\n      call: procurement.list-receipts\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: create-receipt\n      description: Create a receipt\n      call: procurement.create-receipt\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sap-ariba/refs/heads/main/capabilities/procure-to-pay.yaml
tags:
- SAP
- Ariba
- Procurement
- Procure-to-Pay
tools:
- description: List purchase orders
  hints:
    openWorld: true
    readOnly: true
  name: list-purchase-orders
- description: Get purchase order details
  hints:
    readOnly: true
  name: get-purchase-order
- description: Create a purchase order
  hints: {}
  name: create-purchase-order
- description: Update a purchase order
  hints: {}
  name: update-purchase-order
- description: Cancel a purchase order
  hints:
    destructive: true
  name: cancel-purchase-order
- description: List line items for an order
  hints:
    readOnly: true
  name: list-line-items
- description: List invoices
  hints:
    openWorld: true
    readOnly: true
  name: list-invoices
- description: Get invoice details
  hints:
    readOnly: true
  name: get-invoice
- description: Create an invoice
  hints: {}
  name: create-invoice
- description: Approve an invoice for payment
  hints: {}
  name: approve-invoice
- description: Reject an invoice
  hints: {}
  name: reject-invoice
- description: List suppliers
  hints:
    openWorld: true
    readOnly: true
  name: list-suppliers
- description: Get supplier profile
  hints:
    readOnly: true
  name: get-supplier
- description: List requisitions
  hints:
    readOnly: true
  name: list-requisitions
- description: Create a requisition
  hints: {}
  name: create-requisition
- description: Get requisition details
  hints:
    readOnly: true
  name: get-requisition
- description: List receipts for an order
  hints:
    readOnly: true
  name: list-receipts
- description: Create a receipt
  hints: {}
  name: create-receipt
---
