---
categories: []
consumed_apis: []
description: Unified spend management workflow combining expense, travel, and invoice APIs for finance teams managing employee spend.
layout: capability
name: SAP Concur Spend Management
operations:
- description: List expense reports
  method: GET
  name: list-reports
  path: /v1/reports
personas: []
provider_name: SAP Concur
provider_slug: concur
search_terms:
- list expense reports for a user
- spend management
- expense reports
- create a new expense report
- finance and accounting staff managing expense and invoice processing
- managers approving expense reports and invoices
- Finance Team
- expense management
- travel
- invoice
- sap
- unified spend management combining expense and invoice workflows
- sap concur
- create expense report
- list expense reports
- finance
- Approver
- list reports
slug: spend-management
source_filename: spend-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SAP Concur Spend Management\n  description: Unified spend management workflow combining expense, travel, and invoice APIs for finance teams managing employee\n    spend.\n  tags:\n  - Expense Management\n  - SAP Concur\n  - Spend Management\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    CONCUR_ACCESS_TOKEN: CONCUR_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: concur-expense\n    baseUri: https://us.api.concursolutions.com\n    description: SAP Concur Expense API v4\n    authentication:\n      type: bearer\n      token: '{{CONCUR_ACCESS_TOKEN}}'\n    resources:\n    - name: expense-reports\n      path: /expensereports/v4\n      description: Expense report management\n      operations:\n      - name: get-expense-reports\n        method: GET\n        description: Get expense reports for a user\n        inputParameters:\n        - name: userId\n          in: path\n      \
  \    type: string\n          required: true\n          description: User ID\n        - name: contextType\n          in: path\n          type: string\n          required: true\n          description: Context type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-expense-report\n        method: POST\n        description: Create a new expense report\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            reportName: '{{tools.reportName}}'\n            currencyCode: '{{tools.currencyCode}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: spend-management-api\n    description: Unified REST API for\
  \ SAP Concur spend management.\n    resources:\n    - path: /v1/reports\n      name: expense-reports\n      description: Expense reports\n      operations:\n      - method: GET\n        name: list-reports\n        description: List expense reports\n        call: concur-expense.get-expense-reports\n  - type: mcp\n    port: 9090\n    namespace: spend-management-mcp\n    transport: http\n    description: MCP server for AI-assisted spend management.\n    tools:\n    - name: list-expense-reports\n      description: List expense reports for a user\n      hints:\n        readOnly: true\n        openWorld: true\n      call: concur-expense.get-expense-reports\n    - name: create-expense-report\n      description: Create a new expense report\n      hints:\n        readOnly: false\n      call: concur-expense.create-expense-report\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/concur/refs/heads/main/capabilities/spend-management.yaml
tags:
- Expense Management
- SAP Concur
- Spend Management
tools:
- description: List expense reports for a user
  hints:
    openWorld: true
    readOnly: true
  name: list-expense-reports
- description: Create a new expense report
  hints:
    readOnly: false
  name: create-expense-report
---
