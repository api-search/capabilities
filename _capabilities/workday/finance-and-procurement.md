---
consumed_apis:
- workday-finance
description: Unified financial operations combining Financial Management and procurement data for finance teams to manage accounting, suppliers, expenses, and invoices.
layout: capability
name: Workday Finance and Procurement
operations:
- description: List accounting journals
  method: GET
  name: list-journals
  path: /v1/accounting-journals
- description: List suppliers
  method: GET
  name: list-suppliers
  path: /v1/suppliers
personas: []
provider_name: Workday
provider_slug: workday
search_terms:
- accounting journals
- list expense reports
- get a supplier by id
- get supplier
- get expense report
- hcm
- suppliers
- get accounting journal
- list customer invoices
- get an expense report by id
- workday
- list purchase orders
- list suppliers
- enterprise software
- financial management
- procurement
- saas
- cloud computing
- get an accounting journal by id
- list journals
- list accounting journals
slug: finance-and-procurement
tags:
- Workday
- Financial Management
- Procurement
tools:
- description: List accounting journals
  hints:
    readOnly: true
  name: list-accounting-journals
- description: Get an accounting journal by ID
  hints:
    readOnly: true
  name: get-accounting-journal
- description: List suppliers
  hints:
    readOnly: true
  name: list-suppliers
- description: Get a supplier by ID
  hints:
    readOnly: true
  name: get-supplier
- description: List purchase orders
  hints:
    readOnly: true
  name: list-purchase-orders
- description: List expense reports
  hints:
    readOnly: true
  name: list-expense-reports
- description: Get an expense report by ID
  hints:
    readOnly: true
  name: get-expense-report
- description: List customer invoices
  hints:
    readOnly: true
  name: list-customer-invoices
---
