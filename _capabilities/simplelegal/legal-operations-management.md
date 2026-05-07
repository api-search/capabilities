---
categories: []
consumed_apis: []
description: Unified legal operations management capability combining SimpleLegal's matter management, eBilling, vendor management, spend analytics, and user administration APIs into a single workflow. Designed for in-house legal operations teams, general counsel offices, and finance integrators building legal-to-finance data pipelines.
layout: capability
name: SimpleLegal Legal Operations Management
operations:
- description: List all legal matters with filtering and pagination
  method: GET
  name: list-matters
  path: /v1/matters
- description: Create a new legal matter
  method: POST
  name: create-matter
  path: /v1/matters
- description: Get a specific legal matter by ID
  method: GET
  name: get-matter
  path: /v1/matters/{id}
- description: Update matter fields (status, budget, counsel)
  method: PATCH
  name: update-matter
  path: /v1/matters/{id}
- description: List all invoices with filtering by status and matter
  method: GET
  name: list-invoices
  path: /v1/invoices
- description: Submit a new invoice for eBilling review
  method: POST
  name: create-invoice
  path: /v1/invoices
- description: Get a specific invoice by ID
  method: GET
  name: get-invoice
  path: /v1/invoices/{id}
- description: Update invoice status (approve, reject, hold)
  method: PATCH
  name: update-invoice
  path: /v1/invoices/{id}
- description: List all outside counsel and legal service vendors
  method: GET
  name: list-vendors
  path: /v1/vendors
- description: Add a new outside counsel or vendor
  method: POST
  name: create-vendor
  path: /v1/vendors
- description: Get a specific vendor by ID
  method: GET
  name: get-vendor
  path: /v1/vendors/{id}
- description: Update vendor information or status
  method: PATCH
  name: update-vendor
  path: /v1/vendors/{id}
- description: List all configured billing and cost codes
  method: GET
  name: list-cost-codes
  path: /v1/cost-codes
- description: List all platform users
  method: GET
  name: list-users
  path: /v1/users
- description: Create a new platform user
  method: POST
  name: create-user
  path: /v1/users
- description: List all recorded payments
  method: GET
  name: list-payments
  path: /v1/payments
- description: Record a payment for an approved invoice
  method: POST
  name: create-payment
  path: /v1/payments
personas: []
provider_name: SimpleLegal
provider_slug: simplelegal
search_terms:
- get details of a specific invoice including line items and approval status
- legal invoice ebilling and approval workflow
- individual invoice management
- create a new legal matter with name, practice area, budget, and counsel assignment
- list all recorded payments
- list all billing and cost codes available for invoice categorization
- vendor management
- individual vendor management
- ebilling
- record a payment for an approved invoice to track disbursements
- invoices
- legal matter lifecycle management
- legal spend management
- finance integration
- get a specific legal matter by id
- update invoice status (approve, reject, hold)
- create a new platform user
- record payment
- update vendor
- create payment
- billing and cost code catalog
- get matter
- enterprise legal management
- invoice payment recording
- list all legal matters with filtering and pagination
- update matter fields (status, budget, counsel)
- record a payment for an approved invoice
- list all legal matters with optional filtering by status or practice area
- update matter status, budget, or attorney assignments
- approve invoice
- get information about a specific vendor or outside counsel firm
- list matters
- create invoice
- outside counsel and legal vendor management
- list users
- create a new simplelegal platform user
- list all recorded invoice payments
- get a specific invoice by id
- update matter
- get vendor
- submit a new legal invoice for ebilling review and approval
- vendors
- list all invoices with filtering by status and matter
- get a specific vendor by id
- list all platform users
- approve an invoice and set the approved payment amount
- list vendors
- update invoice
- individual matter management
- create matter
- add a new outside counsel law firm or legal service provider
- list legal invoices with filtering by status, matter, or vendor
- create a new legal matter
- list all simplelegal platform users
- create user
- legal operations
- create vendor
- list cost codes
- matter management
- list invoices
- get invoice
- list all outside counsel and legal service vendors
- get detailed information about a specific legal matter by id
- list payments
- user account management
- update vendor information or status
- submit a new invoice for ebilling review
- add a new outside counsel or vendor
- list all configured billing and cost codes
slug: legal-operations-management
source_filename: legal-operations-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SimpleLegal Legal Operations Management\n  description: Unified legal operations management capability combining SimpleLegal's matter management, eBilling, vendor\n    management, spend analytics, and user administration APIs into a single workflow. Designed for in-house legal operations\n    teams, general counsel offices, and finance integrators building legal-to-finance data pipelines.\n  tags:\n  - eBilling\n  - Enterprise Legal Management\n  - Finance Integration\n  - Invoices\n  - Legal Operations\n  - Legal Spend Management\n  - Matter Management\n  - Vendors\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SIMPLELEGAL_USERNAME: SIMPLELEGAL_USERNAME\n    SIMPLELEGAL_PASSWORD: SIMPLELEGAL_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: simplelegal\n    baseUri: https://app.simplelegal.com/api/v1\n    description: SimpleLegal REST API for enterprise legal management\n  \
  \  authentication:\n      type: basic\n      username: '{{env.SIMPLELEGAL_USERNAME}}'\n      password: '{{env.SIMPLELEGAL_PASSWORD}}'\n    resources:\n    - name: matters\n      path: /matters\n      description: Legal matter management\n      operations:\n      - name: list-matters\n        method: GET\n        description: List all legal matters with pagination\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description: Results per page (max 100)\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status (open, closed, pending, on_hold)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-matter\n\
  \        method: POST\n        description: Create a new legal matter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            matter_number: '{{tools.matter_number}}'\n            status: '{{tools.status}}'\n            practice_area: '{{tools.practice_area}}'\n            description: '{{tools.description}}'\n            client: '{{tools.client}}'\n            budget: '{{tools.budget}}'\n      - name: get-matter\n        method: GET\n        description: Get a specific legal matter by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Matter ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-matter\n        method: PATCH\n \
  \       description: Update fields on an existing legal matter\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Matter ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            status: '{{tools.status}}'\n            budget: '{{tools.budget}}'\n            lead_attorney: '{{tools.lead_attorney}}'\n    - name: invoices\n      path: /invoices\n      description: Legal invoice eBilling management\n      operations:\n      - name: list-invoices\n        method: GET\n        description: List all invoices with pagination\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by invoice status\n        - name: matter_id\n          in: query\n          type: string\n   \
  \       required: false\n          description: Filter by matter ID\n        - name: vendor_id\n          in: query\n          type: string\n          required: false\n          description: Filter by vendor ID\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-invoice\n        method: POST\n        description: Submit a new invoice for processing\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            invoice_number: '{{tools.invoice_number}}'\n            matter_id: '{{tools.matter_id}}'\n            vendor_id: '{{tools.vendor_id}}'\n            total_amount: '{{tools.total_amount}}'\n            currency: '{{tools.currency}}'\n\
  \            invoice_date: '{{tools.invoice_date}}'\n      - name: get-invoice\n        method: GET\n        description: Get a specific invoice by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Invoice ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-invoice\n        method: PATCH\n        description: Update invoice status or fields\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Invoice ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            status: '{{tools.status}}'\n            approved_amount: '{{tools.approved_amount}}'\n    - name: vendors\n      path:\
  \ /vendors\n      description: Outside counsel and vendor management\n      operations:\n      - name: list-vendors\n        method: GET\n        description: List all vendors with pagination\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by vendor status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-vendor\n        method: POST\n        description: Create a new vendor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            type: '{{tools.type}}'\n            contact_email: '{{tools.contact_email}}'\n      - name: get-vendor\n        method: GET\n        description: Get a specific vendor by ID\n        inputParameters:\n\
  \        - name: id\n          in: path\n          type: string\n          required: true\n          description: Vendor ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cost-codes\n      path: /cost-codes\n      description: Billing and cost code management\n      operations:\n      - name: list-cost-codes\n        method: GET\n        description: List all cost codes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      description: User account management\n      operations:\n      - name: list-users\n        method: GET\n        description: List all users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create a new user\n   \
  \     outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            email: '{{tools.email}}'\n            first_name: '{{tools.first_name}}'\n            last_name: '{{tools.last_name}}'\n            role: '{{tools.role}}'\n    - name: payments\n      path: /payments\n      description: Invoice payment recording\n      operations:\n      - name: list-payments\n        method: GET\n        description: List all payments\n        inputParameters:\n        - name: invoice_id\n          in: query\n          type: string\n          required: false\n          description: Filter by invoice ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-payment\n        method: POST\n        description: Record a payment for an approved invoice\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            invoice_id: '{{tools.invoice_id}}'\n            amount: '{{tools.amount}}'\n            payment_date: '{{tools.payment_date}}'\n            reference: '{{tools.reference}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: simplelegal-legal-ops-api\n    description: Unified REST API for SimpleLegal legal operations management workflows.\n    resources:\n    - path: /v1/matters\n      name: matters\n      description: Legal matter lifecycle management\n      operations:\n      - method: GET\n        name: list-matters\n        description: List all legal matters with filtering and pagination\n        call: simplelegal.list-matters\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-matter\n        description: Create a new legal matter\n        call: simplelegal.create-matter\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/matters/{id}\n      name: matter\n      description: Individual matter management\n      operations:\n      - method: GET\n        name: get-matter\n        description: Get a specific legal matter by ID\n        call: simplelegal.get-matter\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-matter\n        description: Update matter fields (status, budget, counsel)\n        call: simplelegal.update-matter\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices\n      name: invoices\n      description: Legal invoice eBilling and approval workflow\n      operations:\n      - method: GET\n        name: list-invoices\n        description: List all invoices with filtering by status and matter\n        call: simplelegal.list-invoices\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-invoice\n        description: Submit a new invoice for eBilling review\n        call: simplelegal.create-invoice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices/{id}\n      name: invoice\n      description: Individual invoice management\n      operations:\n      - method: GET\n        name: get-invoice\n        description: Get a specific invoice by ID\n        call: simplelegal.get-invoice\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-invoice\n        description: Update invoice status (approve, reject, hold)\n        call: simplelegal.update-invoice\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vendors\n      name: vendors\n \
  \     description: Outside counsel and legal vendor management\n      operations:\n      - method: GET\n        name: list-vendors\n        description: List all outside counsel and legal service vendors\n        call: simplelegal.list-vendors\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-vendor\n        description: Add a new outside counsel or vendor\n        call: simplelegal.create-vendor\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vendors/{id}\n      name: vendor\n      description: Individual vendor management\n      operations:\n      - method: GET\n        name: get-vendor\n        description: Get a specific vendor by ID\n        call: simplelegal.get-vendor\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-vendor\n        description: Update vendor information\
  \ or status\n        call: simplelegal.update-vendor\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cost-codes\n      name: cost-codes\n      description: Billing and cost code catalog\n      operations:\n      - method: GET\n        name: list-cost-codes\n        description: List all configured billing and cost codes\n        call: simplelegal.list-cost-codes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: User account management\n      operations:\n      - method: GET\n        name: list-users\n        description: List all platform users\n        call: simplelegal.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-user\n        description: Create a new platform user\n        call: simplelegal.create-user\n        outputParameters:\n    \
  \    - type: object\n          mapping: $.\n    - path: /v1/payments\n      name: payments\n      description: Invoice payment recording\n      operations:\n      - method: GET\n        name: list-payments\n        description: List all recorded payments\n        call: simplelegal.list-payments\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-payment\n        description: Record a payment for an approved invoice\n        call: simplelegal.create-payment\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: simplelegal-legal-ops-mcp\n    transport: http\n    description: MCP server for AI-assisted legal operations, matter tracking, invoice review, and spend analysis.\n    tools:\n    - name: list-matters\n      description: List all legal matters with optional filtering by status or practice area\n      hints:\n        readOnly: true\n        idempotent:\
  \ true\n      call: simplelegal.list-matters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-matter\n      description: Create a new legal matter with name, practice area, budget, and counsel assignment\n      hints:\n        readOnly: false\n        idempotent: false\n      call: simplelegal.create-matter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-matter\n      description: Get detailed information about a specific legal matter by ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: simplelegal.get-matter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-matter\n      description: Update matter status, budget, or attorney assignments\n      hints:\n        readOnly: false\n        idempotent: true\n      call: simplelegal.update-matter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-invoices\n      description:\
  \ List legal invoices with filtering by status, matter, or vendor\n      hints:\n        readOnly: true\n        idempotent: true\n      call: simplelegal.list-invoices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-invoice\n      description: Submit a new legal invoice for eBilling review and approval\n      hints:\n        readOnly: false\n        idempotent: false\n      call: simplelegal.create-invoice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-invoice\n      description: Get details of a specific invoice including line items and approval status\n      hints:\n        readOnly: true\n        idempotent: true\n      call: simplelegal.get-invoice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: approve-invoice\n      description: Approve an invoice and set the approved payment amount\n      hints:\n        readOnly: false\n        idempotent: true\n      call: simplelegal.update-invoice\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-vendors\n      description: List all outside counsel and legal service vendors\n      hints:\n        readOnly: true\n        idempotent: true\n      call: simplelegal.list-vendors\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-vendor\n      description: Add a new outside counsel law firm or legal service provider\n      hints:\n        readOnly: false\n        idempotent: false\n      call: simplelegal.create-vendor\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-vendor\n      description: Get information about a specific vendor or outside counsel firm\n      hints:\n        readOnly: true\n        idempotent: true\n      call: simplelegal.get-vendor\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-cost-codes\n      description: List all billing and cost codes available for invoice categorization\n\
  \      hints:\n        readOnly: true\n        idempotent: true\n      call: simplelegal.list-cost-codes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-users\n      description: List all SimpleLegal platform users\n      hints:\n        readOnly: true\n        idempotent: true\n      call: simplelegal.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-user\n      description: Create a new SimpleLegal platform user\n      hints:\n        readOnly: false\n        idempotent: false\n      call: simplelegal.create-user\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-payments\n      description: List all recorded invoice payments\n      hints:\n        readOnly: true\n        idempotent: true\n      call: simplelegal.list-payments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: record-payment\n      description: Record a payment for an\
  \ approved invoice to track disbursements\n      hints:\n        readOnly: false\n        idempotent: false\n      call: simplelegal.create-payment\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/simplelegal/refs/heads/main/capabilities/legal-operations-management.yaml
tags:
- eBilling
- Enterprise Legal Management
- Finance Integration
- Invoices
- Legal Operations
- Legal Spend Management
- Matter Management
- Vendors
tools:
- description: List all legal matters with optional filtering by status or practice area
  hints:
    idempotent: true
    readOnly: true
  name: list-matters
- description: Create a new legal matter with name, practice area, budget, and counsel assignment
  hints:
    idempotent: false
    readOnly: false
  name: create-matter
- description: Get detailed information about a specific legal matter by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-matter
- description: Update matter status, budget, or attorney assignments
  hints:
    idempotent: true
    readOnly: false
  name: update-matter
- description: List legal invoices with filtering by status, matter, or vendor
  hints:
    idempotent: true
    readOnly: true
  name: list-invoices
- description: Submit a new legal invoice for eBilling review and approval
  hints:
    idempotent: false
    readOnly: false
  name: create-invoice
- description: Get details of a specific invoice including line items and approval status
  hints:
    idempotent: true
    readOnly: true
  name: get-invoice
- description: Approve an invoice and set the approved payment amount
  hints:
    idempotent: true
    readOnly: false
  name: approve-invoice
- description: List all outside counsel and legal service vendors
  hints:
    idempotent: true
    readOnly: true
  name: list-vendors
- description: Add a new outside counsel law firm or legal service provider
  hints:
    idempotent: false
    readOnly: false
  name: create-vendor
- description: Get information about a specific vendor or outside counsel firm
  hints:
    idempotent: true
    readOnly: true
  name: get-vendor
- description: List all billing and cost codes available for invoice categorization
  hints:
    idempotent: true
    readOnly: true
  name: list-cost-codes
- description: List all SimpleLegal platform users
  hints:
    idempotent: true
    readOnly: true
  name: list-users
- description: Create a new SimpleLegal platform user
  hints:
    idempotent: false
    readOnly: false
  name: create-user
- description: List all recorded invoice payments
  hints:
    idempotent: true
    readOnly: true
  name: list-payments
- description: Record a payment for an approved invoice to track disbursements
  hints:
    idempotent: false
    readOnly: false
  name: record-payment
---
