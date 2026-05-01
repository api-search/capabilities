---
api_specs:
- filename: financials.yml
  format: yaml
  label: financials
  slug: financials
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/openapi/financials.yml
- filename: enterprise-performance-management.yml
  format: yaml
  label: epm
  slug: epm
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/openapi/enterprise-performance-management.yml
- filename: approval-workflow-engine.yml
  format: yaml
  label: approval-workflow
  slug: approval-workflow
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/openapi/approval-workflow-engine.yml
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
- finance
- finance approval requests
- crm
- supply chain management
- retrieve general ledger journal entries.
- retrieve budget definitions and data.
- hcm
- forecast data and projections
- list pending approvals
- budgeting
- budget definitions and data
- list ar items
- performance analytics reports
- campus solutions
- accounting
- peoplesoft
- list journal entries
- list expense reports
- list budgets
- list analytics reports
- peopletools platform services.
- expense reports
- approve, deny, or push back a finance approval request.
- retrieve performance analytics reports.
- list vouchers
- forecasting
- retrieve forecast data and projections.
- general ledger
- list forecasts
- retrieve accounts payable vouchers.
- campus solutions.
- accounts payable vouchers
- process approval
- retrieve accounts receivable items.
- retrieve expense reports.
- enterprise software
- retrieve pending finance approval requests.
- human capital management.
- accounts receivable items
- financial management
- general ledger journal entries
- financial and supply chain management.
- individual approval operations
- erp
slug: finance-and-accounting
source_filename: finance-and-accounting.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"PeopleSoft Finance And Accounting\"\n  description: \"Unified workflow for finance controllers combining general ledger, accounts payable, accounts receivable, expenses, budgeting, forecasting, analytics, and approval workflows across PeopleSoft Financials, EPM, and Approval Workflow Engine APIs.\"\n  tags:\n    - PeopleSoft\n    - Finance\n    - Accounting\n    - General Ledger\n    - Budgeting\n    - Forecasting\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      PEOPLESOFT_USERNAME: PEOPLESOFT_USERNAME\n      PEOPLESOFT_PASSWORD: PEOPLESOFT_PASSWORD\n\ncapability:\n  consumes:\n    - import: financials\n      location: ./shared/financials.yaml\n    - import: epm\n      location: ./shared/enterprise-performance-management.yaml\n    - import: approval-workflow\n      location: ./shared/approval-workflow-engine.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace:\
  \ finance-api\n      description: \"Unified REST API for PeopleSoft finance and accounting workflows.\"\n      resources:\n        - path: /v1/journal-entries\n          name: journal-entries\n          description: \"General ledger journal entries\"\n          operations:\n            - method: GET\n              name: list-journal-entries\n              description: \"Retrieve general ledger journal entries.\"\n              call: \"financials.list-journal-entries\"\n              with:\n                businessUnit: \"rest.businessUnit\"\n                fromDate: \"rest.fromDate\"\n                toDate: \"rest.toDate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/vouchers\n          name: vouchers\n          description: \"Accounts payable vouchers\"\n          operations:\n            - method: GET\n              name: list-vouchers\n              description: \"Retrieve accounts payable vouchers.\"\n  \
  \            call: \"financials.list-vouchers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/receivable-items\n          name: receivable-items\n          description: \"Accounts receivable items\"\n          operations:\n            - method: GET\n              name: list-ar-items\n              description: \"Retrieve accounts receivable items.\"\n              call: \"financials.list-ar-items\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/expense-reports\n          name: expense-reports\n          description: \"Expense reports\"\n          operations:\n            - method: GET\n              name: list-expense-reports\n              description: \"Retrieve expense reports.\"\n              call: \"financials.list-expense-reports\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\
  \        - path: /v1/budgets\n          name: budgets\n          description: \"Budget definitions and data\"\n          operations:\n            - method: GET\n              name: list-budgets\n              description: \"Retrieve budget definitions and data.\"\n              call: \"epm.list-budgets\"\n              with:\n                fiscalYear: \"rest.fiscalYear\"\n                businessUnit: \"rest.businessUnit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/forecasts\n          name: forecasts\n          description: \"Forecast data and projections\"\n          operations:\n            - method: GET\n              name: list-forecasts\n              description: \"Retrieve forecast data and projections.\"\n              call: \"epm.list-forecasts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/analytics-reports\n          name:\
  \ analytics-reports\n          description: \"Performance analytics reports\"\n          operations:\n            - method: GET\n              name: list-analytics-reports\n              description: \"Retrieve performance analytics reports.\"\n              call: \"epm.list-analytics-reports\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/approvals\n          name: approvals\n          description: \"Finance approval requests\"\n          operations:\n            - method: GET\n              name: list-pending-approvals\n              description: \"Retrieve pending finance approval requests.\"\n              call: \"approval-workflow.list-pending-approvals\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/approvals/{approvalId}\n          name: approval-detail\n          description: \"Individual approval operations\"\n          operations:\n\
  \            - method: PUT\n              name: process-approval\n              description: \"Approve, deny, or push back a finance approval request.\"\n              call: \"approval-workflow.process-approval\"\n              with:\n                approvalId: \"rest.approvalId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: finance-mcp\n      transport: http\n      description: \"MCP server for AI-assisted PeopleSoft finance and accounting workflows.\"\n      tools:\n        - name: list-journal-entries\n          description: \"Retrieve general ledger journal entries.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"financials.list-journal-entries\"\n          with:\n            businessUnit: \"tools.businessUnit\"\n            fromDate: \"tools.fromDate\"\n            toDate: \"tools.toDate\"\n          outputParameters:\n    \
  \        - type: object\n              mapping: \"$.\"\n        - name: list-vouchers\n          description: \"Retrieve accounts payable vouchers.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"financials.list-vouchers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-ar-items\n          description: \"Retrieve accounts receivable items.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"financials.list-ar-items\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-expense-reports\n          description: \"Retrieve expense reports.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"financials.list-expense-reports\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-budgets\n\
  \          description: \"Retrieve budget definitions and data.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"epm.list-budgets\"\n          with:\n            fiscalYear: \"tools.fiscalYear\"\n            businessUnit: \"tools.businessUnit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-forecasts\n          description: \"Retrieve forecast data and projections.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"epm.list-forecasts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-analytics-reports\n          description: \"Retrieve performance analytics reports.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"epm.list-analytics-reports\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\
  \n        - name: list-pending-approvals\n          description: \"Retrieve pending finance approval requests.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"approval-workflow.list-pending-approvals\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: process-approval\n          description: \"Approve, deny, or push back a finance approval request.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"approval-workflow.process-approval\"\n          with:\n            approvalId: \"tools.approvalId\"\n            action: \"tools.action\"\n            comments: \"tools.comments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/capabilities/finance-and-accounting.yaml
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
