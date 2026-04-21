---
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
- create invoice
- create purchase order
- supplier management
- sap
- update a purchase order
- list receipts
- create a purchase order
- create an invoice
- create a requisition
- update purchase order
- create requisition
- cancel a purchase order
- supply chain
- purchase order management
- approve invoice
- list suppliers
- procure-to-pay
- procurement
- get supplier
- list receipts for an order
- list purchase orders
- sourcing
- get purchase order details
- get purchase order
- get invoice details
- list invoices
- approve an invoice for payment
- cancel purchase order
- create receipt
- get invoice
- get requisition details
- b2b
- create a receipt
- spend analysis
- get requisition
- reject invoice
- contract management
- list line items for an order
- reject an invoice
- ariba
- list line items
- get supplier profile
- list requisitions
slug: procure-to-pay
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
