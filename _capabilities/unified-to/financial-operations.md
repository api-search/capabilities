---
categories: []
consumed_apis: []
description: Unified financial operations workflow combining accounting, invoicing, transactions, and payment management across 41 accounting integrations including QuickBooks, Xero, and FreshBooks. Used by fintech developers, accounting automation tools, and finance teams building cross-platform financial reporting and billing automation.
layout: capability
name: Unified.to Financial Operations
operations:
- description: List accounts from chart of accounts
  method: GET
  name: list-accounting-accounts
  path: /v1/accounting/{connection_id}/accounts
- description: List invoices
  method: GET
  name: list-accounting-invoices
  path: /v1/accounting/{connection_id}/invoices
- description: Create a new invoice
  method: POST
  name: create-accounting-invoice
  path: /v1/accounting/{connection_id}/invoices
- description: List financial transactions
  method: GET
  name: list-accounting-transactions
  path: /v1/accounting/{connection_id}/transactions
- description: List accounting payments
  method: GET
  name: list-accounting-payments
  path: /v1/accounting/{connection_id}/payments
- description: List accounting contacts
  method: GET
  name: list-accounting-contacts
  path: /v1/accounting/{connection_id}/contacts
personas: []
provider_name: Unified.to
provider_slug: unified-to
search_terms:
- integrations
- invoice management
- list payments from a connected accounting integration
- accounting
- payment management
- developers building sales tools, crm sync, and revenue reporting integrations
- accounting customer and vendor contacts
- create a new invoice
- unified api
- invoices
- list accounting accounts
- list chart of accounts from a connected accounting integration (quickbooks, xero, etc.)
- list accounts from chart of accounts
- create accounting invoice
- CRM Integrator
- unified.to
- developers building hr workflows, employee onboarding, and recruiting automation
- list invoices from a connected accounting integration
- create a new invoice in a connected accounting integration
- Fintech Developer
- HR Technology Developer
- list accounting payments
- list financial transactions
- Finance Operations Engineer
- financial transaction history
- list accounting contacts
- list accounting transactions
- list financial transactions from a connected accounting integration
- chart of accounts management
- People Operations Engineer
- list accounting invoices
- financial
- list accounting contacts (customers and vendors) from a connected accounting integration
- payments
- crm contact, company, and deal management across 47+ integrations
- accounting, invoicing, and payment management across 41+ integrations
- Revenue Operations Developer
- list invoices
- hris and ats management across 296+ hr and recruiting integrations
- developers building invoicing automation, expense management, and accounting sync
slug: financial-operations
source_filename: financial-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Unified.to Financial Operations\n  description: Unified financial operations workflow combining accounting, invoicing, transactions, and payment management\n    across 41 accounting integrations including QuickBooks, Xero, and FreshBooks. Used by fintech developers, accounting automation\n    tools, and finance teams building cross-platform financial reporting and billing automation.\n  tags:\n  - Unified.to\n  - Accounting\n  - Financial\n  - Invoices\n  - Payments\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    UNIFIED_TO_API_KEY: UNIFIED_TO_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: unified-accounting\n    baseUri: https://api.unified.to\n    description: Unified Accounting API for financial data management.\n    authentication:\n      type: bearer\n      token: '{{UNIFIED_TO_API_KEY}}'\n    resources:\n    - name: accounts\n      path: /accounting/{connection_id}/account\n\
  \      description: Chart of accounts management\n      operations:\n      - name: list-accounting-accounts\n        method: GET\n        description: List accounts from the chart of accounts\n        inputParameters:\n        - name: connection_id\n          in: path\n          type: string\n          required: true\n          description: Accounting integration connection ID\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invoices\n      path: /accounting/{connection_id}/invoice\n      description: Invoice management\n      operations:\n      - name: list-accounting-invoices\n        method: GET\n        description: List invoices\n        inputParameters:\n        - name: connection_id\n          in: path\n          type: string\n          required:\
  \ true\n          description: Accounting integration connection ID\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-accounting-invoice\n        method: POST\n        description: Create an invoice\n        inputParameters:\n        - name: connection_id\n          in: path\n          type: string\n          required: true\n          description: Accounting integration connection ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transactions\n      path: /accounting/{connection_id}/transaction\n      description: Financial transaction management\n      operations:\n      - name: list-accounting-transactions\n        method: GET\n        description: List\
  \ financial transactions\n        inputParameters:\n        - name: connection_id\n          in: path\n          type: string\n          required: true\n          description: Accounting integration connection ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts\n      path: /accounting/{connection_id}/contact\n      description: Accounting contact (customer/vendor) management\n      operations:\n      - name: list-accounting-contacts\n        method: GET\n        description: List accounting contacts\n        inputParameters:\n        - name: connection_id\n          in: path\n          type: string\n          required: true\n          description: Accounting integration connection ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payments\n      path: /accounting/{connection_id}/payment\n      description:\
  \ Payment management\n      operations:\n      - name: list-accounting-payments\n        method: GET\n        description: List accounting payments\n        inputParameters:\n        - name: connection_id\n          in: path\n          type: string\n          required: true\n          description: Accounting integration connection ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: unified-financial-ops-api\n    description: Unified REST API for financial operations across 41+ accounting integrations.\n    resources:\n    - path: /v1/accounting/{connection_id}/accounts\n      name: accounts\n      description: Chart of accounts management\n      operations:\n      - method: GET\n        name: list-accounting-accounts\n        description: List accounts from chart of accounts\n        call: unified-accounting.list-accounting-accounts\n        with:\n\
  \          connection_id: rest.connection_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounting/{connection_id}/invoices\n      name: invoices\n      description: Invoice management\n      operations:\n      - method: GET\n        name: list-accounting-invoices\n        description: List invoices\n        call: unified-accounting.list-accounting-invoices\n        with:\n          connection_id: rest.connection_id\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-accounting-invoice\n        description: Create a new invoice\n        call: unified-accounting.create-accounting-invoice\n        with:\n          connection_id: rest.connection_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounting/{connection_id}/transactions\n      name: transactions\n      description: Financial transaction history\n\
  \      operations:\n      - method: GET\n        name: list-accounting-transactions\n        description: List financial transactions\n        call: unified-accounting.list-accounting-transactions\n        with:\n          connection_id: rest.connection_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounting/{connection_id}/payments\n      name: payments\n      description: Payment management\n      operations:\n      - method: GET\n        name: list-accounting-payments\n        description: List accounting payments\n        call: unified-accounting.list-accounting-payments\n        with:\n          connection_id: rest.connection_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounting/{connection_id}/contacts\n      name: contacts\n      description: Accounting customer and vendor contacts\n      operations:\n      - method: GET\n        name: list-accounting-contacts\n        description:\
  \ List accounting contacts\n        call: unified-accounting.list-accounting-contacts\n        with:\n          connection_id: rest.connection_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9082\n    namespace: unified-financial-ops-mcp\n    transport: http\n    description: MCP server for AI-assisted financial operations across 41+ accounting integrations.\n    tools:\n    - name: list-accounting-accounts\n      description: List chart of accounts from a connected accounting integration (QuickBooks, Xero, etc.)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unified-accounting.list-accounting-accounts\n      with:\n        connection_id: tools.connection_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-accounting-invoices\n      description: List invoices from a connected accounting integration\n      hints:\n        readOnly: true\n        openWorld: false\n  \
  \    call: unified-accounting.list-accounting-invoices\n      with:\n        connection_id: tools.connection_id\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-accounting-invoice\n      description: Create a new invoice in a connected accounting integration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: unified-accounting.create-accounting-invoice\n      with:\n        connection_id: tools.connection_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-accounting-transactions\n      description: List financial transactions from a connected accounting integration\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unified-accounting.list-accounting-transactions\n      with:\n        connection_id: tools.connection_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-accounting-payments\n\
  \      description: List payments from a connected accounting integration\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unified-accounting.list-accounting-payments\n      with:\n        connection_id: tools.connection_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-accounting-contacts\n      description: List accounting contacts (customers and vendors) from a connected accounting integration\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unified-accounting.list-accounting-contacts\n      with:\n        connection_id: tools.connection_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/unified-to/refs/heads/main/capabilities/financial-operations.yaml
tags:
- Unified.to
- Accounting
- Financial
- Invoices
- Payments
tools:
- description: List chart of accounts from a connected accounting integration (QuickBooks, Xero, etc.)
  hints:
    openWorld: false
    readOnly: true
  name: list-accounting-accounts
- description: List invoices from a connected accounting integration
  hints:
    openWorld: false
    readOnly: true
  name: list-accounting-invoices
- description: Create a new invoice in a connected accounting integration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-accounting-invoice
- description: List financial transactions from a connected accounting integration
  hints:
    openWorld: false
    readOnly: true
  name: list-accounting-transactions
- description: List payments from a connected accounting integration
  hints:
    openWorld: false
    readOnly: true
  name: list-accounting-payments
- description: List accounting contacts (customers and vendors) from a connected accounting integration
  hints:
    openWorld: false
    readOnly: true
  name: list-accounting-contacts
---
