---
categories: []
consumed_apis:
- financials
- epm
- approval-workflow
description: Unified workflow for finance controllers combining general ledger, accounts payable, accounts receivable, expenses, budgeting, forecasting, analytics, and approval workflows across PeopleSoft Financials, EPM, and Approval Workflow Engine APIs.
layout: capability
name: PeopleSoft Finance And Accounting
operations:
- description: Retrieve general ledger journal entries.
  method: GET
  name: list-journal-entries
  path: /v1/journal-entries
- description: Retrieve accounts payable vouchers.
  method: GET
  name: list-vouchers
  path: /v1/vouchers
- description: Retrieve accounts receivable items.
  method: GET
  name: list-ar-items
  path: /v1/receivable-items
- description: Retrieve expense reports.
  method: GET
  name: list-expense-reports
  path: /v1/expense-reports
- description: Retrieve budget definitions and data.
  method: GET
  name: list-budgets
  path: /v1/budgets
- description: Retrieve forecast data and projections.
  method: GET
  name: list-forecasts
  path: /v1/forecasts
- description: Retrieve performance analytics reports.
  method: GET
  name: list-analytics-reports
  path: /v1/analytics-reports
- description: Retrieve pending finance approval requests.
  method: GET
  name: list-pending-approvals
  path: /v1/approvals
- description: Approve, deny, or push back a finance approval request.
  method: PUT
  name: process-approval
  path: /v1/approvals/{approvalId}
personas: []
provider_name: PeopleSoft
provider_slug: peoplesoft
search_terms:
- accounts receivable items
- budgeting
- accounting
- retrieve expense reports.
- expense reports
- retrieve budget definitions and data.
- list budgets
- financial and supply chain management.
- finance
- retrieve accounts payable vouchers.
- individual approval operations
- retrieve performance analytics reports.
- forecast data and projections
- peoplesoft
- list analytics reports
- list forecasts
- human capital management.
- retrieve forecast data and projections.
- campus solutions
- approve, deny, or push back a finance approval request.
- hcm
- campus solutions.
- peopletools platform services.
- finance approval requests
- performance analytics reports
- retrieve accounts receivable items.
- erp
- enterprise software
- list pending approvals
- list ar items
- accounts payable vouchers
- process approval
- retrieve general ledger journal entries.
- list expense reports
- supply chain management
- general ledger
- retrieve pending finance approval requests.
- list vouchers
- crm
- financial management
- general ledger journal entries
- budget definitions and data
- forecasting
- list journal entries
slug: finance-and-accounting
tags:
- PeopleSoft
- Finance
- Accounting
- General Ledger
- Budgeting
- Forecasting
tools:
- description: Retrieve general ledger journal entries.
  hints:
    openWorld: true
    readOnly: true
  name: list-journal-entries
- description: Retrieve accounts payable vouchers.
  hints:
    openWorld: true
    readOnly: true
  name: list-vouchers
- description: Retrieve accounts receivable items.
  hints:
    openWorld: true
    readOnly: true
  name: list-ar-items
- description: Retrieve expense reports.
  hints:
    openWorld: true
    readOnly: true
  name: list-expense-reports
- description: Retrieve budget definitions and data.
  hints:
    openWorld: true
    readOnly: true
  name: list-budgets
- description: Retrieve forecast data and projections.
  hints:
    openWorld: true
    readOnly: true
  name: list-forecasts
- description: Retrieve performance analytics reports.
  hints:
    openWorld: true
    readOnly: true
  name: list-analytics-reports
- description: Retrieve pending finance approval requests.
  hints:
    openWorld: true
    readOnly: true
  name: list-pending-approvals
- description: Approve, deny, or push back a finance approval request.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: process-approval
---
