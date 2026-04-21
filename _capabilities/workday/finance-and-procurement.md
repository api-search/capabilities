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
- get a supplier by id
- get accounting journal
- suppliers
- list expense reports
- financial management
- list suppliers
- workday
- procurement
- get supplier
- list purchase orders
- saas
- list customer invoices
- hcm
- list accounting journals
- enterprise software
- get an expense report by id
- get an accounting journal by id
- list journals
- get expense report
- cloud computing
- accounting journals
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
