---
categories: []
consumed_apis:
- concur-expense
description: Unified expense management workflow combining report creation, expense tracking, approval workflows, and allocation management. Used by finance teams, approvers, and employees to manage the full expense lifecycle.
layout: capability
name: SAP Concur Expense Management
operations:
- description: Create a new expense report.
  method: POST
  name: create-report
  path: /v1/reports
- description: Get reports pending approval.
  method: GET
  name: get-reports-to-approve
  path: /v1/reports
- description: Retrieve a report.
  method: GET
  name: get-report
  path: /v1/reports/{reportId}
- description: Submit for approval.
  method: POST
  name: submit-report
  path: /v1/reports/{reportId}/submit
- description: Approve an expense report.
  method: POST
  name: approve-report
  path: /v1/reports/{reportId}/approve
- description: Get expenses for a report.
  method: GET
  name: get-expenses
  path: /v1/expenses
- description: Get report comments.
  method: GET
  name: get-comments
  path: /v1/comments
- description: Add a report comment.
  method: POST
  name: create-comment
  path: /v1/comments
personas: []
provider_name: SAP Concur
provider_slug: sap-concur
search_terms:
- list expense reports pending approval.
- sap concur
- expense entry operations.
- individual report operations.
- approval workflows
- get allocations
- get expense allocations.
- get report
- create report
- submit report
- get a single expense entry.
- get expense
- approve report
- report comments.
- get reports to approve
- get comments on an expense report.
- get expenses
- create report comment
- delete report
- recall a submitted expense report.
- get report comments
- get expenses for a report.
- submit for approval.
- update report
- retrieve an expense report by id.
- add a comment to an expense report.
- invoice management
- financial services
- expense report lifecycle management.
- retrieve a report.
- approve an expense report.
- expense management
- submit an expense report for approval.
- send back report
- approve report.
- travel management
- get comments
- submit report.
- create comment
- create a new expense report.
- get expense entries for a report.
- business travel
- delete an unsubmitted expense report.
- recall report
- get report comments.
- get reports pending approval.
- update an unsubmitted expense report.
- send back an expense report for revision.
- add a report comment.
slug: expense-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SAP Concur Expense Management\"\n  description: \"Unified expense management workflow combining report creation, expense tracking, approval workflows, and allocation management. Used by finance teams, approvers, and employees to manage the full expense lifecycle.\"\n  tags:\n    - SAP Concur\n    - Expense Management\n    - Approval Workflows\n    - Financial Services\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      CONCUR_ACCESS_TOKEN: CONCUR_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: concur-expense\n      location: ./shared/concur-expense.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: concur-expense-mgmt-api\n      description: \"Unified REST API for SAP Concur expense management workflows.\"\n      resources:\n        - path: /v1/reports\n          name: reports\n          description: \"Expense report lifecycle management.\"\n     \
  \     operations:\n            - method: POST\n              name: create-report\n              description: \"Create a new expense report.\"\n              call: \"concur-expense.create-report\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-reports-to-approve\n              description: \"Get reports pending approval.\"\n              call: \"concur-expense.get-reports-to-approve\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reports/{reportId}\n          name: report-detail\n          description: \"Individual report operations.\"\n          operations:\n            - method: GET\n              name: get-report\n              description: \"Retrieve a report.\"\n              call: \"concur-expense.get-report\"\n              with:\n                reportId: \"rest.reportId\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reports/{reportId}/submit\n          name: submit\n          description: \"Submit report.\"\n          operations:\n            - method: POST\n              name: submit-report\n              description: \"Submit for approval.\"\n              call: \"concur-expense.submit-report\"\n              with:\n                reportId: \"rest.reportId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reports/{reportId}/approve\n          name: approve\n          description: \"Approve report.\"\n          operations:\n            - method: POST\n              name: approve-report\n              description: \"Approve an expense report.\"\n              call: \"concur-expense.approve-report\"\n              with:\n                reportId: \"rest.reportId\"\n              outputParameters:\n                - type: object\n         \
  \         mapping: \"$.\"\n        - path: /v1/expenses\n          name: expenses\n          description: \"Expense entry operations.\"\n          operations:\n            - method: GET\n              name: get-expenses\n              description: \"Get expenses for a report.\"\n              call: \"concur-expense.get-expenses\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/comments\n          name: comments\n          description: \"Report comments.\"\n          operations:\n            - method: GET\n              name: get-comments\n              description: \"Get report comments.\"\n              call: \"concur-expense.get-report-comments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-comment\n              description: \"Add a report comment.\"\n              call: \"concur-expense.create-report-comment\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: concur-expense-mgmt-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SAP Concur expense management.\"\n      tools:\n        - name: create-report\n          description: \"Create a new expense report.\"\n          hints:\n            readOnly: false\n          call: \"concur-expense.create-report\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-report\n          description: \"Retrieve an expense report by ID.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"concur-expense.get-report\"\n          with:\n            reportId: \"tools.reportId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-report\n          description: \"Update an unsubmitted\
  \ expense report.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"concur-expense.update-report\"\n          with:\n            reportId: \"tools.reportId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-report\n          description: \"Delete an unsubmitted expense report.\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"concur-expense.delete-report\"\n          with:\n            reportId: \"tools.reportId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-reports-to-approve\n          description: \"List expense reports pending approval.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"concur-expense.get-reports-to-approve\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n  \
  \      - name: submit-report\n          description: \"Submit an expense report for approval.\"\n          hints:\n            readOnly: false\n          call: \"concur-expense.submit-report\"\n          with:\n            reportId: \"tools.reportId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: approve-report\n          description: \"Approve an expense report.\"\n          hints:\n            readOnly: false\n          call: \"concur-expense.approve-report\"\n          with:\n            reportId: \"tools.reportId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-back-report\n          description: \"Send back an expense report for revision.\"\n          hints:\n            readOnly: false\n          call: \"concur-expense.send-back-report\"\n          with:\n            reportId: \"tools.reportId\"\n          outputParameters:\n            - type: object\n      \
  \        mapping: \"$.\"\n        - name: recall-report\n          description: \"Recall a submitted expense report.\"\n          hints:\n            readOnly: false\n          call: \"concur-expense.recall-report\"\n          with:\n            reportId: \"tools.reportId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-expenses\n          description: \"Get expense entries for a report.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"concur-expense.get-expenses\"\n          with:\n            reportId: \"tools.reportId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-expense\n          description: \"Get a single expense entry.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"concur-expense.get-expense\"\n          with:\n            expenseId: \"tools.expenseId\"\n \
  \         outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-allocations\n          description: \"Get expense allocations.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"concur-expense.get-allocations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-report-comments\n          description: \"Get comments on an expense report.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"concur-expense.get-report-comments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-report-comment\n          description: \"Add a comment to an expense report.\"\n          hints:\n            readOnly: false\n          call: \"concur-expense.create-report-comment\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sap-concur/refs/heads/main/capabilities/expense-management.yaml
tags:
- SAP Concur
- Expense Management
- Approval Workflows
- Financial Services
tools:
- description: Create a new expense report.
  hints:
    readOnly: false
  name: create-report
- description: Retrieve an expense report by ID.
  hints:
    idempotent: true
    readOnly: true
  name: get-report
- description: Update an unsubmitted expense report.
  hints:
    idempotent: true
    readOnly: false
  name: update-report
- description: Delete an unsubmitted expense report.
  hints:
    destructive: true
    readOnly: false
  name: delete-report
- description: List expense reports pending approval.
  hints:
    idempotent: true
    readOnly: true
  name: get-reports-to-approve
- description: Submit an expense report for approval.
  hints:
    readOnly: false
  name: submit-report
- description: Approve an expense report.
  hints:
    readOnly: false
  name: approve-report
- description: Send back an expense report for revision.
  hints:
    readOnly: false
  name: send-back-report
- description: Recall a submitted expense report.
  hints:
    readOnly: false
  name: recall-report
- description: Get expense entries for a report.
  hints:
    idempotent: true
    readOnly: true
  name: get-expenses
- description: Get a single expense entry.
  hints:
    idempotent: true
    readOnly: true
  name: get-expense
- description: Get expense allocations.
  hints:
    idempotent: true
    readOnly: true
  name: get-allocations
- description: Get comments on an expense report.
  hints:
    idempotent: true
    readOnly: true
  name: get-report-comments
- description: Add a comment to an expense report.
  hints:
    readOnly: false
  name: create-report-comment
---
