---
categories:
- procurement-supply-chain
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
- retrieve fixed assets.
- ar create invoice
- create an ar invoice.
- po create purchase order
- get journals
- ar get receipts
- financials
- procurement
- retrieve bank accounts.
- retrieve suppliers.
- ar invoice management.
- po get suppliers
- ap invoice management.
- retrieve ap invoices.
- e-business suite
- create an ap invoice.
- get ar invoices
- ap create invoice
- business applications
- retrieve payments.
- get ap invoice by id.
- get purchase order by id.
- list journal entries.
- po get purchase orders
- gl get journals
- ce get bank accounts
- get purchase orders
- create a purchase order.
- enterprise
- ap get invoice by id
- retrieve receipts.
- list purchase orders.
- ar get invoices
- get suppliers
- po get requisitions
- erp
- oracle
- list ar invoices.
- retrieve ar invoices.
- journal entry management.
- gl create journal
- create a journal entry.
- retrieve requisitions.
- get ap invoices
- retrieve general ledger journal entries.
- list ap invoices.
- ap get payments
- po get purchase order by id
- supplier management.
- list suppliers.
- purchase order management.
- retrieve purchase orders.
- fa get assets
- ap get invoices
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
