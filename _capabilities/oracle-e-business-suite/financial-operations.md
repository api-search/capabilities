---
consumed_apis:
- oracle-financial-services
- oracle-supply-chain
description: End-to-end financial operations combining General Ledger, AP/AR, procurement, and cash management. Used by finance teams and controllers for the procure-to-pay and order-to-cash cycles.
layout: capability
name: Oracle EBS Financial Operations
operations:
- description: List journal entries.
  method: GET
  name: get-journals
  path: /v1/journals
- description: List AP invoices.
  method: GET
  name: get-ap-invoices
  path: /v1/ap-invoices
- description: List AR invoices.
  method: GET
  name: get-ar-invoices
  path: /v1/ar-invoices
- description: List purchase orders.
  method: GET
  name: get-purchase-orders
  path: /v1/purchase-orders
- description: List suppliers.
  method: GET
  name: get-suppliers
  path: /v1/suppliers
personas: []
provider_name: Oracle E-Business Suite
provider_slug: oracle-e-business-suite
search_terms:
- procurement
- gl get journals
- ar get receipts
- retrieve requisitions.
- po get suppliers
- retrieve ap invoices.
- retrieve purchase orders.
- create an ar invoice.
- financials
- ap create invoice
- ap invoice management.
- list suppliers.
- po get requisitions
- get ar invoices
- retrieve receipts.
- journal entry management.
- retrieve ar invoices.
- retrieve fixed assets.
- enterprise
- fa get assets
- retrieve bank accounts.
- create a journal entry.
- retrieve payments.
- retrieve general ledger journal entries.
- ap get invoices
- get purchase order by id.
- create an ap invoice.
- get ap invoices
- ar get invoices
- retrieve suppliers.
- list journal entries.
- po get purchase orders
- ap get payments
- list ap invoices.
- gl create journal
- oracle
- ce get bank accounts
- list purchase orders.
- supplier management.
- ap get invoice by id
- po create purchase order
- po get purchase order by id
- get purchase orders
- list ar invoices.
- purchase order management.
- business applications
- get ap invoice by id.
- get journals
- create a purchase order.
- e-business suite
- ar invoice management.
- ar create invoice
- erp
- get suppliers
slug: financial-operations
tags:
- Oracle
- Financials
- Procurement
- ERP
tools:
- description: Retrieve General Ledger journal entries.
  hints:
    openWorld: true
    readOnly: true
  name: gl-get-journals
- description: Create a journal entry.
  hints:
    readOnly: false
  name: gl-create-journal
- description: Retrieve AP invoices.
  hints:
    readOnly: true
  name: ap-get-invoices
- description: Create an AP invoice.
  hints:
    readOnly: false
  name: ap-create-invoice
- description: Get AP invoice by ID.
  hints:
    readOnly: true
  name: ap-get-invoice-by-id
- description: Retrieve payments.
  hints:
    readOnly: true
  name: ap-get-payments
- description: Retrieve AR invoices.
  hints:
    readOnly: true
  name: ar-get-invoices
- description: Create an AR invoice.
  hints:
    readOnly: false
  name: ar-create-invoice
- description: Retrieve receipts.
  hints:
    readOnly: true
  name: ar-get-receipts
- description: Retrieve fixed assets.
  hints:
    readOnly: true
  name: fa-get-assets
- description: Retrieve bank accounts.
  hints:
    readOnly: true
  name: ce-get-bank-accounts
- description: Retrieve purchase orders.
  hints:
    readOnly: true
  name: po-get-purchase-orders
- description: Create a purchase order.
  hints:
    readOnly: false
  name: po-create-purchase-order
- description: Get purchase order by ID.
  hints:
    readOnly: true
  name: po-get-purchase-order-by-id
- description: Retrieve requisitions.
  hints:
    readOnly: true
  name: po-get-requisitions
- description: Retrieve suppliers.
  hints:
    readOnly: true
  name: po-get-suppliers
---
