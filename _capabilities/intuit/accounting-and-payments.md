---
api_specs:
- filename: quickbooks-accounting.yml
  format: yaml
  label: quickbooks-accounting
  slug: quickbooks-accounting
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/intuit/refs/heads/main/openapi/quickbooks-accounting.yml
categories:
- payments
consumed_apis:
- quickbooks-accounting
description: Unified workflow for small business accounting automation combining QuickBooks Online invoice, customer, item, and payment management. Used by accountants, bookkeepers, and business owners to automate financial workflows.
layout: capability
name: Intuit Accounting and Payments
operations:
- description: Create a new invoice.
  method: POST
  name: create-invoice
  path: /v1/invoices
- description: Retrieve an invoice by ID.
  method: GET
  name: read-invoice
  path: /v1/invoices/{invoiceId}
- description: Email an invoice to the customer.
  method: POST
  name: send-invoice
  path: /v1/invoices/{invoiceId}/send
- description: Void an existing invoice.
  method: POST
  name: void-invoice
  path: /v1/invoices/{invoiceId}/void
- description: Retrieve invoice as PDF.
  method: GET
  name: get-invoice-pdf
  path: /v1/invoices/{invoiceId}/pdf
- description: Create a new customer.
  method: POST
  name: create-customer
  path: /v1/customers
- description: Retrieve a customer by ID.
  method: GET
  name: read-customer
  path: /v1/customers/{customerId}
- description: Create a new item.
  method: POST
  name: create-item
  path: /v1/items
- description: Retrieve an item by ID.
  method: GET
  name: read-item
  path: /v1/items/{itemId}
- description: Record a new payment.
  method: POST
  name: create-payment
  path: /v1/payments
- description: Retrieve a payment by ID.
  method: GET
  name: read-payment
  path: /v1/payments/{paymentId}
- description: Query QuickBooks entities.
  method: GET
  name: query-entities
  path: /v1/query
personas: []
provider_name: Intuit
provider_slug: intuit
search_terms:
- update an existing quickbooks invoice.
- payments
- void invoice
- custom fields
- create customer
- single payment operations.
- void an invoice.
- create a new customer.
- retrieve a quickbooks invoice by id.
- accounting
- send an invoice via email.
- single item operations.
- retrieve a quickbooks item by id.
- update an existing quickbooks item.
- create payment
- retrieve a quickbooks payment by id.
- intuit
- taxes
- retrieve an invoice by id.
- retrieve a customer by id.
- void a quickbooks invoice.
- update a quickbooks customer record.
- create invoice
- create item
- tax preparation
- time tracking
- payment management.
- retrieve an item by id.
- single customer operations.
- customer management.
- invoicing
- record a customer payment in quickbooks.
- retrieve a quickbooks customer by id.
- send invoice
- query quickbooks entities.
- financial
- create a new item.
- read item
- update invoice
- payroll
- single invoice operations.
- email an invoice to the customer.
- read invoice
- query entities
- product and service catalog.
- record a new payment.
- send a quickbooks invoice via email.
- void payment
- financial services
- create a new invoice.
- project management
- small business
- update customer
- void a quickbooks payment.
- get pdf of a quickbooks invoice.
- update payment
- invoice lifecycle management.
- entity query endpoint.
- read payment
- query quickbooks entities using sql-like syntax.
- void an existing invoice.
- retrieve invoice as pdf.
- tax
- create a new customer in quickbooks.
- get invoice pdf.
- create a new product or service item.
- update item
- sales tax
- read customer
- retrieve a payment by id.
- get invoice pdf
- create a new quickbooks invoice.
- update an existing quickbooks payment.
slug: accounting-and-payments
source_filename: accounting-and-payments.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Intuit Accounting and Payments\"\n  description: \"Unified workflow for small business accounting automation combining QuickBooks Online invoice, customer, item, and payment management. Used by accountants, bookkeepers, and business owners to automate financial workflows.\"\n  tags:\n    - Intuit\n    - Accounting\n    - Invoicing\n    - Payments\n    - Small Business\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      INTUIT_OAUTH_ACCESS_TOKEN: INTUIT_OAUTH_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: quickbooks-accounting\n      location: ./shared/quickbooks-accounting.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: intuit-accounting-api\n      description: \"Unified REST API for Intuit QuickBooks accounting and payment operations.\"\n      resources:\n        - path: /v1/invoices\n          name: invoices\n          description: \"Invoice\
  \ lifecycle management.\"\n          operations:\n            - method: POST\n              name: create-invoice\n              description: \"Create a new invoice.\"\n              call: \"quickbooks-accounting.create-invoice\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/invoices/{invoiceId}\n          name: invoice-detail\n          description: \"Single invoice operations.\"\n          operations:\n            - method: GET\n              name: read-invoice\n              description: \"Retrieve an invoice by ID.\"\n              call: \"quickbooks-accounting.read-invoice\"\n              with:\n                invoiceId: \"rest.invoiceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/invoices/{invoiceId}/send\n          name: invoice-send\n          description: \"Send an invoice via email.\"\n          operations:\n            - method:\
  \ POST\n              name: send-invoice\n              description: \"Email an invoice to the customer.\"\n              call: \"quickbooks-accounting.send-invoice\"\n              with:\n                invoiceId: \"rest.invoiceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/invoices/{invoiceId}/void\n          name: invoice-void\n          description: \"Void an invoice.\"\n          operations:\n            - method: POST\n              name: void-invoice\n              description: \"Void an existing invoice.\"\n              call: \"quickbooks-accounting.void-invoice\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/invoices/{invoiceId}/pdf\n          name: invoice-pdf\n          description: \"Get invoice PDF.\"\n          operations:\n            - method: GET\n              name: get-invoice-pdf\n              description: \"Retrieve\
  \ invoice as PDF.\"\n              call: \"quickbooks-accounting.get-invoice-pdf\"\n              with:\n                invoiceId: \"rest.invoiceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/customers\n          name: customers\n          description: \"Customer management.\"\n          operations:\n            - method: POST\n              name: create-customer\n              description: \"Create a new customer.\"\n              call: \"quickbooks-accounting.create-customer\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/customers/{customerId}\n          name: customer-detail\n          description: \"Single customer operations.\"\n          operations:\n            - method: GET\n              name: read-customer\n              description: \"Retrieve a customer by ID.\"\n              call: \"quickbooks-accounting.read-customer\"\
  \n              with:\n                customerId: \"rest.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/items\n          name: items\n          description: \"Product and service catalog.\"\n          operations:\n            - method: POST\n              name: create-item\n              description: \"Create a new item.\"\n              call: \"quickbooks-accounting.create-item\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/items/{itemId}\n          name: item-detail\n          description: \"Single item operations.\"\n          operations:\n            - method: GET\n              name: read-item\n              description: \"Retrieve an item by ID.\"\n              call: \"quickbooks-accounting.read-item\"\n              with:\n                itemId: \"rest.itemId\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n        - path: /v1/payments\n          name: payments\n          description: \"Payment management.\"\n          operations:\n            - method: POST\n              name: create-payment\n              description: \"Record a new payment.\"\n              call: \"quickbooks-accounting.create-payment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/payments/{paymentId}\n          name: payment-detail\n          description: \"Single payment operations.\"\n          operations:\n            - method: GET\n              name: read-payment\n              description: \"Retrieve a payment by ID.\"\n              call: \"quickbooks-accounting.read-payment\"\n              with:\n                paymentId: \"rest.paymentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/query\n          name: query\n\
  \          description: \"Entity query endpoint.\"\n          operations:\n            - method: GET\n              name: query-entities\n              description: \"Query QuickBooks entities.\"\n              call: \"quickbooks-accounting.query-entities\"\n              with:\n                query: \"rest.query\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: intuit-accounting-mcp\n      transport: http\n      description: \"MCP server for AI-assisted QuickBooks accounting and payment management.\"\n      tools:\n        - name: create-invoice\n          description: \"Create a new QuickBooks invoice.\"\n          hints:\n            readOnly: false\n          call: \"quickbooks-accounting.create-invoice\"\n          with:\n            customer_ref: \"tools.customer_ref\"\n            line_items: \"tools.line_items\"\n          outputParameters:\n            - type: object\n \
  \             mapping: \"$.\"\n        - name: read-invoice\n          description: \"Retrieve a QuickBooks invoice by ID.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"quickbooks-accounting.read-invoice\"\n          with:\n            invoiceId: \"tools.invoiceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-invoice\n          description: \"Update an existing QuickBooks invoice.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"quickbooks-accounting.update-invoice\"\n          with:\n            invoice_id: \"tools.invoice_id\"\n            sync_token: \"tools.sync_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-invoice\n          description: \"Send a QuickBooks invoice via email.\"\n          hints:\n            readOnly: false\n          call: \"quickbooks-accounting.send-invoice\"\
  \n          with:\n            invoiceId: \"tools.invoiceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: void-invoice\n          description: \"Void a QuickBooks invoice.\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"quickbooks-accounting.void-invoice\"\n          with:\n            invoice_id: \"tools.invoice_id\"\n            sync_token: \"tools.sync_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-invoice-pdf\n          description: \"Get PDF of a QuickBooks invoice.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"quickbooks-accounting.get-invoice-pdf\"\n          with:\n            invoiceId: \"tools.invoiceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-entities\n          description:\
  \ \"Query QuickBooks entities using SQL-like syntax.\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"quickbooks-accounting.query-entities\"\n          with:\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-customer\n          description: \"Create a new customer in QuickBooks.\"\n          hints:\n            readOnly: false\n          call: \"quickbooks-accounting.create-customer\"\n          with:\n            display_name: \"tools.display_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: read-customer\n          description: \"Retrieve a QuickBooks customer by ID.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"quickbooks-accounting.read-customer\"\n          with:\n            customerId: \"tools.customerId\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-customer\n          description: \"Update a QuickBooks customer record.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"quickbooks-accounting.update-customer\"\n          with:\n            customer_id: \"tools.customer_id\"\n            sync_token: \"tools.sync_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-item\n          description: \"Create a new product or service item.\"\n          hints:\n            readOnly: false\n          call: \"quickbooks-accounting.create-item\"\n          with:\n            name: \"tools.name\"\n            type: \"tools.type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: read-item\n          description: \"Retrieve a QuickBooks item by ID.\"\n          hints:\n\
  \            readOnly: true\n            idempotent: true\n          call: \"quickbooks-accounting.read-item\"\n          with:\n            itemId: \"tools.itemId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-item\n          description: \"Update an existing QuickBooks item.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"quickbooks-accounting.update-item\"\n          with:\n            item_id: \"tools.item_id\"\n            sync_token: \"tools.sync_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-payment\n          description: \"Record a customer payment in QuickBooks.\"\n          hints:\n            readOnly: false\n          call: \"quickbooks-accounting.create-payment\"\n          with:\n            customer_ref: \"tools.customer_ref\"\n            total_amount: \"tools.total_amount\"\n     \
  \     outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: read-payment\n          description: \"Retrieve a QuickBooks payment by ID.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"quickbooks-accounting.read-payment\"\n          with:\n            paymentId: \"tools.paymentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-payment\n          description: \"Update an existing QuickBooks payment.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"quickbooks-accounting.update-payment\"\n          with:\n            payment_id: \"tools.payment_id\"\n            sync_token: \"tools.sync_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: void-payment\n          description: \"Void a QuickBooks payment.\"\n          hints:\n     \
  \       readOnly: false\n            destructive: true\n          call: \"quickbooks-accounting.void-payment\"\n          with:\n            payment_id: \"tools.payment_id\"\n            sync_token: \"tools.sync_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/intuit/refs/heads/main/capabilities/accounting-and-payments.yaml
tags:
- Intuit
- Accounting
- Invoicing
- Payments
- Small Business
tools:
- description: Create a new QuickBooks invoice.
  hints:
    readOnly: false
  name: create-invoice
- description: Retrieve a QuickBooks invoice by ID.
  hints:
    idempotent: true
    readOnly: true
  name: read-invoice
- description: Update an existing QuickBooks invoice.
  hints:
    idempotent: true
    readOnly: false
  name: update-invoice
- description: Send a QuickBooks invoice via email.
  hints:
    readOnly: false
  name: send-invoice
- description: Void a QuickBooks invoice.
  hints:
    destructive: true
    readOnly: false
  name: void-invoice
- description: Get PDF of a QuickBooks invoice.
  hints:
    idempotent: true
    readOnly: true
  name: get-invoice-pdf
- description: Query QuickBooks entities using SQL-like syntax.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: query-entities
- description: Create a new customer in QuickBooks.
  hints:
    readOnly: false
  name: create-customer
- description: Retrieve a QuickBooks customer by ID.
  hints:
    idempotent: true
    readOnly: true
  name: read-customer
- description: Update a QuickBooks customer record.
  hints:
    idempotent: true
    readOnly: false
  name: update-customer
- description: Create a new product or service item.
  hints:
    readOnly: false
  name: create-item
- description: Retrieve a QuickBooks item by ID.
  hints:
    idempotent: true
    readOnly: true
  name: read-item
- description: Update an existing QuickBooks item.
  hints:
    idempotent: true
    readOnly: false
  name: update-item
- description: Record a customer payment in QuickBooks.
  hints:
    readOnly: false
  name: create-payment
- description: Retrieve a QuickBooks payment by ID.
  hints:
    idempotent: true
    readOnly: true
  name: read-payment
- description: Update an existing QuickBooks payment.
  hints:
    idempotent: true
    readOnly: false
  name: update-payment
- description: Void a QuickBooks payment.
  hints:
    destructive: true
    readOnly: false
  name: void-payment
---
