---
api_specs:
- filename: ramp-developer-api-openapi.yml
  format: yaml
  label: ramp
  slug: ramp
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/ramp/refs/heads/main/openapi/ramp-developer-api-openapi.yml
categories: []
consumed_apis:
- ramp
description: Workflow capability for managing corporate spend, cards, and expense automation using the Ramp Developer API. Enables finance teams and developers to query transactions, manage cards, track reimbursements, and analyze spending patterns across the organization.
layout: capability
name: Ramp Spend Management
operations:
- description: List transactions with optional date range filters.
  method: GET
  name: list-transactions
  path: /v1/transactions
- description: Retrieve a single transaction by ID.
  method: GET
  name: get-transaction
  path: /v1/transactions/{id}
- description: List all cards issued to users and departments.
  method: GET
  name: list-cards
  path: /v1/cards
- description: List all users in the organization.
  method: GET
  name: list-users
  path: /v1/users
- description: List all departments.
  method: GET
  name: list-departments
  path: /v1/departments
- description: List all reimbursement requests.
  method: GET
  name: list-reimbursements
  path: /v1/reimbursements
- description: List all bills.
  method: GET
  name: list-bills
  path: /v1/bills
- description: List all card statements.
  method: GET
  name: list-statements
  path: /v1/statements
personas: []
provider_name: Ramp
provider_slug: ramp
search_terms:
- list all reimbursement requests.
- list ramp card and bill transactions with optional date range filtering. use to analyze spending, reconcile expenses, or audit financial activity.
- list reimbursements
- physical and virtual corporate cards.
- ramp
- list users
- list bills
- list card statements for period-end reconciliation.
- list all ramp users in the organization with their roles and department assignments.
- get transaction
- list all users in the organization.
- list cards
- accounting
- card statement records.
- department records.
- list all departments to understand organizational spend structure.
- finance
- list all cards issued to users and departments.
- spend management
- accounts payable
- list transactions with optional date range filters.
- list bill pay records and their approval status.
- list all departments.
- corporate cards
- card and bill transactions across the organization.
- out-of-pocket reimbursement requests.
- bill pay records and approval workflows.
- list all card statements.
- expense management
- single transaction record.
- retrieve a single transaction by id.
- ramp user accounts.
- list transactions
- list departments
- retrieve a single ramp transaction by id. use to inspect a specific expense or resolve a dispute.
- bill pay
- list out-of-pocket reimbursement requests submitted by employees.
- list statements
- list all bills.
- reimbursements
- list all corporate cards issued in the organization, including spending limits and states.
slug: spend-management
source_filename: spend-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Ramp Spend Management\"\n  description: >-\n    Workflow capability for managing corporate spend, cards, and expense automation\n    using the Ramp Developer API. Enables finance teams and developers to query\n    transactions, manage cards, track reimbursements, and analyze spending patterns\n    across the organization.\n  tags:\n    - Finance\n    - Spend Management\n    - Corporate Cards\n    - Expense Management\n    - Ramp\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      RAMP_ACCESS_TOKEN: RAMP_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: ramp\n      location: ./shared/ramp-developer-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: ramp-spend-management-api\n      description: \"Unified REST API for Ramp spend management workflows.\"\n      resources:\n        - path: /v1/transactions\n          name: transactions\n          description:\
  \ \"Card and bill transactions across the organization.\"\n          operations:\n            - method: GET\n              name: list-transactions\n              description: \"List transactions with optional date range filters.\"\n              call: \"ramp.list-transactions\"\n              with:\n                from_date: \"rest.from_date\"\n                to_date: \"rest.to_date\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/transactions/{id}\n          name: transaction\n          description: \"Single transaction record.\"\n          operations:\n            - method: GET\n              name: get-transaction\n              description: \"Retrieve a single transaction by ID.\"\n              call: \"ramp.get-transaction\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/cards\n\
  \          name: cards\n          description: \"Physical and virtual corporate cards.\"\n          operations:\n            - method: GET\n              name: list-cards\n              description: \"List all cards issued to users and departments.\"\n              call: \"ramp.list-cards\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/users\n          name: users\n          description: \"Ramp user accounts.\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List all users in the organization.\"\n              call: \"ramp.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/departments\n          name: departments\n          description: \"Department records.\"\n          operations:\n            - method: GET\n              name: list-departments\n              description:\
  \ \"List all departments.\"\n              call: \"ramp.list-departments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/reimbursements\n          name: reimbursements\n          description: \"Out-of-pocket reimbursement requests.\"\n          operations:\n            - method: GET\n              name: list-reimbursements\n              description: \"List all reimbursement requests.\"\n              call: \"ramp.list-reimbursements\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/bills\n          name: bills\n          description: \"Bill pay records and approval workflows.\"\n          operations:\n            - method: GET\n              name: list-bills\n              description: \"List all bills.\"\n              call: \"ramp.list-bills\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n\n        - path: /v1/statements\n          name: statements\n          description: \"Card statement records.\"\n          operations:\n            - method: GET\n              name: list-statements\n              description: \"List all card statements.\"\n              call: \"ramp.list-statements\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: ramp-spend-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted spend management and expense automation using Ramp.\"\n      tools:\n        - name: list-transactions\n          description: \"List Ramp card and bill transactions with optional date range filtering. Use to analyze spending, reconcile expenses, or audit financial activity.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ramp.list-transactions\"\n          with:\n            from_date:\
  \ \"tools.from_date\"\n            to_date: \"tools.to_date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-transaction\n          description: \"Retrieve a single Ramp transaction by ID. Use to inspect a specific expense or resolve a dispute.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ramp.get-transaction\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-cards\n          description: \"List all corporate cards issued in the organization, including spending limits and states.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ramp.list-cards\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-users\n          description: \"List all Ramp users in the organization\
  \ with their roles and department assignments.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ramp.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-departments\n          description: \"List all departments to understand organizational spend structure.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ramp.list-departments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-reimbursements\n          description: \"List out-of-pocket reimbursement requests submitted by employees.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ramp.list-reimbursements\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-bills\n          description: \"List bill pay records\
  \ and their approval status.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ramp.list-bills\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-statements\n          description: \"List card statements for period-end reconciliation.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ramp.list-statements\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ramp/refs/heads/main/capabilities/spend-management.yaml
tags:
- Finance
- Spend Management
- Corporate Cards
- Expense Management
- Ramp
tools:
- description: List Ramp card and bill transactions with optional date range filtering. Use to analyze spending, reconcile expenses, or audit financial activity.
  hints:
    openWorld: true
    readOnly: true
  name: list-transactions
- description: Retrieve a single Ramp transaction by ID. Use to inspect a specific expense or resolve a dispute.
  hints:
    idempotent: true
    readOnly: true
  name: get-transaction
- description: List all corporate cards issued in the organization, including spending limits and states.
  hints:
    openWorld: true
    readOnly: true
  name: list-cards
- description: List all Ramp users in the organization with their roles and department assignments.
  hints:
    openWorld: true
    readOnly: true
  name: list-users
- description: List all departments to understand organizational spend structure.
  hints:
    openWorld: true
    readOnly: true
  name: list-departments
- description: List out-of-pocket reimbursement requests submitted by employees.
  hints:
    openWorld: true
    readOnly: true
  name: list-reimbursements
- description: List bill pay records and their approval status.
  hints:
    openWorld: true
    readOnly: true
  name: list-bills
- description: List card statements for period-end reconciliation.
  hints:
    openWorld: true
    readOnly: true
  name: list-statements
---
