---
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
- update an unsubmitted expense report.
- individual report operations.
- get expense allocations.
- business travel
- get comments on an expense report.
- financial services
- list expense reports pending approval.
- send back report
- create report comment
- delete report
- approve report
- get report
- get expense
- sap concur
- approve report.
- submit an expense report for approval.
- get reports to approve
- approve an expense report.
- update report
- approval workflows
- create a new expense report.
- get comments
- get expense entries for a report.
- submit report.
- retrieve a report.
- get a single expense entry.
- submit report
- retrieve an expense report by id.
- add a comment to an expense report.
- create report
- submit for approval.
- expense entry operations.
- delete an unsubmitted expense report.
- get report comments
- invoice management
- create comment
- get allocations
- get expenses
- report comments.
- get report comments.
- expense management
- get expenses for a report.
- expense report lifecycle management.
- send back an expense report for revision.
- add a report comment.
- travel management
- recall report
- recall a submitted expense report.
- get reports pending approval.
slug: expense-management
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
