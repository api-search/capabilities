---
categories: []
consumed_apis: []
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
- list all departments.
- list all reimbursement requests.
- corporate cards
- retrieve a single transaction by id.
- ramp user accounts.
- list all card statements.
- expense management
- list cards
- bill pay
- accounting
- single transaction record.
- list card statements for period-end reconciliation.
- reimbursements
- ramp
- accounts payable
- list out-of-pocket reimbursement requests submitted by employees.
- list all cards issued to users and departments.
- card statement records.
- list departments
- retrieve a single ramp transaction by id. use to inspect a specific expense or resolve a dispute.
- list all bills.
- get transaction
- list all departments to understand organizational spend structure.
- finance
- list all ramp users in the organization with their roles and department assignments.
- list users
- list all corporate cards issued in the organization, including spending limits and states.
- spend management
- physical and virtual corporate cards.
- list bill pay records and their approval status.
- list reimbursements
- list statements
- list bills
- out-of-pocket reimbursement requests.
- card and bill transactions across the organization.
- list ramp card and bill transactions with optional date range filtering. use to analyze spending, reconcile expenses, or audit financial activity.
- list all users in the organization.
- list transactions
- department records.
- list transactions with optional date range filters.
- bill pay records and approval workflows.
slug: spend-management
source_filename: spend-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Ramp Spend Management\n  description: Workflow capability for managing corporate spend, cards, and expense automation using the Ramp Developer API.\n    Enables finance teams and developers to query transactions, manage cards, track reimbursements, and analyze spending patterns\n    across the organization.\n  tags:\n  - Finance\n  - Spend Management\n  - Corporate Cards\n  - Expense Management\n  - Ramp\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RAMP_ACCESS_TOKEN: RAMP_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: ramp\n    baseUri: https://api.ramp.com/developer/v1\n    description: Ramp Developer API for finance automation and spend management.\n    authentication:\n      type: bearer\n      token: '{{RAMP_ACCESS_TOKEN}}'\n    resources:\n    - name: accounting-accounts\n      path: /accounting/accounts\n      description: General ledger account resources.\n  \
  \    operations:\n      - name: list-accounting-accounts\n        method: GET\n        description: Returns a paginated list of general ledger accounts.\n        inputParameters:\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description: Number of records per page.\n        - name: start\n          in: query\n          type: string\n          required: false\n          description: Cursor for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounting-vendors\n      path: /accounting/vendors\n      description: Vendor records for accounting integrations.\n      operations:\n      - name: list-accounting-vendors\n        method: GET\n        description: Returns a list of vendor records.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ transactions\n      path: /transactions\n      description: Card and bill transactions.\n      operations:\n      - name: list-transactions\n        method: GET\n        description: Returns a paginated list of transactions.\n        inputParameters:\n        - name: from_date\n          in: query\n          type: string\n          required: false\n          description: Start date filter (YYYY-MM-DD).\n        - name: to_date\n          in: query\n          type: string\n          required: false\n          description: End date filter (YYYY-MM-DD).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transaction\n      path: /transactions/{id}\n      description: Single transaction resource.\n      operations:\n      - name: get-transaction\n        method: GET\n        description: Retrieves a single transaction by ID.\n        inputParameters:\n        - name: id\n          in: path\n         \
  \ type: string\n          required: true\n          description: Transaction identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cards\n      path: /cards\n      description: Physical and virtual cards.\n      operations:\n      - name: list-cards\n        method: GET\n        description: Returns a paginated list of cards.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      description: User accounts.\n      operations:\n      - name: list-users\n        method: GET\n        description: Returns a paginated list of users.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: departments\n      path: /departments\n      description: Department records.\n      operations:\n      - name:\
  \ list-departments\n        method: GET\n        description: Returns a paginated list of departments.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: locations\n      path: /locations\n      description: Location records.\n      operations:\n      - name: list-locations\n        method: GET\n        description: Returns a paginated list of locations.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reimbursements\n      path: /reimbursements\n      description: Out-of-pocket reimbursement requests.\n      operations:\n      - name: list-reimbursements\n        method: GET\n        description: Returns a paginated list of reimbursements.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bills\n      path: /bills\n   \
  \   description: Bill pay records.\n      operations:\n      - name: list-bills\n        method: GET\n        description: Returns a paginated list of bills.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: statements\n      path: /statements\n      description: Card statement records.\n      operations:\n      - name: list-statements\n        method: GET\n        description: Returns a paginated list of statements.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: audit-logs\n      path: /audit-logs/events\n      description: Audit events.\n      operations:\n      - name: list-audit-events\n        method: GET\n        description: Returns a paginated list of audit events.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n\
  \  - type: rest\n    port: 8080\n    namespace: ramp-spend-management-api\n    description: Unified REST API for Ramp spend management workflows.\n    resources:\n    - path: /v1/transactions\n      name: transactions\n      description: Card and bill transactions across the organization.\n      operations:\n      - method: GET\n        name: list-transactions\n        description: List transactions with optional date range filters.\n        call: ramp.list-transactions\n        with:\n          from_date: rest.from_date\n          to_date: rest.to_date\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/transactions/{id}\n      name: transaction\n      description: Single transaction record.\n      operations:\n      - method: GET\n        name: get-transaction\n        description: Retrieve a single transaction by ID.\n        call: ramp.get-transaction\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n  \
  \        mapping: $.\n    - path: /v1/cards\n      name: cards\n      description: Physical and virtual corporate cards.\n      operations:\n      - method: GET\n        name: list-cards\n        description: List all cards issued to users and departments.\n        call: ramp.list-cards\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: Ramp user accounts.\n      operations:\n      - method: GET\n        name: list-users\n        description: List all users in the organization.\n        call: ramp.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/departments\n      name: departments\n      description: Department records.\n      operations:\n      - method: GET\n        name: list-departments\n        description: List all departments.\n        call: ramp.list-departments\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /v1/reimbursements\n      name: reimbursements\n      description: Out-of-pocket reimbursement requests.\n      operations:\n      - method: GET\n        name: list-reimbursements\n        description: List all reimbursement requests.\n        call: ramp.list-reimbursements\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bills\n      name: bills\n      description: Bill pay records and approval workflows.\n      operations:\n      - method: GET\n        name: list-bills\n        description: List all bills.\n        call: ramp.list-bills\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/statements\n      name: statements\n      description: Card statement records.\n      operations:\n      - method: GET\n        name: list-statements\n        description: List all card statements.\n        call: ramp.list-statements\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type:\
  \ mcp\n    port: 9080\n    namespace: ramp-spend-management-mcp\n    transport: http\n    description: MCP server for AI-assisted spend management and expense automation using Ramp.\n    tools:\n    - name: list-transactions\n      description: List Ramp card and bill transactions with optional date range filtering. Use to analyze spending, reconcile\n        expenses, or audit financial activity.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ramp.list-transactions\n      with:\n        from_date: tools.from_date\n        to_date: tools.to_date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-transaction\n      description: Retrieve a single Ramp transaction by ID. Use to inspect a specific expense or resolve a dispute.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ramp.get-transaction\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n \
  \   - name: list-cards\n      description: List all corporate cards issued in the organization, including spending limits and states.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ramp.list-cards\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-users\n      description: List all Ramp users in the organization with their roles and department assignments.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ramp.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-departments\n      description: List all departments to understand organizational spend structure.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ramp.list-departments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-reimbursements\n      description: List out-of-pocket reimbursement requests submitted by employees.\n      hints:\n\
  \        readOnly: true\n        openWorld: true\n      call: ramp.list-reimbursements\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-bills\n      description: List bill pay records and their approval status.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ramp.list-bills\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-statements\n      description: List card statements for period-end reconciliation.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ramp.list-statements\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
