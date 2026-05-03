---
categories: []
consumed_apis:
- stripe-customers
- stripe-billing
- stripe-invoices
description: Unified capability for subscription and recurring billing workflows. Combines Stripe Customers, Billing Portal, and Invoices APIs to support customer lifecycle management, subscription administration, and invoice processing. Used by SaaS platforms and subscription businesses.
layout: capability
name: Stripe Subscription Billing
operations:
- description: List customers
  method: GET
  name: list-customers
  path: /v1/customers
- description: Create a customer
  method: POST
  name: create-customer
  path: /v1/customers
- description: Get a customer
  method: GET
  name: get-customer
  path: /v1/customers/{customer}
- description: List invoices
  method: GET
  name: list-invoices
  path: /v1/invoices
- description: Create an invoice
  method: POST
  name: create-invoice
  path: /v1/invoices
- description: Get an invoice
  method: GET
  name: get-invoice
  path: /v1/invoices/{invoice}
- description: Create a billing portal session for a customer
  method: POST
  name: create-portal-session
  path: /v1/billing-portal-sessions
- description: List payouts
  method: GET
  name: list-payouts
  path: /v1/payouts
personas: []
provider_name: Stripe
provider_slug: stripe
search_terms:
- send invoice
- list portal configurations
- retrieve a stripe invoice by id
- finalize invoice
- t1
- individual invoice
- stripe
- create a customer
- saas
- customers
- void invoice
- list stripe billing portal configurations
- get a customer
- financial services
- list payouts
- search stripe customers by query
- invoice management
- individual customer
- email a stripe invoice to the customer
- payments
- payout management
- create portal session
- get an invoice
- list invoices
- create a billing portal session for a customer
- list stripe invoices with optional status filter
- commerce
- subscriptions
- create an invoice
- void an open stripe invoice
- create a new stripe invoice
- list customers
- search customers
- retrieve a stripe customer by id
- attempt to pay a stripe invoice
- get customer
- list stripe customers
- customer self-service billing portal
- create customer
- customer management
- billing
- fintech
- get invoice
- create a new stripe customer
- create invoice
- pay invoice
- invoices
- create a stripe billing portal session so a customer can manage their subscription
- finalize a stripe draft invoice so it can be paid
slug: subscription-billing
source_filename: subscription-billing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Stripe Subscription Billing\"\n  description: >-\n    Unified capability for subscription and recurring billing workflows. Combines Stripe Customers,\n    Billing Portal, and Invoices APIs to support customer lifecycle management, subscription administration,\n    and invoice processing. Used by SaaS platforms and subscription businesses.\n  tags:\n    - Stripe\n    - Subscriptions\n    - Billing\n    - Customers\n    - Invoices\n    - SaaS\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      STRIPE_API_KEY: STRIPE_API_KEY\n\ncapability:\n  consumes:\n    - import: stripe-customers\n      location: ./shared/customers.yaml\n    - import: stripe-billing\n      location: ./shared/billing.yaml\n    - import: stripe-invoices\n      location: ./shared/invoices.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: stripe-subscription-billing-api\n      description: \"\
  Unified REST API for Stripe subscription and billing management.\"\n      resources:\n        - path: /v1/customers\n          name: customers\n          description: \"Customer management\"\n          operations:\n            - method: GET\n              name: list-customers\n              description: \"List customers\"\n              call: \"stripe-customers.list-customers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-customer\n              description: \"Create a customer\"\n              call: \"stripe-customers.create-customer\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/customers/{customer}\n          name: customer\n          description: \"Individual customer\"\n          operations:\n            - method: GET\n              name: get-customer\n              description: \"Get a customer\"\
  \n              call: \"stripe-customers.get-customer\"\n              with:\n                customer: \"rest.customer\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/invoices\n          name: invoices\n          description: \"Invoice management\"\n          operations:\n            - method: GET\n              name: list-invoices\n              description: \"List invoices\"\n              call: \"stripe-invoices.list-invoices\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-invoice\n              description: \"Create an invoice\"\n              call: \"stripe-invoices.create-invoice\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/invoices/{invoice}\n          name: invoice\n          description: \"Individual invoice\"\n     \
  \     operations:\n            - method: GET\n              name: get-invoice\n              description: \"Get an invoice\"\n              call: \"stripe-invoices.get-invoice\"\n              with:\n                invoice: \"rest.invoice\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/billing-portal-sessions\n          name: portal-sessions\n          description: \"Customer self-service billing portal\"\n          operations:\n            - method: POST\n              name: create-portal-session\n              description: \"Create a billing portal session for a customer\"\n              call: \"stripe-billing.create-portal-session\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/payouts\n          name: payouts\n          description: \"Payout management\"\n          operations:\n            - method: GET\n              name: list-payouts\n\
  \              description: \"List payouts\"\n              call: \"stripe-payouts.list-payouts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: stripe-subscription-billing-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Stripe subscription and billing management.\"\n      tools:\n        - name: list-customers\n          description: \"List Stripe customers\"\n          hints:\n            readOnly: true\n          call: \"stripe-customers.list-customers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-customer\n          description: \"Create a new Stripe customer\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"stripe-customers.create-customer\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n \
  \       - name: get-customer\n          description: \"Retrieve a Stripe customer by ID\"\n          hints:\n            readOnly: true\n          call: \"stripe-customers.get-customer\"\n          with:\n            customer: \"tools.customer\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-customers\n          description: \"Search Stripe customers by query\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"stripe-customers.search-customers\"\n          with:\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-invoices\n          description: \"List Stripe invoices with optional status filter\"\n          hints:\n            readOnly: true\n          call: \"stripe-invoices.list-invoices\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n     \
  \   - name: create-invoice\n          description: \"Create a new Stripe invoice\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"stripe-invoices.create-invoice\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-invoice\n          description: \"Retrieve a Stripe invoice by ID\"\n          hints:\n            readOnly: true\n          call: \"stripe-invoices.get-invoice\"\n          with:\n            invoice: \"tools.invoice\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: finalize-invoice\n          description: \"Finalize a Stripe draft invoice so it can be paid\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"stripe-invoices.finalize-invoice\"\n          with:\n            invoice: \"tools.invoice\"\n          outputParameters:\n            - type: object\n        \
  \      mapping: \"$.\"\n        - name: pay-invoice\n          description: \"Attempt to pay a Stripe invoice\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"stripe-invoices.pay-invoice\"\n          with:\n            invoice: \"tools.invoice\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-invoice\n          description: \"Email a Stripe invoice to the customer\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"stripe-invoices.send-invoice\"\n          with:\n            invoice: \"tools.invoice\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: void-invoice\n          description: \"Void an open Stripe invoice\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"stripe-invoices.void-invoice\"\n          with:\n           \
  \ invoice: \"tools.invoice\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-portal-session\n          description: \"Create a Stripe billing portal session so a customer can manage their subscription\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"stripe-billing.create-portal-session\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-portal-configurations\n          description: \"List Stripe billing portal configurations\"\n          hints:\n            readOnly: true\n          call: \"stripe-billing.list-portal-configurations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/stripe/refs/heads/main/capabilities/subscription-billing.yaml
tags:
- Stripe
- Subscriptions
- Billing
- Customers
- Invoices
- SaaS
tools:
- description: List Stripe customers
  hints:
    readOnly: true
  name: list-customers
- description: Create a new Stripe customer
  hints:
    destructive: false
    readOnly: false
  name: create-customer
- description: Retrieve a Stripe customer by ID
  hints:
    readOnly: true
  name: get-customer
- description: Search Stripe customers by query
  hints:
    openWorld: true
    readOnly: true
  name: search-customers
- description: List Stripe invoices with optional status filter
  hints:
    readOnly: true
  name: list-invoices
- description: Create a new Stripe invoice
  hints:
    destructive: false
    readOnly: false
  name: create-invoice
- description: Retrieve a Stripe invoice by ID
  hints:
    readOnly: true
  name: get-invoice
- description: Finalize a Stripe draft invoice so it can be paid
  hints:
    destructive: false
    readOnly: false
  name: finalize-invoice
- description: Attempt to pay a Stripe invoice
  hints:
    destructive: false
    readOnly: false
  name: pay-invoice
- description: Email a Stripe invoice to the customer
  hints:
    destructive: false
    readOnly: false
  name: send-invoice
- description: Void an open Stripe invoice
  hints:
    destructive: true
    readOnly: false
  name: void-invoice
- description: Create a Stripe billing portal session so a customer can manage their subscription
  hints:
    destructive: false
    readOnly: false
  name: create-portal-session
- description: List Stripe billing portal configurations
  hints:
    readOnly: true
  name: list-portal-configurations
---
