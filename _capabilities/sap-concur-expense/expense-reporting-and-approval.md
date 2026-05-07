---
categories: []
consumed_apis: []
description: 'Unified workflow capability for the full expense report lifecycle in SAP Concur: creating reports, adding expense entries, submitting for approval, tracking approval status, and monitoring reimbursement payment batches. Designed for finance teams, expense managers, and ERP integration partners managing employee expense reimbursement end-to-end.'
layout: capability
name: SAP Concur Expense Reporting and Approval
operations:
- description: List expense reports with status filtering
  method: GET
  name: list-reports
  path: /v1/reports
- description: Create a new expense report
  method: POST
  name: create-report
  path: /v1/reports
- description: Get an expense report by ID
  method: GET
  name: get-report
  path: /v1/reports/{id}
- description: Update an expense report
  method: PUT
  name: update-report
  path: /v1/reports/{id}
- description: Delete a draft expense report
  method: DELETE
  name: delete-report
  path: /v1/reports/{id}
- description: List expense entries for a report
  method: GET
  name: list-entries
  path: /v1/entries
- description: Add an expense entry to a report
  method: POST
  name: create-entry
  path: /v1/entries
- description: Get an expense entry by ID
  method: GET
  name: get-entry
  path: /v1/entries/{id}
- description: Delete an expense entry
  method: DELETE
  name: delete-entry
  path: /v1/entries/{id}
- description: List payment batches for reimbursement
  method: GET
  name: list-payment-batches
  path: /v1/payment-batches
- description: List expense group configurations and policies
  method: GET
  name: list-configurations
  path: /v1/configurations
personas: []
provider_name: SAP Concur Expense
provider_slug: sap-concur-expense
search_terms:
- retrieve a specific expense entry with full details.
- create a new expense report
- reimbursement payment batch tracking
- create expense entry
- expense management
- get report
- add an expense entry to a report
- delete entry
- list expense group policy configurations showing available expense types, payment types, and approval workflow settings.
- delete a draft expense report
- list entries
- sap concur
- get expense entry
- approval workflow
- list expense entries for a report
- create report
- list reports
- list expense group configurations and policies
- delete report
- list payment batches for reimbursement
- list payment batches containing approved expense reports ready for employee reimbursement. useful for erp payment reconciliation.
- add a new expense line item to a draft expense report. requires report id, expense type code, transaction date, amount, and currency.
- sap
- delete an expense entry
- list all expense line items within a specific expense report. requires the reportid parameter.
- expense entry line items
- receipts
- list expense group configurations
- delete a draft expense report that has not been submitted.
- financial management
- single expense entry
- list expense entries
- get an expense report by id
- remove an expense entry from a draft expense report.
- delete expense entry
- delete expense report
- update an existing draft expense report's name or purpose.
- get expense report
- update report
- reimbursement
- expense group policy configuration
- update an expense report
- list configurations
- travel
- list expense reports
- retrieve full details of a specific expense report including status, totals, and owner information.
- list expense reports with optional filtering by approval status (a_pend, a_appr, a_file) or payment status (p_notp, p_proc, p_paid).
- create entry
- list payment batches
- get an expense entry by id
- reporting
- single expense report operations
- list expense reports with status filtering
- get entry
- create a new expense report for an employee. requires a report name and optional business purpose and policy id.
- expense report management
- update expense report
- create expense report
slug: expense-reporting-and-approval
source_filename: expense-reporting-and-approval.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SAP Concur Expense Reporting and Approval\n  description: 'Unified workflow capability for the full expense report lifecycle in SAP Concur: creating reports, adding\n    expense entries, submitting for approval, tracking approval status, and monitoring reimbursement payment batches. Designed\n    for finance teams, expense managers, and ERP integration partners managing employee expense reimbursement end-to-end.'\n  tags:\n  - Expense Management\n  - Financial Management\n  - Approval Workflow\n  - Reimbursement\n  - SAP Concur\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    CONCUR_OAUTH_TOKEN: CONCUR_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: concur-expense-report\n    baseUri: https://us.api.concursolutions.com/api/v3.0\n    description: SAP Concur Expense Report v3 API\n    authentication:\n      type: bearer\n      token: '{{CONCUR_OAUTH_TOKEN}}'\n    resources:\n\
  \    - name: expense-reports\n      path: /expense/reports\n      description: Expense report collection\n      operations:\n      - name: list-expense-reports\n        method: GET\n        description: List expense reports for the current user\n        inputParameters:\n        - name: approvalStatusCode\n          in: query\n          type: string\n          required: false\n          description: Filter by approval status code\n        - name: paymentStatusCode\n          in: query\n          type: string\n          required: false\n          description: Filter by payment status code\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of records to return (max 100)\n        - name: offset\n          in: query\n          type: string\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n \
  \         value: $.\n      - name: create-expense-report\n        method: POST\n        description: Create a new expense report\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Name: '{{tools.name}}'\n            Purpose: '{{tools.purpose}}'\n            PolicyID: '{{tools.policyId}}'\n    - name: expense-report-by-id\n      path: /expense/reports/{id}\n      description: Single expense report operations\n      operations:\n      - name: get-expense-report\n        method: GET\n        description: Retrieve a specific expense report by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The expense report ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-expense-report\n\
  \        method: PUT\n        description: Update an expense report\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The expense report ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Name: '{{tools.name}}'\n            Purpose: '{{tools.purpose}}'\n      - name: delete-expense-report\n        method: DELETE\n        description: Delete a draft expense report\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The expense report ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: expense-entries\n      path: /expense/entries\n      description: Expense entry collection\n   \
  \   operations:\n      - name: list-expense-entries\n        method: GET\n        description: List expense entries for a report\n        inputParameters:\n        - name: reportID\n          in: query\n          type: string\n          required: true\n          description: The expense report ID\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of records to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-expense-entry\n        method: POST\n        description: Create a new expense entry within a report\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            ReportID: '{{tools.reportId}}'\n            ExpenseTypeCode: '{{tools.expenseTypeCode}}'\n            TransactionDate:\
  \ '{{tools.transactionDate}}'\n            TransactionAmount: '{{tools.transactionAmount}}'\n            TransactionCurrencyCode: '{{tools.currencyCode}}'\n            BusinessPurpose: '{{tools.businessPurpose}}'\n            VendorDescription: '{{tools.vendor}}'\n    - name: expense-entry-by-id\n      path: /expense/entries/{id}\n      description: Single expense entry operations\n      operations:\n      - name: get-expense-entry\n        method: GET\n        description: Retrieve a specific expense entry by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The expense entry ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-expense-entry\n        method: DELETE\n        description: Delete an expense entry from a draft report\n        inputParameters:\n        - name: id\n          in: path\n\
  \          type: string\n          required: true\n          description: The expense entry ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payment-batches\n      path: /expense/paymentbatches\n      description: Payment batch management\n      operations:\n      - name: list-payment-batches\n        method: GET\n        description: List payment batches for reimbursement\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of records to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: expense-group-configs\n      path: /expense/expensegroupconfigurations\n      description: Expense policy configuration\n      operations:\n      - name: list-expense-group-configurations\n        method: GET\n     \
  \   description: List expense group policy configurations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: expense-reporting-api\n    description: Unified REST API for expense report lifecycle management and approval workflow.\n    resources:\n    - path: /v1/reports\n      name: reports\n      description: Expense report management\n      operations:\n      - method: GET\n        name: list-reports\n        description: List expense reports with status filtering\n        call: concur-expense-report.list-expense-reports\n        with:\n          approvalStatusCode: rest.approvalStatusCode\n          paymentStatusCode: rest.paymentStatusCode\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-report\n        description: Create a new expense report\n       \
  \ call: concur-expense-report.create-expense-report\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports/{id}\n      name: report-detail\n      description: Single expense report operations\n      operations:\n      - method: GET\n        name: get-report\n        description: Get an expense report by ID\n        call: concur-expense-report.get-expense-report\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-report\n        description: Update an expense report\n        call: concur-expense-report.update-expense-report\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-report\n        description: Delete a draft expense report\n        call: concur-expense-report.delete-expense-report\n        with:\n          id: rest.id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/entries\n      name: entries\n      description: Expense entry line items\n      operations:\n      - method: GET\n        name: list-entries\n        description: List expense entries for a report\n        call: concur-expense-report.list-expense-entries\n        with:\n          reportID: rest.reportID\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-entry\n        description: Add an expense entry to a report\n        call: concur-expense-report.create-expense-entry\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/entries/{id}\n      name: entry-detail\n      description: Single expense entry\n      operations:\n      - method: GET\n        name: get-entry\n        description: Get an expense entry by ID\n        call: concur-expense-report.get-expense-entry\n        with:\n          id: rest.id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-entry\n        description: Delete an expense entry\n        call: concur-expense-report.delete-expense-entry\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payment-batches\n      name: payment-batches\n      description: Reimbursement payment batch tracking\n      operations:\n      - method: GET\n        name: list-payment-batches\n        description: List payment batches for reimbursement\n        call: concur-expense-report.list-payment-batches\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/configurations\n      name: configurations\n      description: Expense group policy configuration\n      operations:\n      - method: GET\n        name: list-configurations\n        description: List expense group configurations and policies\n        call: concur-expense-report.list-expense-group-configurations\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: expense-reporting-mcp\n    transport: http\n    description: MCP server for AI-assisted expense report management and approval tracking.\n    tools:\n    - name: list-expense-reports\n      description: List expense reports with optional filtering by approval status (A_PEND, A_APPR, A_FILE) or payment status\n        (P_NOTP, P_PROC, P_PAID).\n      hints:\n        readOnly: true\n        openWorld: true\n      call: concur-expense-report.list-expense-reports\n      with:\n        approvalStatusCode: tools.approvalStatusCode\n        paymentStatusCode: tools.paymentStatusCode\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-expense-report\n      description: Retrieve full details of a specific expense report including status, totals, and owner information.\n      hints:\n        readOnly: true\n        openWorld:\
  \ false\n      call: concur-expense-report.get-expense-report\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-expense-report\n      description: Create a new expense report for an employee. Requires a report name and optional business purpose and policy\n        ID.\n      hints:\n        readOnly: false\n        destructive: false\n      call: concur-expense-report.create-expense-report\n      with:\n        name: tools.name\n        purpose: tools.purpose\n        policyId: tools.policyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-expense-report\n      description: Update an existing draft expense report's name or purpose.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: concur-expense-report.update-expense-report\n      with:\n        id: tools.id\n        name: tools.name\n        purpose: tools.purpose\n  \
  \    outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-expense-report\n      description: Delete a draft expense report that has not been submitted.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: concur-expense-report.delete-expense-report\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-expense-entries\n      description: List all expense line items within a specific expense report. Requires the reportID parameter.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: concur-expense-report.list-expense-entries\n      with:\n        reportID: tools.reportID\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-expense-entry\n      description: Retrieve a specific expense entry with full details.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: concur-expense-report.get-expense-entry\n\
  \      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-expense-entry\n      description: Add a new expense line item to a draft expense report. Requires report ID, expense type code, transaction\n        date, amount, and currency.\n      hints:\n        readOnly: false\n        destructive: false\n      call: concur-expense-report.create-expense-entry\n      with:\n        reportId: tools.reportId\n        expenseTypeCode: tools.expenseTypeCode\n        transactionDate: tools.transactionDate\n        transactionAmount: tools.transactionAmount\n        currencyCode: tools.currencyCode\n        businessPurpose: tools.businessPurpose\n        vendor: tools.vendor\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-expense-entry\n      description: Remove an expense entry from a draft expense report.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent:\
  \ true\n      call: concur-expense-report.delete-expense-entry\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-payment-batches\n      description: List payment batches containing approved expense reports ready for employee reimbursement. Useful for ERP\n        payment reconciliation.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: concur-expense-report.list-payment-batches\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-expense-group-configurations\n      description: List expense group policy configurations showing available expense types, payment types, and approval workflow\n        settings.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: concur-expense-report.list-expense-group-configurations\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sap-concur-expense/refs/heads/main/capabilities/expense-reporting-and-approval.yaml
tags:
- Expense Management
- Financial Management
- Approval Workflow
- Reimbursement
- SAP Concur
tools:
- description: List expense reports with optional filtering by approval status (A_PEND, A_APPR, A_FILE) or payment status (P_NOTP, P_PROC, P_PAID).
  hints:
    openWorld: true
    readOnly: true
  name: list-expense-reports
- description: Retrieve full details of a specific expense report including status, totals, and owner information.
  hints:
    openWorld: false
    readOnly: true
  name: get-expense-report
- description: Create a new expense report for an employee. Requires a report name and optional business purpose and policy ID.
  hints:
    destructive: false
    readOnly: false
  name: create-expense-report
- description: Update an existing draft expense report's name or purpose.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-expense-report
- description: Delete a draft expense report that has not been submitted.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-expense-report
- description: List all expense line items within a specific expense report. Requires the reportID parameter.
  hints:
    openWorld: true
    readOnly: true
  name: list-expense-entries
- description: Retrieve a specific expense entry with full details.
  hints:
    openWorld: false
    readOnly: true
  name: get-expense-entry
- description: Add a new expense line item to a draft expense report. Requires report ID, expense type code, transaction date, amount, and currency.
  hints:
    destructive: false
    readOnly: false
  name: create-expense-entry
- description: Remove an expense entry from a draft expense report.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-expense-entry
- description: List payment batches containing approved expense reports ready for employee reimbursement. Useful for ERP payment reconciliation.
  hints:
    openWorld: true
    readOnly: true
  name: list-payment-batches
- description: List expense group policy configurations showing available expense types, payment types, and approval workflow settings.
  hints:
    openWorld: true
    readOnly: true
  name: list-expense-group-configurations
---
