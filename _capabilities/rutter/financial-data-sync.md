---
categories: []
consumed_apis:
- rutter
description: Unified workflow for syncing financial data across accounting platforms including QuickBooks, Xero, NetSuite, and Freshbooks. Enables finance teams to read and reconcile accounts, transactions, invoices, bills, and expenses through a single interface regardless of the underlying accounting platform.
layout: capability
name: Rutter Financial Data Sync
operations:
- description: List all connected accounting platforms
  method: GET
  name: list-connections
  path: /v1/connections
- description: Get a specific connection by ID
  method: GET
  name: get-connection
  path: /v1/connections
- description: List all accounts from connected accounting platform
  method: GET
  name: list-accounts
  path: /v1/accounts
- description: List financial transactions from connected platform
  method: GET
  name: list-transactions
  path: /v1/transactions
- description: List invoices from connected accounting platform
  method: GET
  name: list-invoices
  path: /v1/invoices
- description: Create a new invoice in connected accounting platform
  method: POST
  name: create-invoice
  path: /v1/invoices
- description: Get a specific invoice by ID
  method: GET
  name: get-invoice
  path: /v1/invoices/{invoiceId}
- description: List bills from connected accounting platform
  method: GET
  name: list-bills
  path: /v1/bills
- description: Create a new bill in connected accounting platform
  method: POST
  name: create-bill
  path: /v1/bills
- description: List expenses from connected accounting platform
  method: GET
  name: list-expenses
  path: /v1/expenses
personas: []
provider_name: Rutter
provider_slug: rutter
search_terms:
- get a specific invoice by id
- list all accounts from connected accounting platform
- list chart of accounts from connected accounting platform
- list all connected accounting platforms
- list connections
- accounting
- chart of accounts
- list bills from connected accounting platform
- create bill
- list vendor bills from connected accounting platform
- platform connections management
- get a specific connection by id
- list transactions
- create a new invoice in connected accounting platform
- unified api
- list bills
- list expenses from connected accounting platform
- expense records
- list financial transactions from connected platform
- b2b
- list expense records from connected accounting platform
- payments
- list invoices
- commerce
- list financial transactions from connected accounting platform
- reconciliation
- list accounts
- list all connected accounting platforms (quickbooks, xero, netsuite, etc.)
- bills (vendor invoices)
- create a new invoice in the connected accounting platform
- create a new bill in connected accounting platform
- list expenses
- single invoice
- financial data
- get details for a specific accounting platform connection
- get invoice
- create invoice
- get connection
- create a new vendor bill in the connected accounting platform
- list invoices from connected accounting platform
- financial transactions
- invoices
slug: financial-data-sync
source_filename: financial-data-sync.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Rutter Financial Data Sync\"\n  description: >-\n    Unified workflow for syncing financial data across accounting platforms including\n    QuickBooks, Xero, NetSuite, and Freshbooks. Enables finance teams to read and\n    reconcile accounts, transactions, invoices, bills, and expenses through a single\n    interface regardless of the underlying accounting platform.\n  tags:\n    - Accounting\n    - B2B\n    - Financial Data\n    - Invoices\n    - Reconciliation\n    - Unified API\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      RUTTER_CLIENT_ID: RUTTER_CLIENT_ID\n      RUTTER_CLIENT_SECRET: RUTTER_CLIENT_SECRET\n\ncapability:\n  consumes:\n    - import: rutter\n      location: ./shared/unified-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: rutter-financial-sync-api\n      description: \"Unified REST API for financial data synchronization across\
  \ accounting platforms.\"\n      resources:\n        - path: /v1/connections\n          name: connections\n          description: \"Platform connections management\"\n          operations:\n            - method: GET\n              name: list-connections\n              description: \"List all connected accounting platforms\"\n              call: \"rutter.list-connections\"\n              with:\n                X-Rutter-Version: \"rest.header.x-rutter-version\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-connection\n              description: \"Get a specific connection by ID\"\n              call: \"rutter.get-connection\"\n              with:\n                X-Rutter-Version: \"rest.header.x-rutter-version\"\n                connectionId: \"rest.path.connectionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path:\
  \ /v1/accounts\n          name: accounts\n          description: \"Chart of accounts\"\n          operations:\n            - method: GET\n              name: list-accounts\n              description: \"List all accounts from connected accounting platform\"\n              call: \"rutter.list-accounts\"\n              with:\n                X-Rutter-Version: \"rest.header.x-rutter-version\"\n                access_token: \"rest.query.access_token\"\n                cursor: \"rest.query.cursor\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/transactions\n          name: transactions\n          description: \"Financial transactions\"\n          operations:\n            - method: GET\n              name: list-transactions\n              description: \"List financial transactions from connected platform\"\n              call: \"rutter.list-transactions\"\n              with:\n                X-Rutter-Version: \"rest.header.x-rutter-version\"\
  \n                access_token: \"rest.query.access_token\"\n                cursor: \"rest.query.cursor\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/invoices\n          name: invoices\n          description: \"Invoices\"\n          operations:\n            - method: GET\n              name: list-invoices\n              description: \"List invoices from connected accounting platform\"\n              call: \"rutter.list-invoices\"\n              with:\n                X-Rutter-Version: \"rest.header.x-rutter-version\"\n                access_token: \"rest.query.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-invoice\n              description: \"Create a new invoice in connected accounting platform\"\n              call: \"rutter.create-invoice\"\n              with:\n                X-Rutter-Version:\
  \ \"rest.header.x-rutter-version\"\n                access_token: \"rest.query.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/invoices/{invoiceId}\n          name: invoice\n          description: \"Single invoice\"\n          operations:\n            - method: GET\n              name: get-invoice\n              description: \"Get a specific invoice by ID\"\n              call: \"rutter.get-invoice\"\n              with:\n                X-Rutter-Version: \"rest.header.x-rutter-version\"\n                access_token: \"rest.query.access_token\"\n                invoiceId: \"rest.path.invoiceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/bills\n          name: bills\n          description: \"Bills (vendor invoices)\"\n          operations:\n            - method: GET\n              name: list-bills\n              description:\
  \ \"List bills from connected accounting platform\"\n              call: \"rutter.list-bills\"\n              with:\n                X-Rutter-Version: \"rest.header.x-rutter-version\"\n                access_token: \"rest.query.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-bill\n              description: \"Create a new bill in connected accounting platform\"\n              call: \"rutter.create-bill\"\n              with:\n                X-Rutter-Version: \"rest.header.x-rutter-version\"\n                access_token: \"rest.query.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/expenses\n          name: expenses\n          description: \"Expense records\"\n          operations:\n            - method: GET\n              name: list-expenses\n              description: \"List expenses\
  \ from connected accounting platform\"\n              call: \"rutter.list-expenses\"\n              with:\n                X-Rutter-Version: \"rest.header.x-rutter-version\"\n                access_token: \"rest.query.access_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: rutter-financial-sync-mcp\n      transport: http\n      description: \"MCP server for AI-assisted financial data sync and reconciliation.\"\n      tools:\n        - name: list-connections\n          description: \"List all connected accounting platforms (QuickBooks, Xero, NetSuite, etc.)\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rutter.list-connections\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-connection\n          description: \"Get details for a specific accounting platform connection\"\
  \n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"rutter.get-connection\"\n          with:\n            connectionId: \"tools.connectionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-accounts\n          description: \"List chart of accounts from connected accounting platform\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rutter.list-accounts\"\n          with:\n            access_token: \"tools.access_token\"\n            cursor: \"tools.cursor\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-transactions\n          description: \"List financial transactions from connected accounting platform\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rutter.list-transactions\"\n          with:\n            access_token: \"tools.access_token\"\
  \n            updated_at_min: \"tools.updated_at_min\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-invoices\n          description: \"List invoices from connected accounting platform\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rutter.list-invoices\"\n          with:\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-invoice\n          description: \"Get a specific invoice by ID\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"rutter.get-invoice\"\n          with:\n            access_token: \"tools.access_token\"\n            invoiceId: \"tools.invoiceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-invoice\n          description: \"Create a new invoice\
  \ in the connected accounting platform\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"rutter.create-invoice\"\n          with:\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-bills\n          description: \"List vendor bills from connected accounting platform\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rutter.list-bills\"\n          with:\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-bill\n          description: \"Create a new vendor bill in the connected accounting platform\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"rutter.create-bill\"\n  \
  \        with:\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-expenses\n          description: \"List expense records from connected accounting platform\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rutter.list-expenses\"\n          with:\n            access_token: \"tools.access_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/rutter/refs/heads/main/capabilities/financial-data-sync.yaml
tags:
- Accounting
- B2B
- Financial Data
- Invoices
- Reconciliation
- Unified API
tools:
- description: List all connected accounting platforms (QuickBooks, Xero, NetSuite, etc.)
  hints:
    openWorld: true
    readOnly: true
  name: list-connections
- description: Get details for a specific accounting platform connection
  hints:
    openWorld: false
    readOnly: true
  name: get-connection
- description: List chart of accounts from connected accounting platform
  hints:
    openWorld: true
    readOnly: true
  name: list-accounts
- description: List financial transactions from connected accounting platform
  hints:
    openWorld: true
    readOnly: true
  name: list-transactions
- description: List invoices from connected accounting platform
  hints:
    openWorld: true
    readOnly: true
  name: list-invoices
- description: Get a specific invoice by ID
  hints:
    openWorld: false
    readOnly: true
  name: get-invoice
- description: Create a new invoice in the connected accounting platform
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-invoice
- description: List vendor bills from connected accounting platform
  hints:
    openWorld: true
    readOnly: true
  name: list-bills
- description: Create a new vendor bill in the connected accounting platform
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-bill
- description: List expense records from connected accounting platform
  hints:
    openWorld: true
    readOnly: true
  name: list-expenses
---
