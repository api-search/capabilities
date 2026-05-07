---
categories: []
consumed_apis: []
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
- list sales invoices
- record a payment received for a sales invoice
- individual sales invoice
- list ledger accounts
- create a new customer or supplier contact in sage accounting
- list sales invoices with filtering by customer, status, and date
- get contact
- accounting
- create product
- list products
- record a payment received against a sales invoice
- create a new purchase invoice (supplier bill) in sage accounting
- sales invoice management
- create contact
- business management
- cloud software
- customer and supplier contact management
- list bank accounts
- list customers and suppliers in sage accounting
- list bank accounts connected to the sage accounting business
- create a new sales invoice
- chart of accounts
- create a new sales invoice with line items, due date, and customer reference
- create a new customer or supplier
- create a new purchase invoice
- update contact details
- product and service catalog
- create a new product or service
- purchase invoice (supplier bill) management
- list purchase invoices (supplier bills) with filtering options
- get full details of a sales invoice including line items and payment status
- list tax rates
- finance
- hr
- get details for a specific contact including balance and outstanding amounts
- payroll
- list sales invoices filtered by customer, status, or date range
- list configured tax rates for invoice line items
- individual contact operations
- list contacts
- list customers and suppliers
- tax rates
- record sales payment
- list configured tax rates
- create purchase invoice
- list purchase invoices
- bank account management
- list chart of accounts (ledger accounts) for financial reporting
- create a new product or service in sage accounting
- invoicing
- erp
- get sales invoice
- payments
- list products and services
- get contact details
- update contact
- sales invoice payments
- get sales invoice details
- list products and services in the sage catalog
slug: accounting-and-finance
source_filename: accounting-and-finance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Sage Accounting and Finance\n  description: Unified workflow for accounting and financial management using Sage Accounting API v3.1. Covers contacts, invoicing,\n    payment recording, bank reconciliation, and financial reporting. Used by accountants, bookkeepers, and finance teams to\n    manage business finances.\n  tags:\n  - Accounting\n  - ERP\n  - Finance\n  - Invoicing\n  - Payments\n  - Cloud Software\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SAGE_ACCESS_TOKEN: SAGE_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: sage-accounting\n    baseUri: https://api.accounting.sage.com/v3.1\n    description: Sage Accounting API v3.1\n    authentication:\n      type: bearer\n      token: '{{SAGE_ACCESS_TOKEN}}'\n    resources:\n    - name: contacts\n      path: /contacts\n      description: Customer and supplier contact management\n      operations:\n      - name: list-contacts\n\
  \        method: GET\n        description: List customer and supplier contacts\n        inputParameters:\n        - name: contact_type_ids\n          in: query\n          type: string\n          required: false\n          description: 'Filter by contact type: CUSTOMER or SUPPLIER'\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search by name or reference\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-contact\n        method: POST\n        description: Create a new customer or supplier contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            contact:\n\
  \              name: '{{tools.name}}'\n              contact_type_ids: '{{tools.contact_type_ids}}'\n              email: '{{tools.email}}'\n    - name: contact-detail\n      path: /contacts/{key}\n      description: Individual contact operations\n      operations:\n      - name: get-contact\n        method: GET\n        description: Get contact details by ID\n        inputParameters:\n        - name: key\n          in: path\n          type: string\n          required: true\n          description: Contact unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-contact\n        method: PUT\n        description: Update a contact's details\n        inputParameters:\n        - name: key\n          in: path\n          type: string\n          required: true\n          description: Contact unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            contact:\n              name: '{{tools.name}}'\n              email: '{{tools.email}}'\n    - name: sales-invoices\n      path: /sales_invoices\n      description: Sales invoice management\n      operations:\n      - name: list-sales-invoices\n        method: GET\n        description: List sales invoices with optional filtering\n        inputParameters:\n        - name: contact_id\n          in: query\n          type: string\n          required: false\n          description: Filter by customer contact ID\n        - name: status_id\n          in: query\n          type: string\n          required: false\n          description: 'Filter by status: DRAFT, SENT, PAID, VOID'\n        - name: from_date\n          in: query\n          type: string\n          required: false\n          description: Filter from date (YYYY-MM-DD)\n        - name: to_date\n          in: query\n          type:\
  \ string\n          required: false\n          description: Filter to date (YYYY-MM-DD)\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-sales-invoice\n        method: POST\n        description: Create a new sales invoice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            sales_invoice:\n              contact_id: '{{tools.contact_id}}'\n              date: '{{tools.date}}'\n              due_date: '{{tools.due_date}}'\n              reference: '{{tools.reference}}'\n              line_items: '{{tools.line_items}}'\n    - name: sales-invoice-detail\n      path: /sales_invoices/{key}\n      description: Individual sales\
  \ invoice operations\n      operations:\n      - name: get-sales-invoice\n        method: GET\n        description: Get sales invoice details\n        inputParameters:\n        - name: key\n          in: path\n          type: string\n          required: true\n          description: Invoice unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sales-invoice-payments\n      path: /sales_invoices/{key}/payments\n      description: Sales invoice payment recording\n      operations:\n      - name: record-sales-payment\n        method: POST\n        description: Record a payment received for a sales invoice\n        inputParameters:\n        - name: key\n          in: path\n          type: string\n          required: true\n          description: Invoice ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      \
  \  body:\n          type: json\n          data:\n            payment:\n              payment_type_id: '{{tools.payment_type_id}}'\n              bank_account_id: '{{tools.bank_account_id}}'\n              date: '{{tools.date}}'\n              amount: '{{tools.amount}}'\n    - name: purchase-invoices\n      path: /purchase_invoices\n      description: Purchase invoice management\n      operations:\n      - name: list-purchase-invoices\n        method: GET\n        description: List purchase invoices (supplier bills)\n        inputParameters:\n        - name: contact_id\n          in: query\n          type: string\n          required: false\n          description: Filter by supplier contact ID\n        - name: status_id\n          in: query\n          type: string\n          required: false\n          description: Filter by status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-purchase-invoice\n\
  \        method: POST\n        description: Create a new purchase invoice (supplier bill)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            purchase_invoice:\n              contact_id: '{{tools.contact_id}}'\n              date: '{{tools.date}}'\n              due_date: '{{tools.due_date}}'\n              line_items: '{{tools.line_items}}'\n    - name: bank-accounts\n      path: /bank_accounts\n      description: Bank account management\n      operations:\n      - name: list-bank-accounts\n        method: GET\n        description: List bank accounts connected to the business\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: products\n      path: /products\n      description: Product and service catalog\n      operations:\n      - name: list-products\n    \
  \    method: GET\n        description: List products and services\n        inputParameters:\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search by product name\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-product\n        method: POST\n        description: Create a new product or service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            product:\n              description: '{{tools.description}}'\n              item_code: '{{tools.item_code}}'\n    - name: tax-rates\n      path: /tax_rates\n      description: Tax rate configuration\n      operations:\n\
  \      - name: list-tax-rates\n        method: GET\n        description: List configured tax rates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ledger-accounts\n      path: /ledger_accounts\n      description: Chart of accounts\n      operations:\n      - name: list-ledger-accounts\n        method: GET\n        description: List ledger accounts (chart of accounts)\n        inputParameters:\n        - name: visible_in\n          in: query\n          type: string\n          required: false\n          description: Filter by visibility context\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: accounting-finance-api\n    description: Unified REST API for Sage accounting and finance management.\n    resources:\n    - path: /v1/contacts\n      name: contacts\n    \
  \  description: Customer and supplier contact management\n      operations:\n      - method: GET\n        name: list-contacts\n        description: List customers and suppliers\n        call: sage-accounting.list-contacts\n        with:\n          contact_type_ids: rest.contact_type_ids\n          search: rest.search\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-contact\n        description: Create a new customer or supplier\n        call: sage-accounting.create-contact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/contacts/{id}\n      name: contact-detail\n      description: Individual contact operations\n      operations:\n      - method: GET\n        name: get-contact\n        description: Get contact details\n        call: sage-accounting.get-contact\n        with:\n          key: rest.id\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n      - method: PUT\n        name: update-contact\n        description: Update contact details\n        call: sage-accounting.update-contact\n        with:\n          key: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sales-invoices\n      name: sales-invoices\n      description: Sales invoice management\n      operations:\n      - method: GET\n        name: list-sales-invoices\n        description: List sales invoices with filtering by customer, status, and date\n        call: sage-accounting.list-sales-invoices\n        with:\n          contact_id: rest.contact_id\n          status_id: rest.status_id\n          from_date: rest.from_date\n          to_date: rest.to_date\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-sales-invoice\n        description: Create a new sales invoice\n        call: sage-accounting.create-sales-invoice\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sales-invoices/{id}\n      name: sales-invoice-detail\n      description: Individual sales invoice\n      operations:\n      - method: GET\n        name: get-sales-invoice\n        description: Get sales invoice details\n        call: sage-accounting.get-sales-invoice\n        with:\n          key: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sales-invoices/{id}/payments\n      name: sales-invoice-payments\n      description: Sales invoice payments\n      operations:\n      - method: POST\n        name: record-sales-payment\n        description: Record a payment received for a sales invoice\n        call: sage-accounting.record-sales-payment\n        with:\n          key: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/purchase-invoices\n      name: purchase-invoices\n      description: Purchase\
  \ invoice (supplier bill) management\n      operations:\n      - method: GET\n        name: list-purchase-invoices\n        description: List purchase invoices\n        call: sage-accounting.list-purchase-invoices\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-purchase-invoice\n        description: Create a new purchase invoice\n        call: sage-accounting.create-purchase-invoice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bank-accounts\n      name: bank-accounts\n      description: Bank account management\n      operations:\n      - method: GET\n        name: list-bank-accounts\n        description: List bank accounts\n        call: sage-accounting.list-bank-accounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/products\n      name: products\n      description: Product and service catalog\n      operations:\n      - method:\
  \ GET\n        name: list-products\n        description: List products and services\n        call: sage-accounting.list-products\n        with:\n          search: rest.search\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-product\n        description: Create a new product or service\n        call: sage-accounting.create-product\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ledger-accounts\n      name: ledger-accounts\n      description: Chart of accounts\n      operations:\n      - method: GET\n        name: list-ledger-accounts\n        description: List ledger accounts\n        call: sage-accounting.list-ledger-accounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tax-rates\n      name: tax-rates\n      description: Tax rates\n      operations:\n      - method: GET\n        name: list-tax-rates\n \
  \       description: List configured tax rates\n        call: sage-accounting.list-tax-rates\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: accounting-finance-mcp\n    transport: http\n    description: MCP server for AI-assisted accounting and financial management with Sage Accounting.\n    tools:\n    - name: list-contacts\n      description: List customers and suppliers in Sage Accounting\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sage-accounting.list-contacts\n      with:\n        contact_type_ids: tools.contact_type_ids\n        search: tools.search\n        page: tools.page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-contact\n      description: Create a new customer or supplier contact in Sage Accounting\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: sage-accounting.create-contact\n\
  \      with:\n        name: tools.name\n        contact_type_ids: tools.contact_type_ids\n        email: tools.email\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-contact\n      description: Get details for a specific contact including balance and outstanding amounts\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sage-accounting.get-contact\n      with:\n        key: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-sales-invoices\n      description: List sales invoices filtered by customer, status, or date range\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sage-accounting.list-sales-invoices\n      with:\n        contact_id: tools.contact_id\n        status_id: tools.status_id\n        from_date: tools.from_date\n        to_date: tools.to_date\n        page: tools.page\n      outputParameters:\n      - type: object\n        mapping: $.\n   \
  \ - name: create-sales-invoice\n      description: Create a new sales invoice with line items, due date, and customer reference\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: sage-accounting.create-sales-invoice\n      with:\n        contact_id: tools.contact_id\n        date: tools.date\n        due_date: tools.due_date\n        reference: tools.reference\n        line_items: tools.line_items\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-sales-invoice\n      description: Get full details of a sales invoice including line items and payment status\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sage-accounting.get-sales-invoice\n      with:\n        key: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: record-sales-payment\n      description: Record a payment received against a sales invoice\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: sage-accounting.record-sales-payment\n      with:\n        key: tools.invoice_id\n        payment_type_id: tools.payment_type_id\n        bank_account_id: tools.bank_account_id\n        date: tools.date\n        amount: tools.amount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-purchase-invoices\n      description: List purchase invoices (supplier bills) with filtering options\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sage-accounting.list-purchase-invoices\n      with:\n        contact_id: tools.contact_id\n        status_id: tools.status_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-purchase-invoice\n      description: Create a new purchase invoice (supplier bill) in Sage Accounting\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: sage-accounting.create-purchase-invoice\n\
  \      with:\n        contact_id: tools.contact_id\n        date: tools.date\n        due_date: tools.due_date\n        line_items: tools.line_items\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-bank-accounts\n      description: List bank accounts connected to the Sage Accounting business\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sage-accounting.list-bank-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-products\n      description: List products and services in the Sage catalog\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sage-accounting.list-products\n      with:\n        search: tools.search\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-product\n      description: Create a new product or service in Sage Accounting\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ false\n      call: sage-accounting.create-product\n      with:\n        description: tools.description\n        item_code: tools.item_code\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-ledger-accounts\n      description: List chart of accounts (ledger accounts) for financial reporting\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sage-accounting.list-ledger-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tax-rates\n      description: List configured tax rates for invoice line items\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sage-accounting.list-tax-rates\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
