---
categories:
- payments
consumed_apis: []
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
- read payment
- invoice lifecycle management.
- create a new customer.
- query quickbooks entities.
- create customer
- tax preparation
- update an existing quickbooks payment.
- accounting
- time tracking
- send a quickbooks invoice via email.
- update item
- create a new product or service item.
- retrieve an invoice by id.
- void an existing invoice.
- read customer
- get invoice pdf.
- void an invoice.
- single payment operations.
- update an existing quickbooks item.
- void payment
- create item
- update a quickbooks customer record.
- create a new item.
- read item
- send an invoice via email.
- email an invoice to the customer.
- retrieve a quickbooks invoice by id.
- void invoice
- single customer operations.
- create payment
- payment management.
- project management
- query entities
- intuit
- create a new customer in quickbooks.
- sales tax
- entity query endpoint.
- update payment
- create invoice
- customer management.
- get pdf of a quickbooks invoice.
- small business
- financial services
- payroll
- retrieve a payment by id.
- update an existing quickbooks invoice.
- get invoice pdf
- send invoice
- retrieve invoice as pdf.
- void a quickbooks invoice.
- single item operations.
- tax
- query quickbooks entities using sql-like syntax.
- retrieve a customer by id.
- custom fields
- update invoice
- invoicing
- update customer
- product and service catalog.
- record a customer payment in quickbooks.
- financial
- retrieve a quickbooks payment by id.
- payments
- retrieve an item by id.
- record a new payment.
- read invoice
- taxes
- void a quickbooks payment.
- retrieve a quickbooks item by id.
- create a new quickbooks invoice.
- retrieve a quickbooks customer by id.
- create a new invoice.
- single invoice operations.
slug: accounting-and-payments
source_filename: accounting-and-payments.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Intuit Accounting and Payments\n  description: Unified workflow for small business accounting automation combining QuickBooks Online invoice, customer, item,\n    and payment management. Used by accountants, bookkeepers, and business owners to automate financial workflows.\n  tags:\n  - Intuit\n  - Accounting\n  - Invoicing\n  - Payments\n  - Small Business\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    INTUIT_OAUTH_ACCESS_TOKEN: INTUIT_OAUTH_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: quickbooks-accounting\n    baseUri: https://quickbooks.api.intuit.com/v3/company/{realmId}\n    description: QuickBooks Online Accounting API for managing invoices, customers, items, and payments.\n    authentication:\n      type: bearer\n      token: '{{INTUIT_OAUTH_ACCESS_TOKEN}}'\n    resources:\n    - name: invoices\n      path: /invoice\n      description: Manage sales invoices and\
  \ accounts receivable transactions.\n      operations:\n      - name: create-invoice\n        method: POST\n        description: Create a new invoice with customer reference and line items.\n        inputParameters:\n        - name: minorversion\n          in: query\n          type: integer\n          required: false\n          description: API minor version for backward-compatible features.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            CustomerRef: '{{tools.customer_ref}}'\n            Line: '{{tools.line_items}}'\n      - name: read-invoice\n        method: GET\n        description: Retrieve an invoice by its unique ID.\n        inputParameters:\n        - name: invoiceId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the invoice.\n        - name: minorversion\n     \
  \     in: query\n          type: integer\n          required: false\n          description: API minor version.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-invoice\n        method: POST\n        description: Update an existing invoice with full sparse update support.\n        inputParameters:\n        - name: minorversion\n          in: query\n          type: integer\n          required: false\n          description: API minor version.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Id: '{{tools.invoice_id}}'\n            SyncToken: '{{tools.sync_token}}'\n            sparse: true\n      - name: send-invoice\n        method: POST\n        description: Send an invoice via email to the customer.\n        inputParameters:\n        - name: invoiceId\n\
  \          in: path\n          type: string\n          required: true\n          description: The invoice ID to send.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: void-invoice\n        method: POST\n        description: Void an existing invoice.\n        inputParameters:\n        - name: minorversion\n          in: query\n          type: integer\n          required: false\n          description: API minor version.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Id: '{{tools.invoice_id}}'\n            SyncToken: '{{tools.sync_token}}'\n      - name: get-invoice-pdf\n        method: GET\n        description: Retrieve the PDF representation of an invoice.\n        inputParameters:\n        - name: invoiceId\n          in: path\n          type: string\n\
  \          required: true\n          description: The invoice ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customers\n      path: /customer\n      description: Manage customer records and contact information.\n      operations:\n      - name: create-customer\n        method: POST\n        description: Create a new customer record.\n        inputParameters:\n        - name: minorversion\n          in: query\n          type: integer\n          required: false\n          description: API minor version.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            DisplayName: '{{tools.display_name}}'\n      - name: read-customer\n        method: GET\n        description: Retrieve a customer by ID.\n        inputParameters:\n        - name: customerId\n         \
  \ in: path\n          type: string\n          required: true\n          description: The customer ID.\n        - name: minorversion\n          in: query\n          type: integer\n          required: false\n          description: API minor version.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-customer\n        method: POST\n        description: Update an existing customer record.\n        inputParameters:\n        - name: minorversion\n          in: query\n          type: integer\n          required: false\n          description: API minor version.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Id: '{{tools.customer_id}}'\n            SyncToken: '{{tools.sync_token}}'\n            sparse: true\n    - name: items\n      path: /item\n      description:\
  \ Manage products and services catalog.\n      operations:\n      - name: create-item\n        method: POST\n        description: Create a new item (product or service).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Name: '{{tools.name}}'\n            Type: '{{tools.type}}'\n      - name: read-item\n        method: GET\n        description: Retrieve an item by ID.\n        inputParameters:\n        - name: itemId\n          in: path\n          type: string\n          required: true\n          description: The item ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-item\n        method: POST\n        description: Update an existing item.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n        body:\n          type: json\n          data:\n            Id: '{{tools.item_id}}'\n            SyncToken: '{{tools.sync_token}}'\n            sparse: true\n    - name: payments\n      path: /payment\n      description: Record and manage customer payments against invoices.\n      operations:\n      - name: create-payment\n        method: POST\n        description: Record a new payment from a customer.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            CustomerRef: '{{tools.customer_ref}}'\n            TotalAmt: '{{tools.total_amount}}'\n      - name: read-payment\n        method: GET\n        description: Retrieve a payment by ID.\n        inputParameters:\n        - name: paymentId\n          in: path\n          type: string\n          required: true\n          description: The payment ID.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-payment\n        method: POST\n        description: Update an existing payment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Id: '{{tools.payment_id}}'\n            SyncToken: '{{tools.sync_token}}'\n            sparse: true\n      - name: void-payment\n        method: POST\n        description: Void an existing payment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Id: '{{tools.payment_id}}'\n            SyncToken: '{{tools.sync_token}}'\n    - name: query\n      path: /query\n      description: Query QuickBooks entities using SQL-like syntax.\n      operations:\n      -\
  \ name: query-entities\n        method: GET\n        description: Query entities using QuickBooks query language.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: SQL-like query string.\n        - name: minorversion\n          in: query\n          type: integer\n          required: false\n          description: API minor version.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: intuit-accounting-api\n    description: Unified REST API for Intuit QuickBooks accounting and payment operations.\n    resources:\n    - path: /v1/invoices\n      name: invoices\n      description: Invoice lifecycle management.\n      operations:\n      - method: POST\n        name: create-invoice\n        description: Create a new invoice.\n        call: quickbooks-accounting.create-invoice\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices/{invoiceId}\n      name: invoice-detail\n      description: Single invoice operations.\n      operations:\n      - method: GET\n        name: read-invoice\n        description: Retrieve an invoice by ID.\n        call: quickbooks-accounting.read-invoice\n        with:\n          invoiceId: rest.invoiceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices/{invoiceId}/send\n      name: invoice-send\n      description: Send an invoice via email.\n      operations:\n      - method: POST\n        name: send-invoice\n        description: Email an invoice to the customer.\n        call: quickbooks-accounting.send-invoice\n        with:\n          invoiceId: rest.invoiceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices/{invoiceId}/void\n      name: invoice-void\n      description: Void an invoice.\n\
  \      operations:\n      - method: POST\n        name: void-invoice\n        description: Void an existing invoice.\n        call: quickbooks-accounting.void-invoice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices/{invoiceId}/pdf\n      name: invoice-pdf\n      description: Get invoice PDF.\n      operations:\n      - method: GET\n        name: get-invoice-pdf\n        description: Retrieve invoice as PDF.\n        call: quickbooks-accounting.get-invoice-pdf\n        with:\n          invoiceId: rest.invoiceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/customers\n      name: customers\n      description: Customer management.\n      operations:\n      - method: POST\n        name: create-customer\n        description: Create a new customer.\n        call: quickbooks-accounting.create-customer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/customers/{customerId}\n\
  \      name: customer-detail\n      description: Single customer operations.\n      operations:\n      - method: GET\n        name: read-customer\n        description: Retrieve a customer by ID.\n        call: quickbooks-accounting.read-customer\n        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/items\n      name: items\n      description: Product and service catalog.\n      operations:\n      - method: POST\n        name: create-item\n        description: Create a new item.\n        call: quickbooks-accounting.create-item\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/items/{itemId}\n      name: item-detail\n      description: Single item operations.\n      operations:\n      - method: GET\n        name: read-item\n        description: Retrieve an item by ID.\n        call: quickbooks-accounting.read-item\n        with:\n          itemId: rest.itemId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payments\n      name: payments\n      description: Payment management.\n      operations:\n      - method: POST\n        name: create-payment\n        description: Record a new payment.\n        call: quickbooks-accounting.create-payment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payments/{paymentId}\n      name: payment-detail\n      description: Single payment operations.\n      operations:\n      - method: GET\n        name: read-payment\n        description: Retrieve a payment by ID.\n        call: quickbooks-accounting.read-payment\n        with:\n          paymentId: rest.paymentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/query\n      name: query\n      description: Entity query endpoint.\n      operations:\n      - method: GET\n        name: query-entities\n        description: Query QuickBooks\
  \ entities.\n        call: quickbooks-accounting.query-entities\n        with:\n          query: rest.query\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: intuit-accounting-mcp\n    transport: http\n    description: MCP server for AI-assisted QuickBooks accounting and payment management.\n    tools:\n    - name: create-invoice\n      description: Create a new QuickBooks invoice.\n      hints:\n        readOnly: false\n      call: quickbooks-accounting.create-invoice\n      with:\n        customer_ref: tools.customer_ref\n        line_items: tools.line_items\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: read-invoice\n      description: Retrieve a QuickBooks invoice by ID.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: quickbooks-accounting.read-invoice\n      with:\n        invoiceId: tools.invoiceId\n      outputParameters:\n      - type: object\n \
  \       mapping: $.\n    - name: update-invoice\n      description: Update an existing QuickBooks invoice.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: quickbooks-accounting.update-invoice\n      with:\n        invoice_id: tools.invoice_id\n        sync_token: tools.sync_token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-invoice\n      description: Send a QuickBooks invoice via email.\n      hints:\n        readOnly: false\n      call: quickbooks-accounting.send-invoice\n      with:\n        invoiceId: tools.invoiceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: void-invoice\n      description: Void a QuickBooks invoice.\n      hints:\n        readOnly: false\n        destructive: true\n      call: quickbooks-accounting.void-invoice\n      with:\n        invoice_id: tools.invoice_id\n        sync_token: tools.sync_token\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: get-invoice-pdf\n      description: Get PDF of a QuickBooks invoice.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: quickbooks-accounting.get-invoice-pdf\n      with:\n        invoiceId: tools.invoiceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-entities\n      description: Query QuickBooks entities using SQL-like syntax.\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: quickbooks-accounting.query-entities\n      with:\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-customer\n      description: Create a new customer in QuickBooks.\n      hints:\n        readOnly: false\n      call: quickbooks-accounting.create-customer\n      with:\n        display_name: tools.display_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: read-customer\n      description:\
  \ Retrieve a QuickBooks customer by ID.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: quickbooks-accounting.read-customer\n      with:\n        customerId: tools.customerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-customer\n      description: Update a QuickBooks customer record.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: quickbooks-accounting.update-customer\n      with:\n        customer_id: tools.customer_id\n        sync_token: tools.sync_token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-item\n      description: Create a new product or service item.\n      hints:\n        readOnly: false\n      call: quickbooks-accounting.create-item\n      with:\n        name: tools.name\n        type: tools.type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: read-item\n      description: Retrieve a QuickBooks\
  \ item by ID.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: quickbooks-accounting.read-item\n      with:\n        itemId: tools.itemId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-item\n      description: Update an existing QuickBooks item.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: quickbooks-accounting.update-item\n      with:\n        item_id: tools.item_id\n        sync_token: tools.sync_token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-payment\n      description: Record a customer payment in QuickBooks.\n      hints:\n        readOnly: false\n      call: quickbooks-accounting.create-payment\n      with:\n        customer_ref: tools.customer_ref\n        total_amount: tools.total_amount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: read-payment\n      description: Retrieve a QuickBooks payment by\
  \ ID.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: quickbooks-accounting.read-payment\n      with:\n        paymentId: tools.paymentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-payment\n      description: Update an existing QuickBooks payment.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: quickbooks-accounting.update-payment\n      with:\n        payment_id: tools.payment_id\n        sync_token: tools.sync_token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: void-payment\n      description: Void a QuickBooks payment.\n      hints:\n        readOnly: false\n        destructive: true\n      call: quickbooks-accounting.void-payment\n      with:\n        payment_id: tools.payment_id\n        sync_token: tools.sync_token\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
