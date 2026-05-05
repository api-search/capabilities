---
api_specs:
- filename: simplelegal-openapi.yml
  format: yaml
  label: simplelegal
  slug: simplelegal
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/simplelegal/refs/heads/main/openapi/simplelegal-openapi.yml
categories: []
consumed_apis:
- simplelegal
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
- get a specific invoice by id
- outside counsel and legal vendor management
- create a new simplelegal platform user
- update matter status, budget, or attorney assignments
- submit a new legal invoice for ebilling review and approval
- list all legal matters with filtering and pagination
- matter management
- invoices
- list users
- update matter fields (status, budget, counsel)
- list payments
- list vendors
- create vendor
- get a specific vendor by id
- legal spend management
- user account management
- create user
- create a new platform user
- add a new outside counsel law firm or legal service provider
- list all billing and cost codes available for invoice categorization
- update vendor information or status
- legal matter lifecycle management
- create invoice
- list all recorded invoice payments
- create payment
- get information about a specific vendor or outside counsel firm
- legal operations
- list invoices
- list all invoices with filtering by status and matter
- individual invoice management
- list cost codes
- legal invoice ebilling and approval workflow
- create a new legal matter with name, practice area, budget, and counsel assignment
- update invoice status (approve, reject, hold)
- get invoice
- get a specific legal matter by id
- update invoice
- list all configured billing and cost codes
- list legal invoices with filtering by status, matter, or vendor
- get details of a specific invoice including line items and approval status
- list all outside counsel and legal service vendors
- create matter
- list matters
- list all platform users
- individual matter management
- invoice payment recording
- list all legal matters with optional filtering by status or practice area
- individual vendor management
- vendors
- list all recorded payments
- record payment
- vendor management
- approve invoice
- approve an invoice and set the approved payment amount
- get detailed information about a specific legal matter by id
- update matter
- finance integration
- enterprise legal management
- get matter
- update vendor
- create a new legal matter
- ebilling
- billing and cost code catalog
- submit a new invoice for ebilling review
- record a payment for an approved invoice to track disbursements
- get vendor
- record a payment for an approved invoice
- list all simplelegal platform users
- add a new outside counsel or vendor
slug: legal-operations-management
source_filename: legal-operations-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SimpleLegal Legal Operations Management\"\n  description: >-\n    Unified legal operations management capability combining SimpleLegal's matter\n    management, eBilling, vendor management, spend analytics, and user administration\n    APIs into a single workflow. Designed for in-house legal operations teams,\n    general counsel offices, and finance integrators building legal-to-finance data\n    pipelines.\n  tags:\n    - eBilling\n    - Enterprise Legal Management\n    - Finance Integration\n    - Invoices\n    - Legal Operations\n    - Legal Spend Management\n    - Matter Management\n    - Vendors\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SIMPLELEGAL_USERNAME: SIMPLELEGAL_USERNAME\n      SIMPLELEGAL_PASSWORD: SIMPLELEGAL_PASSWORD\n\ncapability:\n  consumes:\n    - import: simplelegal\n      location: ./shared/simplelegal.yaml\n\n  exposes:\n    - type: rest\n    \
  \  port: 8080\n      namespace: simplelegal-legal-ops-api\n      description: \"Unified REST API for SimpleLegal legal operations management workflows.\"\n      resources:\n        - path: /v1/matters\n          name: matters\n          description: Legal matter lifecycle management\n          operations:\n            - method: GET\n              name: list-matters\n              description: List all legal matters with filtering and pagination\n              call: \"simplelegal.list-matters\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-matter\n              description: Create a new legal matter\n              call: \"simplelegal.create-matter\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/matters/{id}\n          name: matter\n          description: Individual matter management\n          operations:\n\
  \            - method: GET\n              name: get-matter\n              description: Get a specific legal matter by ID\n              call: \"simplelegal.get-matter\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-matter\n              description: Update matter fields (status, budget, counsel)\n              call: \"simplelegal.update-matter\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/invoices\n          name: invoices\n          description: Legal invoice eBilling and approval workflow\n          operations:\n            - method: GET\n              name: list-invoices\n              description: List all invoices with filtering by status and matter\n              call: \"simplelegal.list-invoices\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-invoice\n              description: Submit a new invoice for eBilling review\n              call: \"simplelegal.create-invoice\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/invoices/{id}\n          name: invoice\n          description: Individual invoice management\n          operations:\n            - method: GET\n              name: get-invoice\n              description: Get a specific invoice by ID\n              call: \"simplelegal.get-invoice\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-invoice\n              description: Update invoice status (approve, reject, hold)\n              call:\
  \ \"simplelegal.update-invoice\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/vendors\n          name: vendors\n          description: Outside counsel and legal vendor management\n          operations:\n            - method: GET\n              name: list-vendors\n              description: List all outside counsel and legal service vendors\n              call: \"simplelegal.list-vendors\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-vendor\n              description: Add a new outside counsel or vendor\n              call: \"simplelegal.create-vendor\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/vendors/{id}\n          name: vendor\n          description: Individual vendor\
  \ management\n          operations:\n            - method: GET\n              name: get-vendor\n              description: Get a specific vendor by ID\n              call: \"simplelegal.get-vendor\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-vendor\n              description: Update vendor information or status\n              call: \"simplelegal.update-vendor\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/cost-codes\n          name: cost-codes\n          description: Billing and cost code catalog\n          operations:\n            - method: GET\n              name: list-cost-codes\n              description: List all configured billing and cost codes\n              call: \"simplelegal.list-cost-codes\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/users\n          name: users\n          description: User account management\n          operations:\n            - method: GET\n              name: list-users\n              description: List all platform users\n              call: \"simplelegal.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-user\n              description: Create a new platform user\n              call: \"simplelegal.create-user\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/payments\n          name: payments\n          description: Invoice payment recording\n          operations:\n            - method: GET\n              name: list-payments\n              description: List all recorded payments\n  \
  \            call: \"simplelegal.list-payments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-payment\n              description: Record a payment for an approved invoice\n              call: \"simplelegal.create-payment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: simplelegal-legal-ops-mcp\n      transport: http\n      description: \"MCP server for AI-assisted legal operations, matter tracking, invoice review, and spend analysis.\"\n      tools:\n        - name: list-matters\n          description: List all legal matters with optional filtering by status or practice area\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"simplelegal.list-matters\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n\n        - name: create-matter\n          description: Create a new legal matter with name, practice area, budget, and counsel assignment\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"simplelegal.create-matter\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-matter\n          description: Get detailed information about a specific legal matter by ID\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"simplelegal.get-matter\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-matter\n          description: Update matter status, budget, or attorney assignments\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"simplelegal.update-matter\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n\n        - name: list-invoices\n          description: List legal invoices with filtering by status, matter, or vendor\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"simplelegal.list-invoices\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-invoice\n          description: Submit a new legal invoice for eBilling review and approval\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"simplelegal.create-invoice\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-invoice\n          description: Get details of a specific invoice including line items and approval status\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"simplelegal.get-invoice\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n\n        - name: approve-invoice\n          description: Approve an invoice and set the approved payment amount\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"simplelegal.update-invoice\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-vendors\n          description: List all outside counsel and legal service vendors\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"simplelegal.list-vendors\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-vendor\n          description: Add a new outside counsel law firm or legal service provider\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"simplelegal.create-vendor\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name:\
  \ get-vendor\n          description: Get information about a specific vendor or outside counsel firm\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"simplelegal.get-vendor\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-cost-codes\n          description: List all billing and cost codes available for invoice categorization\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"simplelegal.list-cost-codes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-users\n          description: List all SimpleLegal platform users\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"simplelegal.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-user\n          description:\
  \ Create a new SimpleLegal platform user\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"simplelegal.create-user\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-payments\n          description: List all recorded invoice payments\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"simplelegal.list-payments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: record-payment\n          description: Record a payment for an approved invoice to track disbursements\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"simplelegal.create-payment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
