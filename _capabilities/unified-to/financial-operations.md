---
categories: []
consumed_apis:
- unified-accounting
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
- invoice management
- list financial transactions
- invoices
- CRM Integrator
- developers building hr workflows, employee onboarding, and recruiting automation
- accounting
- list accounting transactions
- list invoices from a connected accounting integration
- list payments from a connected accounting integration
- list accounting payments
- crm contact, company, and deal management across 47+ integrations
- create a new invoice
- financial
- chart of accounts management
- list invoices
- list financial transactions from a connected accounting integration
- developers building invoicing automation, expense management, and accounting sync
- list accounting accounts
- create a new invoice in a connected accounting integration
- People Operations Engineer
- unified.to
- developers building sales tools, crm sync, and revenue reporting integrations
- payment management
- payments
- list accounting contacts (customers and vendors) from a connected accounting integration
- integrations
- list accounts from chart of accounts
- unified api
- accounting customer and vendor contacts
- Revenue Operations Developer
- Finance Operations Engineer
- list chart of accounts from a connected accounting integration (quickbooks, xero, etc.)
- HR Technology Developer
- list accounting invoices
- list accounting contacts
- hris and ats management across 296+ hr and recruiting integrations
- Fintech Developer
- financial transaction history
- create accounting invoice
- accounting, invoicing, and payment management across 41+ integrations
slug: financial-operations
source_filename: financial-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Unified.to Financial Operations\"\n  description: >-\n    Unified financial operations workflow combining accounting, invoicing, transactions,\n    and payment management across 41 accounting integrations including QuickBooks, Xero,\n    and FreshBooks. Used by fintech developers, accounting automation tools, and finance\n    teams building cross-platform financial reporting and billing automation.\n  tags:\n    - Unified.to\n    - Accounting\n    - Financial\n    - Invoices\n    - Payments\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      UNIFIED_TO_API_KEY: UNIFIED_TO_API_KEY\n\ncapability:\n  consumes:\n    - import: unified-accounting\n      location: ./shared/accounting-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: unified-financial-ops-api\n      description: \"Unified REST API for financial operations across 41+ accounting integrations.\"\
  \n      resources:\n        - path: /v1/accounting/{connection_id}/accounts\n          name: accounts\n          description: \"Chart of accounts management\"\n          operations:\n            - method: GET\n              name: list-accounting-accounts\n              description: \"List accounts from chart of accounts\"\n              call: \"unified-accounting.list-accounting-accounts\"\n              with:\n                connection_id: \"rest.connection_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/accounting/{connection_id}/invoices\n          name: invoices\n          description: \"Invoice management\"\n          operations:\n            - method: GET\n              name: list-accounting-invoices\n              description: \"List invoices\"\n              call: \"unified-accounting.list-accounting-invoices\"\n              with:\n                connection_id: \"rest.connection_id\"\n          \
  \      limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-accounting-invoice\n              description: \"Create a new invoice\"\n              call: \"unified-accounting.create-accounting-invoice\"\n              with:\n                connection_id: \"rest.connection_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/accounting/{connection_id}/transactions\n          name: transactions\n          description: \"Financial transaction history\"\n          operations:\n            - method: GET\n              name: list-accounting-transactions\n              description: \"List financial transactions\"\n              call: \"unified-accounting.list-accounting-transactions\"\n              with:\n                connection_id: \"rest.connection_id\"\n              outputParameters:\n  \
  \              - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/accounting/{connection_id}/payments\n          name: payments\n          description: \"Payment management\"\n          operations:\n            - method: GET\n              name: list-accounting-payments\n              description: \"List accounting payments\"\n              call: \"unified-accounting.list-accounting-payments\"\n              with:\n                connection_id: \"rest.connection_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/accounting/{connection_id}/contacts\n          name: contacts\n          description: \"Accounting customer and vendor contacts\"\n          operations:\n            - method: GET\n              name: list-accounting-contacts\n              description: \"List accounting contacts\"\n              call: \"unified-accounting.list-accounting-contacts\"\n              with:\n       \
  \         connection_id: \"rest.connection_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9082\n      namespace: unified-financial-ops-mcp\n      transport: http\n      description: \"MCP server for AI-assisted financial operations across 41+ accounting integrations.\"\n      tools:\n        - name: list-accounting-accounts\n          description: \"List chart of accounts from a connected accounting integration (QuickBooks, Xero, etc.)\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unified-accounting.list-accounting-accounts\"\n          with:\n            connection_id: \"tools.connection_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-accounting-invoices\n          description: \"List invoices from a connected accounting integration\"\n          hints:\n            readOnly: true\n\
  \            openWorld: false\n          call: \"unified-accounting.list-accounting-invoices\"\n          with:\n            connection_id: \"tools.connection_id\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-accounting-invoice\n          description: \"Create a new invoice in a connected accounting integration\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"unified-accounting.create-accounting-invoice\"\n          with:\n            connection_id: \"tools.connection_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-accounting-transactions\n          description: \"List financial transactions from a connected accounting integration\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unified-accounting.list-accounting-transactions\"\
  \n          with:\n            connection_id: \"tools.connection_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-accounting-payments\n          description: \"List payments from a connected accounting integration\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unified-accounting.list-accounting-payments\"\n          with:\n            connection_id: \"tools.connection_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-accounting-contacts\n          description: \"List accounting contacts (customers and vendors) from a connected accounting integration\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unified-accounting.list-accounting-contacts\"\n          with:\n            connection_id: \"tools.connection_id\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n"
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
