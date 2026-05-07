---
categories: []
consumed_apis: []
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
- get details for a specific accounting platform connection
- create a new invoice in the connected accounting platform
- accounting
- list connections
- create bill
- create a new invoice in connected accounting platform
- unified api
- invoices
- list all accounts from connected accounting platform
- create a new bill in connected accounting platform
- list bills from connected accounting platform
- list all connected accounting platforms (quickbooks, xero, netsuite, etc.)
- b2b
- list accounts
- list all connected accounting platforms
- chart of accounts
- list financial transactions from connected accounting platform
- single invoice
- financial data
- reconciliation
- create invoice
- financial transactions
- list expense records from connected accounting platform
- list invoices from connected accounting platform
- get a specific invoice by id
- list expenses
- create a new vendor bill in the connected accounting platform
- bills (vendor invoices)
- list bills
- expense records
- platform connections management
- list vendor bills from connected accounting platform
- list expenses from connected accounting platform
- get connection
- payments
- list invoices
- list financial transactions from connected platform
- get invoice
- list chart of accounts from connected accounting platform
- list transactions
- commerce
- get a specific connection by id
slug: financial-data-sync
source_filename: financial-data-sync.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Rutter Financial Data Sync\n  description: Unified workflow for syncing financial data across accounting platforms including QuickBooks, Xero, NetSuite,\n    and Freshbooks. Enables finance teams to read and reconcile accounts, transactions, invoices, bills, and expenses through\n    a single interface regardless of the underlying accounting platform.\n  tags:\n  - Accounting\n  - B2B\n  - Financial Data\n  - Invoices\n  - Reconciliation\n  - Unified API\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RUTTER_CLIENT_ID: RUTTER_CLIENT_ID\n    RUTTER_CLIENT_SECRET: RUTTER_CLIENT_SECRET\ncapability:\n  consumes:\n  - type: http\n    namespace: rutter\n    baseUri: https://production.rutterapi.com/versioned\n    description: Rutter Unified API for B2B financial platform data\n    authentication:\n      type: basic\n      username: '{{RUTTER_CLIENT_ID}}'\n      password: '{{RUTTER_CLIENT_SECRET}}'\n\
  \    resources:\n    - name: connections\n      path: /connections\n      description: Manage platform connections\n      operations:\n      - name: list-connections\n        method: GET\n        description: Retrieve all connections for the authenticated client\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version (e.g. 2024-08-31)\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-connection\n        method: GET\n        description: Retrieve details for a specific platform connection\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n\
  \        - name: connectionId\n          in: path\n          type: string\n          required: true\n          description: Connection identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: exchange-token\n        method: POST\n        description: Exchange Rutter Link public token for permanent access token\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            public_token: '{{tools.public_token}}'\n    - name: accounts\n      path: /accounts\n      description: Chart of accounts from connected accounting platforms\n      operations:\n      - name: list-accounts\n        method: GET\n \
  \       description: Retrieve chart of accounts from the connected accounting platform\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transactions\n      path: /transactions\n      description: Financial transactions from connected platforms\n      operations:\n      - name: list-transactions\n        method: GET\n        description: Retrieve financial transactions from the connected platform\n        inputParameters:\n        - name: X-Rutter-Version\n\
  \          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: updated_at_min\n          in: query\n          type: string\n          required: false\n          description: Filter updated after this timestamp\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invoices\n      path: /invoices\n      description: Invoices from connected accounting platforms\n      operations:\n      - name: list-invoices\n        method: GET\n        description: Retrieve invoices from the connected accounting platform\n        inputParameters:\n        - name: X-Rutter-Version\n\
  \          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-invoice\n        method: POST\n        description: Create a new invoice in the connected accounting platform\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            customer_id: '{{tools.customer_id}}'\n            currency: '{{tools.currency}}'\n            due_date: '{{tools.due_date}}'\n      - name: get-invoice\n        method: GET\n        description: Retrieve a specific invoice by ID\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        - name: invoiceId\n          in: path\n          type: string\n          required: true\n          description: Invoice identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bills\n   \
  \   path: /bills\n      description: Bills (vendor invoices) from connected accounting platforms\n      operations:\n      - name: list-bills\n        method: GET\n        description: Retrieve bills from the connected accounting platform\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-bill\n        method: POST\n        description: Create a new bill in the connected accounting platform\n        inputParameters:\n        - name: X-Rutter-Version\n\
  \          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            vendor_id: '{{tools.vendor_id}}'\n            currency: '{{tools.currency}}'\n            due_date: '{{tools.due_date}}'\n    - name: expenses\n      path: /expenses\n      description: Expense records from connected accounting platforms\n      operations:\n      - name: list-expenses\n        method: GET\n        description: Retrieve expense records from the connected accounting platform\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description:\
  \ API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders\n      path: /orders\n      description: Orders from connected commerce platforms\n      operations:\n      - name: list-orders\n        method: GET\n        description: Retrieve orders from the connected commerce platform\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        -\
  \ name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: expand\n          in: query\n          type: string\n          required: false\n          description: Expand with platform_data\n        - name: updated_at_min\n          in: query\n          type: string\n          required: false\n          description: Filter updated after this timestamp\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-order\n        method: POST\n        description: Create a new order in the connected commerce platform\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access\
  \ token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            customer_id: '{{tools.customer_id}}'\n            currency: '{{tools.currency}}'\n      - name: get-order\n        method: GET\n        description: Retrieve a specific order by ID\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        - name: orderId\n          in: path\n          type: string\n          required: true\n          description: Order identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: fulfill-order\n      \
  \  method: POST\n        description: Mark an order as fulfilled with fulfillment details\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        - name: orderId\n          in: path\n          type: string\n          required: true\n          description: Order identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            tracking_number: '{{tools.tracking_number}}'\n            carrier: '{{tools.carrier}}'\n    - name: products\n      path: /products\n      description: Products from connected commerce platforms\n      operations:\n      - name: list-products\n        method: GET\n\
  \        description: Retrieve products from the connected commerce platform\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-product\n        method: POST\n        description: Create a new product in the connected commerce platform\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in:\
  \ query\n          type: string\n          required: true\n          description: Connection access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            price: '{{tools.price}}'\n      - name: get-product\n        method: GET\n        description: Retrieve a specific product by ID\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        - name: productId\n          in: path\n          type: string\n          required: true\n          description: Product identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: update-product\n        method: PUT\n        description: Update an existing product in the connected commerce platform\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        - name: productId\n          in: path\n          type: string\n          required: true\n          description: Product identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            price: '{{tools.price}}'\n    - name: customers\n      path: /customers\n      description: Customers from connected commerce or accounting\
  \ platforms\n      operations:\n      - name: list-customers\n        method: GET\n        description: Retrieve customers from the connected platform\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-customer\n        method: GET\n        description: Retrieve details for a specific customer\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description:\
  \ API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description: Connection access token\n        - name: customerId\n          in: path\n          type: string\n          required: true\n          description: Customer identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bank-accounts\n      path: /bank-accounts\n      description: Bank accounts from connected banking platforms\n      operations:\n      - name: list-bank-accounts\n        method: GET\n        description: Retrieve bank accounts from the connected banking platform\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        - name: access_token\n          in: query\n          type: string\n          required: true\n          description:\
  \ Connection access token\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks\n      path: /config-webhooks\n      description: Webhook configuration and management\n      operations:\n      - name: list-webhooks\n        method: GET\n        description: Retrieve all configured webhooks\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-webhook\n        method: POST\n        description: Configure a new webhook endpoint\n        inputParameters:\n        - name: X-Rutter-Version\n          in:\
  \ header\n          type: string\n          required: true\n          description: API version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            url: '{{tools.url}}'\n            events: '{{tools.events}}'\n      - name: delete-webhook\n        method: DELETE\n        description: Remove a webhook configuration\n        inputParameters:\n        - name: X-Rutter-Version\n          in: header\n          type: string\n          required: true\n          description: API version\n        - name: webhookId\n          in: path\n          type: string\n          required: true\n          description: Webhook identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: rutter-financial-sync-api\n    description: Unified\
  \ REST API for financial data synchronization across accounting platforms.\n    resources:\n    - path: /v1/connections\n      name: connections\n      description: Platform connections management\n      operations:\n      - method: GET\n        name: list-connections\n        description: List all connected accounting platforms\n        call: rutter.list-connections\n        with:\n          X-Rutter-Version: rest.header.x-rutter-version\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-connection\n        description: Get a specific connection by ID\n        call: rutter.get-connection\n        with:\n          X-Rutter-Version: rest.header.x-rutter-version\n          connectionId: rest.path.connectionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts\n      name: accounts\n      description: Chart of accounts\n      operations:\n      - method: GET\n        name: list-accounts\n\
  \        description: List all accounts from connected accounting platform\n        call: rutter.list-accounts\n        with:\n          X-Rutter-Version: rest.header.x-rutter-version\n          access_token: rest.query.access_token\n          cursor: rest.query.cursor\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/transactions\n      name: transactions\n      description: Financial transactions\n      operations:\n      - method: GET\n        name: list-transactions\n        description: List financial transactions from connected platform\n        call: rutter.list-transactions\n        with:\n          X-Rutter-Version: rest.header.x-rutter-version\n          access_token: rest.query.access_token\n          cursor: rest.query.cursor\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices\n      name: invoices\n      description: Invoices\n      operations:\n      - method: GET\n        name: list-invoices\n\
  \        description: List invoices from connected accounting platform\n        call: rutter.list-invoices\n        with:\n          X-Rutter-Version: rest.header.x-rutter-version\n          access_token: rest.query.access_token\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-invoice\n        description: Create a new invoice in connected accounting platform\n        call: rutter.create-invoice\n        with:\n          X-Rutter-Version: rest.header.x-rutter-version\n          access_token: rest.query.access_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices/{invoiceId}\n      name: invoice\n      description: Single invoice\n      operations:\n      - method: GET\n        name: get-invoice\n        description: Get a specific invoice by ID\n        call: rutter.get-invoice\n        with:\n          X-Rutter-Version: rest.header.x-rutter-version\n          access_token:\
  \ rest.query.access_token\n          invoiceId: rest.path.invoiceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bills\n      name: bills\n      description: Bills (vendor invoices)\n      operations:\n      - method: GET\n        name: list-bills\n        description: List bills from connected accounting platform\n        call: rutter.list-bills\n        with:\n          X-Rutter-Version: rest.header.x-rutter-version\n          access_token: rest.query.access_token\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-bill\n        description: Create a new bill in connected accounting platform\n        call: rutter.create-bill\n        with:\n          X-Rutter-Version: rest.header.x-rutter-version\n          access_token: rest.query.access_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/expenses\n      name: expenses\n      description:\
  \ Expense records\n      operations:\n      - method: GET\n        name: list-expenses\n        description: List expenses from connected accounting platform\n        call: rutter.list-expenses\n        with:\n          X-Rutter-Version: rest.header.x-rutter-version\n          access_token: rest.query.access_token\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: rutter-financial-sync-mcp\n    transport: http\n    description: MCP server for AI-assisted financial data sync and reconciliation.\n    tools:\n    - name: list-connections\n      description: List all connected accounting platforms (QuickBooks, Xero, NetSuite, etc.)\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rutter.list-connections\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-connection\n      description: Get details for a specific accounting platform connection\n      hints:\n    \
  \    readOnly: true\n        openWorld: false\n      call: rutter.get-connection\n      with:\n        connectionId: tools.connectionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-accounts\n      description: List chart of accounts from connected accounting platform\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rutter.list-accounts\n      with:\n        access_token: tools.access_token\n        cursor: tools.cursor\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-transactions\n      description: List financial transactions from connected accounting platform\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rutter.list-transactions\n      with:\n        access_token: tools.access_token\n        updated_at_min: tools.updated_at_min\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-invoices\n      description: List invoices\
  \ from connected accounting platform\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rutter.list-invoices\n      with:\n        access_token: tools.access_token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-invoice\n      description: Get a specific invoice by ID\n      hints:\n        readOnly: true\n        openWorld: false\n      call: rutter.get-invoice\n      with:\n        access_token: tools.access_token\n        invoiceId: tools.invoiceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-invoice\n      description: Create a new invoice in the connected accounting platform\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: rutter.create-invoice\n      with:\n        access_token: tools.access_token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-bills\n      description: List vendor\
  \ bills from connected accounting platform\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rutter.list-bills\n      with:\n        access_token: tools.access_token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-bill\n      description: Create a new vendor bill in the connected accounting platform\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: rutter.create-bill\n      with:\n        access_token: tools.access_token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-expenses\n      description: List expense records from connected accounting platform\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rutter.list-expenses\n      with:\n        access_token: tools.access_token\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
