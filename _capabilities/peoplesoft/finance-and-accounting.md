---
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
- approve, deny, or push back a finance approval request.
- list vouchers
- budget definitions and data
- list budgets
- list forecasts
- process approval
- general ledger journal entries
- finance
- accounts payable vouchers
- accounts receivable items
- retrieve budget definitions and data.
- list analytics reports
- human capital management.
- campus solutions
- general ledger
- financial and supply chain management.
- list journal entries
- retrieve forecast data and projections.
- accounting
- forecast data and projections
- forecasting
- performance analytics reports
- retrieve general ledger journal entries.
- finance approval requests
- peopletools platform services.
- hcm
- expense reports
- crm
- list ar items
- list pending approvals
- enterprise software
- retrieve expense reports.
- budgeting
- individual approval operations
- retrieve accounts receivable items.
- retrieve performance analytics reports.
- list expense reports
- peoplesoft
- retrieve pending finance approval requests.
- campus solutions.
- supply chain management
- erp
- financial management
- retrieve accounts payable vouchers.
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
