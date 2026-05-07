---
categories: []
consumed_apis: []
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
- retrieve a stripe invoice by id
- get an invoice
- create a billing portal session for a customer
- invoice management
- create customer
- void an open stripe invoice
- finalize invoice
- payout management
- list stripe customers
- invoices
- billing
- search stripe customers by query
- individual invoice
- subscriptions
- commerce
- retrieve a stripe customer by id
- saas
- create a stripe billing portal session so a customer can manage their subscription
- create a customer
- get a customer
- list portal configurations
- customer self-service billing portal
- finalize a stripe draft invoice so it can be paid
- customers
- attempt to pay a stripe invoice
- pay invoice
- void invoice
- search customers
- fintech
- email a stripe invoice to the customer
- create invoice
- financial services
- t1
- list payouts
- get customer
- create a new stripe customer
- send invoice
- stripe
- create portal session
- create a new stripe invoice
- list customers
- create an invoice
- payments
- customer management
- list invoices
- get invoice
- list stripe billing portal configurations
- list stripe invoices with optional status filter
- individual customer
slug: subscription-billing
source_filename: subscription-billing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Stripe Subscription Billing\n  description: Unified capability for subscription and recurring billing workflows. Combines Stripe Customers, Billing Portal,\n    and Invoices APIs to support customer lifecycle management, subscription administration, and invoice processing. Used\n    by SaaS platforms and subscription businesses.\n  tags:\n  - Stripe\n  - Subscriptions\n  - Billing\n  - Customers\n  - Invoices\n  - SaaS\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    STRIPE_API_KEY: STRIPE_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: stripe-customers\n    baseUri: https://api.stripe.com\n    description: Stripe Customers API for managing customer records and payment methods.\n    authentication:\n      type: bearer\n      token: '{{STRIPE_API_KEY}}'\n    resources:\n    - name: customers\n      path: /v1/customers\n      description: Customer collection operations\n      operations:\n\
  \      - name: list-customers\n        method: GET\n        description: List all customers\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max items to return\n        - name: email\n          in: query\n          type: string\n          required: false\n          description: Filter by email address\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-customer\n        method: POST\n        description: Create a new customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            email: '{{tools.email}}'\n            name: '{{tools.name}}'\n    - name: customers-search\n      path: /v1/customers/search\n      description: Search customers\n      operations:\n\
  \      - name: search-customers\n        method: GET\n        description: Search customers using query syntax\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: Search query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customer\n      path: /v1/customers/{customer}\n      description: Individual customer operations\n      operations:\n      - name: get-customer\n        method: GET\n        description: Retrieve a customer by ID\n        inputParameters:\n        - name: customer\n          in: path\n          type: string\n          required: true\n          description: Customer ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-customer\n        method: POST\n        description: Update a customer\n\
  \        inputParameters:\n        - name: customer\n          in: path\n          type: string\n          required: true\n          description: Customer ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-customer\n        method: DELETE\n        description: Delete a customer permanently\n        inputParameters:\n        - name: customer\n          in: path\n          type: string\n          required: true\n          description: Customer ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customer-payment-methods\n      path: /v1/customers/{customer}/payment_methods\n      description: Customer payment methods\n      operations:\n      - name: list-customer-payment-methods\n        method: GET\n        description: List all payment methods for a customer\n        inputParameters:\n        - name:\
  \ customer\n          in: path\n          type: string\n          required: true\n          description: Customer ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: stripe-billing\n    baseUri: https://api.stripe.com\n    description: Stripe Billing Portal API for customer self-service subscription management.\n    authentication:\n      type: bearer\n      token: '{{STRIPE_API_KEY}}'\n    resources:\n    - name: billing-portal-configurations\n      path: /v1/billing_portal/configurations\n      description: Portal configuration management\n      operations:\n      - name: list-portal-configurations\n        method: GET\n        description: List billing portal configurations\n        inputParameters:\n        - name: active\n          in: query\n          type: boolean\n          required: false\n          description: Filter active or inactive configurations\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-portal-configuration\n        method: POST\n        description: Create a billing portal configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: billing-portal-sessions\n      path: /v1/billing_portal/sessions\n      description: Portal session management\n      operations:\n      - name: create-portal-session\n        method: POST\n        description: Create a billing portal session for a customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            customer: '{{tools.customer}}'\n            return_url: '{{tools.return_url}}'\n  - type: http\n    namespace: stripe-invoices\n    baseUri: https://api.stripe.com\n    description:\
  \ Stripe Invoice API for billing document management.\n    authentication:\n      type: bearer\n      token: '{{STRIPE_API_KEY}}'\n    resources:\n    - name: invoices\n      path: /v1/invoices\n      description: Invoice collection\n      operations:\n      - name: list-invoices\n        method: GET\n        description: List all invoices\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max items to return\n        - name: customer\n          in: query\n          type: string\n          required: false\n          description: Filter by customer\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status (draft, open, paid, uncollectible, void)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-invoice\n        method:\
  \ POST\n        description: Create a new invoice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invoice\n      path: /v1/invoices/{invoice}\n      description: Individual invoice\n      operations:\n      - name: get-invoice\n        method: GET\n        description: Retrieve an invoice\n        inputParameters:\n        - name: invoice\n          in: path\n          type: string\n          required: true\n          description: Invoice ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invoice-finalize\n      path: /v1/invoices/{invoice}/finalize\n      description: Finalize an invoice\n      operations:\n      - name: finalize-invoice\n        method: POST\n        description: Finalize a draft invoice\n        inputParameters:\n        - name: invoice\n          in: path\n          type: string\n   \
  \       required: true\n          description: Invoice ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invoice-pay\n      path: /v1/invoices/{invoice}/pay\n      description: Pay an invoice\n      operations:\n      - name: pay-invoice\n        method: POST\n        description: Attempt to pay an invoice\n        inputParameters:\n        - name: invoice\n          in: path\n          type: string\n          required: true\n          description: Invoice ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invoice-send\n      path: /v1/invoices/{invoice}/send\n      description: Send an invoice\n      operations:\n      - name: send-invoice\n        method: POST\n        description: Email an invoice to the customer\n        inputParameters:\n        - name: invoice\n          in: path\n          type: string\n\
  \          required: true\n          description: Invoice ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invoice-void\n      path: /v1/invoices/{invoice}/void\n      description: Void an invoice\n      operations:\n      - name: void-invoice\n        method: POST\n        description: Void an open invoice\n        inputParameters:\n        - name: invoice\n          in: path\n          type: string\n          required: true\n          description: Invoice ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: stripe-subscription-billing-api\n    description: Unified REST API for Stripe subscription and billing management.\n    resources:\n    - path: /v1/customers\n      name: customers\n      description: Customer management\n      operations:\n      - method:\
  \ GET\n        name: list-customers\n        description: List customers\n        call: stripe-customers.list-customers\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-customer\n        description: Create a customer\n        call: stripe-customers.create-customer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/customers/{customer}\n      name: customer\n      description: Individual customer\n      operations:\n      - method: GET\n        name: get-customer\n        description: Get a customer\n        call: stripe-customers.get-customer\n        with:\n          customer: rest.customer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices\n      name: invoices\n      description: Invoice management\n      operations:\n      - method: GET\n        name: list-invoices\n        description: List invoices\n        call: stripe-invoices.list-invoices\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-invoice\n        description: Create an invoice\n        call: stripe-invoices.create-invoice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices/{invoice}\n      name: invoice\n      description: Individual invoice\n      operations:\n      - method: GET\n        name: get-invoice\n        description: Get an invoice\n        call: stripe-invoices.get-invoice\n        with:\n          invoice: rest.invoice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/billing-portal-sessions\n      name: portal-sessions\n      description: Customer self-service billing portal\n      operations:\n      - method: POST\n        name: create-portal-session\n        description: Create a billing portal session for a customer\n        call: stripe-billing.create-portal-session\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/payouts\n      name: payouts\n      description: Payout management\n      operations:\n      - method: GET\n        name: list-payouts\n        description: List payouts\n        call: stripe-payouts.list-payouts\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: stripe-subscription-billing-mcp\n    transport: http\n    description: MCP server for AI-assisted Stripe subscription and billing management.\n    tools:\n    - name: list-customers\n      description: List Stripe customers\n      hints:\n        readOnly: true\n      call: stripe-customers.list-customers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-customer\n      description: Create a new Stripe customer\n      hints:\n        readOnly: false\n        destructive: false\n      call: stripe-customers.create-customer\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: get-customer\n      description: Retrieve a Stripe customer by ID\n      hints:\n        readOnly: true\n      call: stripe-customers.get-customer\n      with:\n        customer: tools.customer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-customers\n      description: Search Stripe customers by query\n      hints:\n        readOnly: true\n        openWorld: true\n      call: stripe-customers.search-customers\n      with:\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-invoices\n      description: List Stripe invoices with optional status filter\n      hints:\n        readOnly: true\n      call: stripe-invoices.list-invoices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-invoice\n      description: Create a new Stripe invoice\n      hints:\n        readOnly: false\n        destructive: false\n   \
  \   call: stripe-invoices.create-invoice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-invoice\n      description: Retrieve a Stripe invoice by ID\n      hints:\n        readOnly: true\n      call: stripe-invoices.get-invoice\n      with:\n        invoice: tools.invoice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: finalize-invoice\n      description: Finalize a Stripe draft invoice so it can be paid\n      hints:\n        readOnly: false\n        destructive: false\n      call: stripe-invoices.finalize-invoice\n      with:\n        invoice: tools.invoice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pay-invoice\n      description: Attempt to pay a Stripe invoice\n      hints:\n        readOnly: false\n        destructive: false\n      call: stripe-invoices.pay-invoice\n      with:\n        invoice: tools.invoice\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: send-invoice\n      description: Email a Stripe invoice to the customer\n      hints:\n        readOnly: false\n        destructive: false\n      call: stripe-invoices.send-invoice\n      with:\n        invoice: tools.invoice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: void-invoice\n      description: Void an open Stripe invoice\n      hints:\n        readOnly: false\n        destructive: true\n      call: stripe-invoices.void-invoice\n      with:\n        invoice: tools.invoice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-portal-session\n      description: Create a Stripe billing portal session so a customer can manage their subscription\n      hints:\n        readOnly: false\n        destructive: false\n      call: stripe-billing.create-portal-session\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-portal-configurations\n      description: List Stripe billing\
  \ portal configurations\n      hints:\n        readOnly: true\n      call: stripe-billing.list-portal-configurations\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
