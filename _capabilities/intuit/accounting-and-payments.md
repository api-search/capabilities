---
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
- payment management.
- single customer operations.
- read item
- retrieve a customer by id.
- taxes
- tax preparation
- retrieve a quickbooks payment by id.
- create item
- create a new product or service item.
- single payment operations.
- update an existing quickbooks invoice.
- time tracking
- create invoice
- create a new invoice.
- void a quickbooks payment.
- tax
- customer management.
- update customer
- query entities
- entity query endpoint.
- retrieve invoice as pdf.
- create a new quickbooks invoice.
- single item operations.
- retrieve a quickbooks invoice by id.
- single invoice operations.
- update item
- create payment
- project management
- accounting
- intuit
- send a quickbooks invoice via email.
- invoicing
- get pdf of a quickbooks invoice.
- query quickbooks entities using sql-like syntax.
- update an existing quickbooks item.
- create a new customer.
- record a customer payment in quickbooks.
- void invoice
- record a new payment.
- update invoice
- create a new customer in quickbooks.
- query quickbooks entities.
- void an invoice.
- retrieve a quickbooks customer by id.
- invoice lifecycle management.
- financial
- update a quickbooks customer record.
- sales tax
- void an existing invoice.
- financial services
- email an invoice to the customer.
- retrieve an item by id.
- void payment
- retrieve an invoice by id.
- custom fields
- payments
- read payment
- send invoice
- update an existing quickbooks payment.
- get invoice pdf
- retrieve a quickbooks item by id.
- retrieve a payment by id.
- read customer
- update payment
- send an invoice via email.
- product and service catalog.
- payroll
- void a quickbooks invoice.
- read invoice
- get invoice pdf.
- create a new item.
- create customer
- small business
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
