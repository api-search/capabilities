---
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
- retrieve a customer by id.
- void an existing invoice.
- read item
- send an invoice via email.
- project management
- time tracking
- create item
- invoice lifecycle management.
- get invoice pdf
- void invoice
- void a quickbooks payment.
- accounting
- intuit
- query entities
- product and service catalog.
- void payment
- single item operations.
- create a new customer in quickbooks.
- update payment
- retrieve a quickbooks item by id.
- single customer operations.
- create a new invoice.
- send invoice
- void an invoice.
- send a quickbooks invoice via email.
- create a new quickbooks invoice.
- retrieve an item by id.
- update an existing quickbooks payment.
- email an invoice to the customer.
- taxes
- single invoice operations.
- entity query endpoint.
- custom fields
- update customer
- get pdf of a quickbooks invoice.
- payment management.
- update an existing quickbooks item.
- void a quickbooks invoice.
- get invoice pdf.
- tax
- retrieve a quickbooks payment by id.
- create a new customer.
- create payment
- payroll
- retrieve an invoice by id.
- update invoice
- update a quickbooks customer record.
- retrieve invoice as pdf.
- create a new item.
- update item
- query quickbooks entities.
- create customer
- customer management.
- create invoice
- single payment operations.
- retrieve a payment by id.
- tax preparation
- update an existing quickbooks invoice.
- small business
- invoicing
- read customer
- record a new payment.
- payments
- financial services
- record a customer payment in quickbooks.
- query quickbooks entities using sql-like syntax.
- read payment
- read invoice
- retrieve a quickbooks customer by id.
- sales tax
- retrieve a quickbooks invoice by id.
- financial
- create a new product or service item.
slug: accounting-and-payments
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
