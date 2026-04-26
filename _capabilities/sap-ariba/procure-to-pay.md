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
- create a requisition
- create purchase order
- get invoice
- approve an invoice for payment
- list line items for an order
- approve invoice
- reject invoice
- cancel a purchase order
- list line items
- list receipts for an order
- update a purchase order
- b2b
- list requisitions
- list suppliers
- spend analysis
- procurement
- create a purchase order
- get supplier profile
- create requisition
- supplier management
- purchase order management
- create a receipt
- list receipts
- contract management
- get purchase order
- get requisition details
- get invoice details
- procure-to-pay
- create receipt
- ariba
- cancel purchase order
- get purchase order details
- sap
- create invoice
- list invoices
- create an invoice
- get requisition
- sourcing
- list purchase orders
- supply chain
- get supplier
- update purchase order
- reject an invoice
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
