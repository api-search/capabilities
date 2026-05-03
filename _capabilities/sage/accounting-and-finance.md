---
api_specs:
- filename: sage-accounting-openapi.yml
  format: yaml
  label: sage-accounting
  slug: sage-accounting
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/sage/refs/heads/main/openapi/sage-accounting-openapi.yml
categories: []
consumed_apis:
- sage-accounting
description: Unified workflow for accounting and financial management using Sage Accounting API v3.1. Covers contacts, invoicing, payment recording, bank reconciliation, and financial reporting. Used by accountants, bookkeepers, and finance teams to manage business finances.
layout: capability
name: Sage Accounting and Finance
operations:
- description: List customers and suppliers
  method: GET
  name: list-contacts
  path: /v1/contacts
- description: Create a new customer or supplier
  method: POST
  name: create-contact
  path: /v1/contacts
- description: Get contact details
  method: GET
  name: get-contact
  path: /v1/contacts/{id}
- description: Update contact details
  method: PUT
  name: update-contact
  path: /v1/contacts/{id}
- description: List sales invoices with filtering by customer, status, and date
  method: GET
  name: list-sales-invoices
  path: /v1/sales-invoices
- description: Create a new sales invoice
  method: POST
  name: create-sales-invoice
  path: /v1/sales-invoices
- description: Get sales invoice details
  method: GET
  name: get-sales-invoice
  path: /v1/sales-invoices/{id}
- description: Record a payment received for a sales invoice
  method: POST
  name: record-sales-payment
  path: /v1/sales-invoices/{id}/payments
- description: List purchase invoices
  method: GET
  name: list-purchase-invoices
  path: /v1/purchase-invoices
- description: Create a new purchase invoice
  method: POST
  name: create-purchase-invoice
  path: /v1/purchase-invoices
- description: List bank accounts
  method: GET
  name: list-bank-accounts
  path: /v1/bank-accounts
- description: List products and services
  method: GET
  name: list-products
  path: /v1/products
- description: Create a new product or service
  method: POST
  name: create-product
  path: /v1/products
- description: List ledger accounts
  method: GET
  name: list-ledger-accounts
  path: /v1/ledger-accounts
- description: List configured tax rates
  method: GET
  name: list-tax-rates
  path: /v1/tax-rates
personas: []
provider_name: Sage
provider_slug: sage
search_terms:
- create sales invoice
- list configured tax rates
- create product
- get full details of a sales invoice including line items and payment status
- individual sales invoice
- list sales invoices
- list purchase invoices
- create a new purchase invoice (supplier bill) in sage accounting
- update contact
- list chart of accounts (ledger accounts) for financial reporting
- record a payment received against a sales invoice
- customer and supplier contact management
- accounting
- list customers and suppliers
- chart of accounts
- list customers and suppliers in sage accounting
- hr
- get sales invoice
- individual contact operations
- list purchase invoices (supplier bills) with filtering options
- list bank accounts
- erp
- list products and services
- create a new customer or supplier
- record sales payment
- get contact
- create a new product or service
- create a new customer or supplier contact in sage accounting
- payments
- create purchase invoice
- list sales invoices with filtering by customer, status, and date
- finance
- get contact details
- list configured tax rates for invoice line items
- cloud software
- create a new product or service in sage accounting
- business management
- sales invoice payments
- product and service catalog
- list tax rates
- create a new purchase invoice
- create a new sales invoice
- list products and services in the sage catalog
- get sales invoice details
- payroll
- create contact
- get details for a specific contact including balance and outstanding amounts
- list contacts
- list products
- bank account management
- tax rates
- record a payment received for a sales invoice
- create a new sales invoice with line items, due date, and customer reference
- list bank accounts connected to the sage accounting business
- sales invoice management
- invoicing
- purchase invoice (supplier bill) management
- list ledger accounts
- update contact details
- list sales invoices filtered by customer, status, or date range
slug: accounting-and-finance
source_filename: accounting-and-finance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Sage Accounting and Finance\"\n  description: \"Unified workflow for accounting and financial management using Sage Accounting API v3.1. Covers contacts, invoicing, payment recording, bank reconciliation, and financial reporting. Used by accountants, bookkeepers, and finance teams to manage business finances.\"\n  tags:\n    - Accounting\n    - ERP\n    - Finance\n    - Invoicing\n    - Payments\n    - Cloud Software\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SAGE_ACCESS_TOKEN: SAGE_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: sage-accounting\n      location: ./shared/sage-accounting.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: accounting-finance-api\n      description: \"Unified REST API for Sage accounting and finance management.\"\n      resources:\n        - path: /v1/contacts\n          name: contacts\n          description:\
  \ \"Customer and supplier contact management\"\n          operations:\n            - method: GET\n              name: list-contacts\n              description: \"List customers and suppliers\"\n              call: \"sage-accounting.list-contacts\"\n              with:\n                contact_type_ids: \"rest.contact_type_ids\"\n                search: \"rest.search\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-contact\n              description: \"Create a new customer or supplier\"\n              call: \"sage-accounting.create-contact\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/contacts/{id}\n          name: contact-detail\n          description: \"Individual contact operations\"\n          operations:\n            - method: GET\n              name: get-contact\n\
  \              description: \"Get contact details\"\n              call: \"sage-accounting.get-contact\"\n              with:\n                key: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-contact\n              description: \"Update contact details\"\n              call: \"sage-accounting.update-contact\"\n              with:\n                key: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/sales-invoices\n          name: sales-invoices\n          description: \"Sales invoice management\"\n          operations:\n            - method: GET\n              name: list-sales-invoices\n              description: \"List sales invoices with filtering by customer, status, and date\"\n              call: \"sage-accounting.list-sales-invoices\"\n              with:\n                contact_id:\
  \ \"rest.contact_id\"\n                status_id: \"rest.status_id\"\n                from_date: \"rest.from_date\"\n                to_date: \"rest.to_date\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-sales-invoice\n              description: \"Create a new sales invoice\"\n              call: \"sage-accounting.create-sales-invoice\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/sales-invoices/{id}\n          name: sales-invoice-detail\n          description: \"Individual sales invoice\"\n          operations:\n            - method: GET\n              name: get-sales-invoice\n              description: \"Get sales invoice details\"\n              call: \"sage-accounting.get-sales-invoice\"\n              with:\n                key: \"rest.id\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/sales-invoices/{id}/payments\n          name: sales-invoice-payments\n          description: \"Sales invoice payments\"\n          operations:\n            - method: POST\n              name: record-sales-payment\n              description: \"Record a payment received for a sales invoice\"\n              call: \"sage-accounting.record-sales-payment\"\n              with:\n                key: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/purchase-invoices\n          name: purchase-invoices\n          description: \"Purchase invoice (supplier bill) management\"\n          operations:\n            - method: GET\n              name: list-purchase-invoices\n              description: \"List purchase invoices\"\n              call: \"sage-accounting.list-purchase-invoices\"\n              outputParameters:\n      \
  \          - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-purchase-invoice\n              description: \"Create a new purchase invoice\"\n              call: \"sage-accounting.create-purchase-invoice\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/bank-accounts\n          name: bank-accounts\n          description: \"Bank account management\"\n          operations:\n            - method: GET\n              name: list-bank-accounts\n              description: \"List bank accounts\"\n              call: \"sage-accounting.list-bank-accounts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/products\n          name: products\n          description: \"Product and service catalog\"\n          operations:\n            - method: GET\n              name: list-products\n              description:\
  \ \"List products and services\"\n              call: \"sage-accounting.list-products\"\n              with:\n                search: \"rest.search\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-product\n              description: \"Create a new product or service\"\n              call: \"sage-accounting.create-product\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/ledger-accounts\n          name: ledger-accounts\n          description: \"Chart of accounts\"\n          operations:\n            - method: GET\n              name: list-ledger-accounts\n              description: \"List ledger accounts\"\n              call: \"sage-accounting.list-ledger-accounts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n\
  \        - path: /v1/tax-rates\n          name: tax-rates\n          description: \"Tax rates\"\n          operations:\n            - method: GET\n              name: list-tax-rates\n              description: \"List configured tax rates\"\n              call: \"sage-accounting.list-tax-rates\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: accounting-finance-mcp\n      transport: http\n      description: \"MCP server for AI-assisted accounting and financial management with Sage Accounting.\"\n      tools:\n        - name: list-contacts\n          description: \"List customers and suppliers in Sage Accounting\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sage-accounting.list-contacts\"\n          with:\n            contact_type_ids: \"tools.contact_type_ids\"\n            search: \"tools.search\"\n            page: \"tools.page\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-contact\n          description: \"Create a new customer or supplier contact in Sage Accounting\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"sage-accounting.create-contact\"\n          with:\n            name: \"tools.name\"\n            contact_type_ids: \"tools.contact_type_ids\"\n            email: \"tools.email\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-contact\n          description: \"Get details for a specific contact including balance and outstanding amounts\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sage-accounting.get-contact\"\n          with:\n            key: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n\n        - name: list-sales-invoices\n          description: \"List sales invoices filtered by customer, status, or date range\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sage-accounting.list-sales-invoices\"\n          with:\n            contact_id: \"tools.contact_id\"\n            status_id: \"tools.status_id\"\n            from_date: \"tools.from_date\"\n            to_date: \"tools.to_date\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-sales-invoice\n          description: \"Create a new sales invoice with line items, due date, and customer reference\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"sage-accounting.create-sales-invoice\"\n          with:\n            contact_id: \"tools.contact_id\"\n            date: \"tools.date\"\n      \
  \      due_date: \"tools.due_date\"\n            reference: \"tools.reference\"\n            line_items: \"tools.line_items\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-sales-invoice\n          description: \"Get full details of a sales invoice including line items and payment status\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sage-accounting.get-sales-invoice\"\n          with:\n            key: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: record-sales-payment\n          description: \"Record a payment received against a sales invoice\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"sage-accounting.record-sales-payment\"\n          with:\n            key: \"tools.invoice_id\"\n            payment_type_id: \"tools.payment_type_id\"\
  \n            bank_account_id: \"tools.bank_account_id\"\n            date: \"tools.date\"\n            amount: \"tools.amount\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-purchase-invoices\n          description: \"List purchase invoices (supplier bills) with filtering options\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sage-accounting.list-purchase-invoices\"\n          with:\n            contact_id: \"tools.contact_id\"\n            status_id: \"tools.status_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-purchase-invoice\n          description: \"Create a new purchase invoice (supplier bill) in Sage Accounting\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"sage-accounting.create-purchase-invoice\"\n          with:\n\
  \            contact_id: \"tools.contact_id\"\n            date: \"tools.date\"\n            due_date: \"tools.due_date\"\n            line_items: \"tools.line_items\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-bank-accounts\n          description: \"List bank accounts connected to the Sage Accounting business\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sage-accounting.list-bank-accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-products\n          description: \"List products and services in the Sage catalog\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sage-accounting.list-products\"\n          with:\n            search: \"tools.search\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name:\
  \ create-product\n          description: \"Create a new product or service in Sage Accounting\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"sage-accounting.create-product\"\n          with:\n            description: \"tools.description\"\n            item_code: \"tools.item_code\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-ledger-accounts\n          description: \"List chart of accounts (ledger accounts) for financial reporting\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sage-accounting.list-ledger-accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-tax-rates\n          description: \"List configured tax rates for invoice line items\"\n          hints:\n            readOnly: true\n            openWorld: false\n \
  \         call: \"sage-accounting.list-tax-rates\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sage/refs/heads/main/capabilities/accounting-and-finance.yaml
tags:
- Accounting
- ERP
- Finance
- Invoicing
- Payments
- Cloud Software
tools:
- description: List customers and suppliers in Sage Accounting
  hints:
    openWorld: false
    readOnly: true
  name: list-contacts
- description: Create a new customer or supplier contact in Sage Accounting
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-contact
- description: Get details for a specific contact including balance and outstanding amounts
  hints:
    openWorld: false
    readOnly: true
  name: get-contact
- description: List sales invoices filtered by customer, status, or date range
  hints:
    openWorld: false
    readOnly: true
  name: list-sales-invoices
- description: Create a new sales invoice with line items, due date, and customer reference
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-sales-invoice
- description: Get full details of a sales invoice including line items and payment status
  hints:
    openWorld: false
    readOnly: true
  name: get-sales-invoice
- description: Record a payment received against a sales invoice
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: record-sales-payment
- description: List purchase invoices (supplier bills) with filtering options
  hints:
    openWorld: false
    readOnly: true
  name: list-purchase-invoices
- description: Create a new purchase invoice (supplier bill) in Sage Accounting
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-purchase-invoice
- description: List bank accounts connected to the Sage Accounting business
  hints:
    openWorld: false
    readOnly: true
  name: list-bank-accounts
- description: List products and services in the Sage catalog
  hints:
    openWorld: false
    readOnly: true
  name: list-products
- description: Create a new product or service in Sage Accounting
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-product
- description: List chart of accounts (ledger accounts) for financial reporting
  hints:
    openWorld: false
    readOnly: true
  name: list-ledger-accounts
- description: List configured tax rates for invoice line items
  hints:
    openWorld: false
    readOnly: true
  name: list-tax-rates
---
