---
categories:
- procurement-supply-chain
consumed_apis:
- procurement
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
- get supplier
- approve invoice
- purchase order management
- update a purchase order
- create an invoice
- create receipt
- list invoices
- ariba
- update purchase order
- create purchase order
- list suppliers
- get requisition details
- sourcing
- create a requisition
- list line items for an order
- create a purchase order
- sap
- spend analysis
- cancel purchase order
- create invoice
- get supplier profile
- list receipts
- create requisition
- get invoice
- supplier management
- b2b
- procurement
- get purchase order
- get invoice details
- reject invoice
- create a receipt
- procure-to-pay
- approve an invoice for payment
- reject an invoice
- list line items
- cancel a purchase order
- contract management
- get requisition
- supply chain
- list requisitions
- list receipts for an order
- get purchase order details
- list purchase orders
slug: procure-to-pay
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: \"SAP Ariba Procure-to-Pay\"\n  description: \"Unified procure-to-pay capability combining purchase orders, invoices, requisitions, suppliers, and receipts. Used by procurement teams and AP automation workflows.\"\n  tags: [SAP, Ariba, Procurement, Procure-to-Pay]\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\nbinds:\n  - namespace: env\n    keys:\n      ARIBA_OAUTH_TOKEN: ARIBA_OAUTH_TOKEN\ncapability:\n  consumes:\n    - import: procurement\n      location: ./shared/procurement.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: procure-to-pay-api\n      description: \"Unified REST API for SAP Ariba procure-to-pay operations.\"\n      resources:\n        - path: /v1/purchase-orders\n          name: purchase-orders\n          description: \"Purchase order management\"\n          operations:\n            - { method: GET, name: list-purchase-orders, description: \"List purchase orders\", call: \"procurement.list-purchase-orders\"\
  , outputParameters: [{ type: object, mapping: \"$.\" }] }\n            - { method: POST, name: create-purchase-order, description: \"Create a purchase order\", call: \"procurement.create-purchase-order\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n    - type: mcp\n      port: 9090\n      namespace: procure-to-pay-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SAP Ariba procure-to-pay operations.\"\n      tools:\n        - { name: list-purchase-orders, description: \"List purchase orders\", hints: { readOnly: true, openWorld: true }, call: \"procurement.list-purchase-orders\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: get-purchase-order, description: \"Get purchase order details\", hints: { readOnly: true }, call: \"procurement.get-purchase-order\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: create-purchase-order, description: \"Create a purchase order\", call: \"procurement.create-purchase-order\"\
  , outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: update-purchase-order, description: \"Update a purchase order\", call: \"procurement.update-purchase-order\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: cancel-purchase-order, description: \"Cancel a purchase order\", hints: { destructive: true }, call: \"procurement.cancel-purchase-order\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-line-items, description: \"List line items for an order\", hints: { readOnly: true }, call: \"procurement.list-line-items\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-invoices, description: \"List invoices\", hints: { readOnly: true, openWorld: true }, call: \"procurement.list-invoices\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: get-invoice, description: \"Get invoice details\", hints: { readOnly: true }, call: \"procurement.get-invoice\", outputParameters:\
  \ [{ type: object, mapping: \"$.\" }] }\n        - { name: create-invoice, description: \"Create an invoice\", call: \"procurement.create-invoice\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: approve-invoice, description: \"Approve an invoice for payment\", call: \"procurement.approve-invoice\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: reject-invoice, description: \"Reject an invoice\", call: \"procurement.reject-invoice\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-suppliers, description: \"List suppliers\", hints: { readOnly: true, openWorld: true }, call: \"procurement.list-suppliers\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: get-supplier, description: \"Get supplier profile\", hints: { readOnly: true }, call: \"procurement.get-supplier\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-requisitions, description: \"\
  List requisitions\", hints: { readOnly: true }, call: \"procurement.list-requisitions\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: create-requisition, description: \"Create a requisition\", call: \"procurement.create-requisition\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: get-requisition, description: \"Get requisition details\", hints: { readOnly: true }, call: \"procurement.get-requisition\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-receipts, description: \"List receipts for an order\", hints: { readOnly: true }, call: \"procurement.list-receipts\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: create-receipt, description: \"Create a receipt\", call: \"procurement.create-receipt\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n"
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
