---
categories: []
consumed_apis:
- concur-receipt-capture
description: Workflow capability for mobile expense capture and receipt management in SAP Concur. Enables on-the-go expense logging via quick expenses and receipt image capture before formal report submission. Designed for field employees, mobile users, and receipt processing integrations that capture expenses at the point of transaction.
layout: capability
name: SAP Concur Expense Capture and Receipt Management
operations:
- description: List unassigned quick expenses
  method: GET
  name: list-quick-expenses
  path: /v1/quick-expenses
- description: Capture a new quick expense
  method: POST
  name: create-quick-expense
  path: /v1/quick-expenses
- description: Get a quick expense by ID
  method: GET
  name: get-quick-expense
  path: /v1/quick-expenses/{id}
- description: Delete a quick expense
  method: DELETE
  name: delete-quick-expense
  path: /v1/quick-expenses/{id}
- description: List receipt images
  method: GET
  name: list-receipts
  path: /v1/receipts
- description: Get receipt image URL
  method: GET
  name: get-receipt
  path: /v1/receipts/{id}
- description: Delete a receipt image
  method: DELETE
  name: delete-receipt
  path: /v1/receipts/{id}
personas: []
provider_name: SAP Concur Expense
provider_slug: sap-concur-expense
search_terms:
- delete a quick expense that is no longer needed.
- list unassigned quick expenses
- get receipt image
- travel
- sap
- delete receipt image
- capture a new quick expense
- get details of a specific quick expense by id.
- sap concur
- receipt image management
- delete quick expense
- list receipts
- capture a new quick expense on-the-go. provide the expense type, date, amount, currency, and optional vendor and comment. the expense can later be promoted to a full expense report entry.
- list quick expenses
- retrieve the download url for a specific receipt image. the url is temporary and expires after a short period.
- get quick expense
- quick expense capture without a formal report
- list receipt images attached to expense entries. optionally filter by entry id to find receipts for a specific expense.
- delete receipt
- expense management
- delete a receipt image
- delete a quick expense
- create quick expense
- get receipt image url
- single quick expense
- expense capture
- list all quick expenses the user has captured that have not yet been assigned to a formal expense report.
- mobile
- receipts
- list receipt images
- single receipt image
- financial management
- reporting
- get a quick expense by id
- delete a receipt image that was uploaded in error.
- reimbursement
- get receipt
slug: expense-capture-and-receipts
source_filename: expense-capture-and-receipts.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SAP Concur Expense Capture and Receipt Management\"\n  description: >-\n    Workflow capability for mobile expense capture and receipt management in\n    SAP Concur. Enables on-the-go expense logging via quick expenses and receipt\n    image capture before formal report submission. Designed for field employees,\n    mobile users, and receipt processing integrations that capture expenses\n    at the point of transaction.\n  tags:\n    - Expense Capture\n    - Mobile\n    - Receipts\n    - SAP Concur\n    - Travel\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      CONCUR_OAUTH_TOKEN: CONCUR_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: concur-receipt-capture\n      location: ./shared/receipt-capture.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: expense-capture-api\n      description: \"Unified REST API for on-the-go expense capture and receipt\
  \ image management.\"\n      resources:\n        - path: /v1/quick-expenses\n          name: quick-expenses\n          description: \"Quick expense capture without a formal report\"\n          operations:\n            - method: GET\n              name: list-quick-expenses\n              description: \"List unassigned quick expenses\"\n              call: \"concur-receipt-capture.list-quick-expenses\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-quick-expense\n              description: \"Capture a new quick expense\"\n              call: \"concur-receipt-capture.create-quick-expense\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/quick-expenses/{id}\n          name: quick-expense-detail\n          description: \"Single quick expense\"\n          operations:\n            - method: GET\n              name:\
  \ get-quick-expense\n              description: \"Get a quick expense by ID\"\n              call: \"concur-receipt-capture.get-quick-expense\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-quick-expense\n              description: \"Delete a quick expense\"\n              call: \"concur-receipt-capture.delete-quick-expense\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/receipts\n          name: receipts\n          description: \"Receipt image management\"\n          operations:\n            - method: GET\n              name: list-receipts\n              description: \"List receipt images\"\n              call: \"concur-receipt-capture.list-receipt-images\"\n              outputParameters:\n   \
  \             - type: object\n                  mapping: \"$.\"\n        - path: /v1/receipts/{id}\n          name: receipt-detail\n          description: \"Single receipt image\"\n          operations:\n            - method: GET\n              name: get-receipt\n              description: \"Get receipt image URL\"\n              call: \"concur-receipt-capture.get-receipt-image\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-receipt\n              description: \"Delete a receipt image\"\n              call: \"concur-receipt-capture.delete-receipt-image\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: expense-capture-mcp\n      transport: http\n      description: \"\
  MCP server for AI-assisted expense capture and receipt management.\"\n      tools:\n        - name: list-quick-expenses\n          description: >-\n            List all quick expenses the user has captured that have not yet been\n            assigned to a formal expense report.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"concur-receipt-capture.list-quick-expenses\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-quick-expense\n          description: \"Get details of a specific quick expense by ID.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"concur-receipt-capture.get-quick-expense\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-quick-expense\n          description: >-\n            Capture a new quick expense on-the-go.\
  \ Provide the expense type,\n            date, amount, currency, and optional vendor and comment. The expense\n            can later be promoted to a full expense report entry.\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"concur-receipt-capture.create-quick-expense\"\n          with:\n            expenseTypeCode: \"tools.expenseTypeCode\"\n            transactionDate: \"tools.transactionDate\"\n            transactionAmount: \"tools.transactionAmount\"\n            currencyCode: \"tools.currencyCode\"\n            vendor: \"tools.vendor\"\n            comment: \"tools.comment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-quick-expense\n          description: \"Delete a quick expense that is no longer needed.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"concur-receipt-capture.delete-quick-expense\"\
  \n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-receipt-images\n          description: >-\n            List receipt images attached to expense entries. Optionally filter\n            by entry ID to find receipts for a specific expense.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"concur-receipt-capture.list-receipt-images\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-receipt-image\n          description: >-\n            Retrieve the download URL for a specific receipt image.\n            The URL is temporary and expires after a short period.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"concur-receipt-capture.get-receipt-image\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            -\
  \ type: object\n              mapping: \"$.\"\n        - name: delete-receipt-image\n          description: \"Delete a receipt image that was uploaded in error.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"concur-receipt-capture.delete-receipt-image\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sap-concur-expense/refs/heads/main/capabilities/expense-capture-and-receipts.yaml
tags:
- Expense Capture
- Mobile
- Receipts
- SAP Concur
- Travel
tools:
- description: List all quick expenses the user has captured that have not yet been assigned to a formal expense report.
  hints:
    openWorld: true
    readOnly: true
  name: list-quick-expenses
- description: Get details of a specific quick expense by ID.
  hints:
    openWorld: false
    readOnly: true
  name: get-quick-expense
- description: Capture a new quick expense on-the-go. Provide the expense type, date, amount, currency, and optional vendor and comment. The expense can later be promoted to a full expense report entry.
  hints:
    destructive: false
    readOnly: false
  name: create-quick-expense
- description: Delete a quick expense that is no longer needed.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-quick-expense
- description: List receipt images attached to expense entries. Optionally filter by entry ID to find receipts for a specific expense.
  hints:
    openWorld: true
    readOnly: true
  name: list-receipt-images
- description: Retrieve the download URL for a specific receipt image. The URL is temporary and expires after a short period.
  hints:
    openWorld: false
    readOnly: true
  name: get-receipt-image
- description: Delete a receipt image that was uploaded in error.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-receipt-image
---
