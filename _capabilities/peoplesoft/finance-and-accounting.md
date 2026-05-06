---
categories: []
consumed_apis: []
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
- list journal entries
- supply chain management
- retrieve performance analytics reports.
- list pending approvals
- general ledger journal entries
- peopletools platform services.
- peoplesoft
- process approval
- finance
- list vouchers
- list expense reports
- accounts receivable items
- list forecasts
- campus solutions.
- accounting
- retrieve budget definitions and data.
- retrieve general ledger journal entries.
- retrieve accounts receivable items.
- approve, deny, or push back a finance approval request.
- financial and supply chain management.
- individual approval operations
- human capital management.
- forecast data and projections
- forecasting
- list ar items
- erp
- general ledger
- financial management
- expense reports
- crm
- hcm
- retrieve accounts payable vouchers.
- finance approval requests
- performance analytics reports
- campus solutions
- retrieve forecast data and projections.
- budgeting
- list analytics reports
- enterprise software
- accounts payable vouchers
- retrieve expense reports.
- budget definitions and data
- list budgets
- retrieve pending finance approval requests.
slug: finance-and-accounting
source_filename: finance-and-accounting.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: PeopleSoft Finance And Accounting\n  description: Unified workflow for finance controllers combining general ledger, accounts payable, accounts receivable, expenses,\n    budgeting, forecasting, analytics, and approval workflows across PeopleSoft Financials, EPM, and Approval Workflow Engine\n    APIs.\n  tags:\n  - PeopleSoft\n  - Finance\n  - Accounting\n  - General Ledger\n  - Budgeting\n  - Forecasting\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    PEOPLESOFT_USERNAME: PEOPLESOFT_USERNAME\n    PEOPLESOFT_PASSWORD: PEOPLESOFT_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: financials\n    baseUri: https://${PEOPLESOFT_HOST}:${PEOPLESOFT_PORT}/psft/api/financials/v1\n    description: PeopleSoft Financials API\n    authentication:\n      type: basic\n      username: '{{PEOPLESOFT_USERNAME}}'\n      password: '{{PEOPLESOFT_PASSWORD}}'\n    resources:\n    - name: general-ledger\n\
  \      path: /gl\n      description: General ledger operations\n      operations:\n      - name: list-journal-entries\n        method: GET\n        description: Retrieve general ledger journal entries.\n        inputParameters:\n        - name: businessUnit\n          in: query\n          type: string\n          required: false\n          description: Business unit filter\n        - name: fromDate\n          in: query\n          type: string\n          required: false\n          description: Start date filter\n        - name: toDate\n          in: query\n          type: string\n          required: false\n          description: End date filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-payable\n      path: /ap\n      description: Accounts payable operations\n      operations:\n      - name: list-vouchers\n        method: GET\n        description: Retrieve accounts payable vouchers.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-receivable\n      path: /ar\n      description: Accounts receivable operations\n      operations:\n      - name: list-ar-items\n        method: GET\n        description: Retrieve accounts receivable items.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: expenses\n      path: /expenses\n      description: Expense management operations\n      operations:\n      - name: list-expense-reports\n        method: GET\n        description: Retrieve expense reports.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: epm\n    baseUri: https://${PEOPLESOFT_HOST}:${PEOPLESOFT_PORT}/psft/api/epm/v1\n    description: PeopleSoft Enterprise Performance Management\
  \ API\n    authentication:\n      type: basic\n      username: '{{PEOPLESOFT_USERNAME}}'\n      password: '{{PEOPLESOFT_PASSWORD}}'\n    resources:\n    - name: budgets\n      path: /budgets\n      description: Budget management operations\n      operations:\n      - name: list-budgets\n        method: GET\n        description: Retrieve budget definitions and data.\n        inputParameters:\n        - name: fiscalYear\n          in: query\n          type: string\n          required: false\n          description: Fiscal year filter\n        - name: businessUnit\n          in: query\n          type: string\n          required: false\n          description: Business unit filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: forecasts\n      path: /forecasts\n      description: Forecasting operations\n      operations:\n      - name: list-forecasts\n        method: GET\n        description: Retrieve\
  \ forecast data and projections.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analytics\n      path: /analytics\n      description: Analytics and reporting operations\n      operations:\n      - name: list-analytics-reports\n        method: GET\n        description: Retrieve performance analytics reports.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: approval-workflow\n    baseUri: https://${PEOPLESOFT_HOST}:${PEOPLESOFT_PORT}/psft/api/approvals/v1\n    description: PeopleSoft Approval Workflow Engine API\n    authentication:\n      type: basic\n      username: '{{PEOPLESOFT_USERNAME}}'\n      password: '{{PEOPLESOFT_PASSWORD}}'\n    resources:\n    - name: approvals\n      path: /approvals\n      description: Approval workflow operations\n      operations:\n      - name: list-pending-approvals\n\
  \        method: GET\n        description: Retrieve a list of pending approval requests for the current user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: process-approval\n        method: PUT\n        description: Approve, deny, or push back an approval request.\n        inputParameters:\n        - name: approvalId\n          in: path\n          type: string\n          required: true\n          description: The approval request identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            action: '{{tools.action}}'\n            comments: '{{tools.comments}}'\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: finance-api\n    description: Unified REST API for PeopleSoft finance and accounting workflows.\n    resources:\n    - path: /v1/journal-entries\n\
  \      name: journal-entries\n      description: General ledger journal entries\n      operations:\n      - method: GET\n        name: list-journal-entries\n        description: Retrieve general ledger journal entries.\n        call: financials.list-journal-entries\n        with:\n          businessUnit: rest.businessUnit\n          fromDate: rest.fromDate\n          toDate: rest.toDate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vouchers\n      name: vouchers\n      description: Accounts payable vouchers\n      operations:\n      - method: GET\n        name: list-vouchers\n        description: Retrieve accounts payable vouchers.\n        call: financials.list-vouchers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/receivable-items\n      name: receivable-items\n      description: Accounts receivable items\n      operations:\n      - method: GET\n        name: list-ar-items\n        description:\
  \ Retrieve accounts receivable items.\n        call: financials.list-ar-items\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/expense-reports\n      name: expense-reports\n      description: Expense reports\n      operations:\n      - method: GET\n        name: list-expense-reports\n        description: Retrieve expense reports.\n        call: financials.list-expense-reports\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/budgets\n      name: budgets\n      description: Budget definitions and data\n      operations:\n      - method: GET\n        name: list-budgets\n        description: Retrieve budget definitions and data.\n        call: epm.list-budgets\n        with:\n          fiscalYear: rest.fiscalYear\n          businessUnit: rest.businessUnit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/forecasts\n      name: forecasts\n      description: Forecast data\
  \ and projections\n      operations:\n      - method: GET\n        name: list-forecasts\n        description: Retrieve forecast data and projections.\n        call: epm.list-forecasts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/analytics-reports\n      name: analytics-reports\n      description: Performance analytics reports\n      operations:\n      - method: GET\n        name: list-analytics-reports\n        description: Retrieve performance analytics reports.\n        call: epm.list-analytics-reports\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/approvals\n      name: approvals\n      description: Finance approval requests\n      operations:\n      - method: GET\n        name: list-pending-approvals\n        description: Retrieve pending finance approval requests.\n        call: approval-workflow.list-pending-approvals\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /v1/approvals/{approvalId}\n      name: approval-detail\n      description: Individual approval operations\n      operations:\n      - method: PUT\n        name: process-approval\n        description: Approve, deny, or push back a finance approval request.\n        call: approval-workflow.process-approval\n        with:\n          approvalId: rest.approvalId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: finance-mcp\n    transport: http\n    description: MCP server for AI-assisted PeopleSoft finance and accounting workflows.\n    tools:\n    - name: list-journal-entries\n      description: Retrieve general ledger journal entries.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: financials.list-journal-entries\n      with:\n        businessUnit: tools.businessUnit\n        fromDate: tools.fromDate\n        toDate: tools.toDate\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: list-vouchers\n      description: Retrieve accounts payable vouchers.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: financials.list-vouchers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-ar-items\n      description: Retrieve accounts receivable items.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: financials.list-ar-items\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-expense-reports\n      description: Retrieve expense reports.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: financials.list-expense-reports\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-budgets\n      description: Retrieve budget definitions and data.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: epm.list-budgets\n      with:\n        fiscalYear: tools.fiscalYear\n\
  \        businessUnit: tools.businessUnit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-forecasts\n      description: Retrieve forecast data and projections.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: epm.list-forecasts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-analytics-reports\n      description: Retrieve performance analytics reports.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: epm.list-analytics-reports\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-pending-approvals\n      description: Retrieve pending finance approval requests.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: approval-workflow.list-pending-approvals\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: process-approval\n      description: Approve, deny, or push back a finance\
  \ approval request.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: approval-workflow.process-approval\n      with:\n        approvalId: tools.approvalId\n        action: tools.action\n        comments: tools.comments\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
