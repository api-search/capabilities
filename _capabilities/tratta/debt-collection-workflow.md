---
categories: []
consumed_apis: []
description: 'Workflow capability for debt collection and payment recovery operations. Enables collections teams and system integrators to manage the full debt collection lifecycle: importing debt accounts, creating payment plans, processing charges, generating customer portal sessions, and tracking transactions.'
layout: capability
name: Tratta Debt Collection Workflow
operations:
- description: List customers in the organization
  method: GET
  name: list-customers
  path: /v1/customers
- description: Create a new customer record
  method: POST
  name: create-customer
  path: /v1/customers
- description: List all debt accounts
  method: GET
  name: list-debt-accounts
  path: /v1/debt-accounts
- description: Create a debt account for a customer
  method: POST
  name: create-debt-account
  path: /v1/debt-accounts
- description: List all payment plans
  method: GET
  name: list-payment-plans
  path: /v1/payment-plans
- description: Create a payment plan for a debt account
  method: POST
  name: create-payment-plan
  path: /v1/payment-plans
- description: List charges
  method: GET
  name: list-charges
  path: /v1/charges
- description: Process a charge against a payment method
  method: POST
  name: create-charge
  path: /v1/charges
- description: List payment transactions with date filtering
  method: GET
  name: list-transactions
  path: /v1/transactions
- description: Generate a magic link for customer portal access
  method: POST
  name: create-customer-session
  path: /v1/customer-sessions
- description: List stored payment methods
  method: GET
  name: list-payment-methods
  path: /v1/payment-methods
- description: Store a new payment method
  method: POST
  name: create-payment-method
  path: /v1/payment-methods
- description: List configured webhooks
  method: GET
  name: list-webhooks
  path: /v1/webhooks
- description: Create a webhook for payment events
  method: POST
  name: create-webhook
  path: /v1/webhooks
personas: []
provider_name: Tratta
provider_slug: tratta
search_terms:
- set up a payment plan for a debt account
- process a one-time charge against a stored payment method
- subscribe to payment plan and transaction events via webhook
- create payment plan
- create a debt account for a customer
- create payment method
- list customers in the collections portfolio
- list payment transactions with date filtering
- debt collection
- store a new payment method
- create webhook
- list debt accounts in the portfolio
- list active and historical payment plans
- billing
- transaction history and reporting
- collections
- transactions
- process a charge against a payment method
- add a new customer to the collections system
- list all debt accounts
- create a new customer record
- list configured webhooks
- generate a magic link for customer portal access
- create a new debt account for a customer
- debt account portfolio management
- list payment plans
- list payment transactions with optional date range filter
- customer account management
- webhook event subscriptions
- create a payment plan for a debt account
- create a webhook for payment events
- secure customer portal sessions
- list stored payment methods
- payment plans
- create customer
- list customers in the organization
- payments
- create charge
- create customer session
- list customers
- create debt account
- stored payment methods
- charge processing
- generate a magic link for a customer to access their payment portal
- list debt accounts
- payment plan management and tracking
- list charges
- list transactions
- list payment methods
- list webhooks
- list all payment plans
- fintech
slug: debt-collection-workflow
source_filename: debt-collection-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Tratta Debt Collection Workflow\n  description: 'Workflow capability for debt collection and payment recovery operations. Enables collections teams and system\n    integrators to manage the full debt collection lifecycle: importing debt accounts, creating payment plans, processing\n    charges, generating customer portal sessions, and tracking transactions.'\n  tags:\n  - Billing\n  - Collections\n  - Payments\n  - Debt Collection\n  - Fintech\n  - Payment Plans\n  - Transactions\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TRATTA_BEARER_TOKEN: TRATTA_BEARER_TOKEN\n    TRATTA_ORG_UUID: TRATTA_ORG_UUID\ncapability:\n  consumes:\n  - type: http\n    namespace: tratta\n    baseUri: https://{{TRATTA_ORG_UUID}}.production.tratta.io/api/v1\n    description: Tratta debt collection and payment management REST API.\n    authentication:\n      type: bearer\n      token: '{{TRATTA_BEARER_TOKEN}}'\n  \
  \  resources:\n    - name: customers\n      path: /customers\n      description: Customer account management\n      operations:\n      - name: list-customers\n        method: GET\n        description: List customers with pagination\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Records per page (1-500)\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: include\n          in: query\n          type: string\n          required: false\n          description: Related resources to include\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-customer\n        method: POST\n        description: Create a new customer record\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n \
  \         type: object\n          value: $.\n        body:\n          type: json\n          data:\n            first_name: '{{tools.first_name}}'\n            last_name: '{{tools.last_name}}'\n            email: '{{tools.email}}'\n            phone: '{{tools.phone}}'\n    - name: customers-by-id\n      path: /customers/{id}\n      description: Individual customer operations\n      operations:\n      - name: get-customer\n        method: GET\n        description: Get a customer by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Customer ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: debt-accounts\n      path: /debt_accounts\n      description: Debt account operations\n      operations:\n      - name: list-debt-accounts\n        method: GET\n        description: List debt accounts with pagination\n \
  \       inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Records per page\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-debt-account\n        method: POST\n        description: Create a new debt account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            customer_id: '{{tools.customer_id}}'\n            original_balance: '{{tools.original_balance}}'\n            account_number: '{{tools.account_number}}'\n    - name: payment-plans\n      path: /payment_plans\n      description: Payment plan management\n      operations:\n      - name:\
  \ list-payment-plans\n        method: GET\n        description: List payment plans\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Records per page\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-payment-plan\n        method: POST\n        description: Create a payment plan for a debt account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            debt_account_id: '{{tools.debt_account_id}}'\n            total_amount: '{{tools.total_amount}}'\n            installment_amount: '{{tools.installment_amount}}'\n            frequency:\
  \ '{{tools.frequency}}'\n    - name: payment-methods\n      path: /payment_methods\n      description: Payment method storage\n      operations:\n      - name: list-payment-methods\n        method: GET\n        description: List stored payment methods\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-payment-method\n        method: POST\n        description: Store a new payment method\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            type: '{{tools.type}}'\n            token: '{{tools.token}}'\n    - name: charges\n      path: /charges\n      description: Charge processing\n      operations:\n      - name: list-charges\n        method: GET\n        description: List charges\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: create-charge\n        method: POST\n        description: Create a charge against a payment method\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            amount: '{{tools.amount}}'\n            payment_method_id: '{{tools.payment_method_id}}'\n            debt_account_id: '{{tools.debt_account_id}}'\n    - name: transactions\n      path: /transactions\n      description: Transaction history\n      operations:\n      - name: list-transactions\n        method: GET\n        description: List payment transactions\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Records per page\n        - name: start_date\n          in: query\n          type: string\n          required: false\n          description:\
  \ Filter from date\n        - name: end_date\n          in: query\n          type: string\n          required: false\n          description: Filter to date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customer-sessions\n      path: /customer_sessions\n      description: Customer portal session management\n      operations:\n      - name: create-customer-session\n        method: POST\n        description: Create a magic link session for customer portal access\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            customer_id: '{{tools.customer_id}}'\n            redirect_url: '{{tools.redirect_url}}'\n            expires_in: '{{tools.expires_in}}'\n    - name: webhooks\n      path: /webhooks\n      description: Webhook configuration\n      operations:\n   \
  \   - name: list-webhooks\n        method: GET\n        description: List configured webhooks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-webhook\n        method: POST\n        description: Create a webhook for event notifications\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            url: '{{tools.url}}'\n            events: '{{tools.events}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: debt-collection-api\n    description: Unified REST API for debt collection and payment recovery workflows.\n    resources:\n    - path: /v1/customers\n      name: customers\n      description: Customer account management\n      operations:\n      - method: GET\n        name: list-customers\n        description: List customers in the organization\n\
  \        call: tratta.list-customers\n        with:\n          limit: rest.limit\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-customer\n        description: Create a new customer record\n        call: tratta.create-customer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/debt-accounts\n      name: debt-accounts\n      description: Debt account portfolio management\n      operations:\n      - method: GET\n        name: list-debt-accounts\n        description: List all debt accounts\n        call: tratta.list-debt-accounts\n        with:\n          limit: rest.limit\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-debt-account\n        description: Create a debt account for a customer\n        call: tratta.create-debt-account\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/payment-plans\n      name: payment-plans\n      description: Payment plan management and tracking\n      operations:\n      - method: GET\n        name: list-payment-plans\n        description: List all payment plans\n        call: tratta.list-payment-plans\n        with:\n          limit: rest.limit\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-payment-plan\n        description: Create a payment plan for a debt account\n        call: tratta.create-payment-plan\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/charges\n      name: charges\n      description: Charge processing\n      operations:\n      - method: GET\n        name: list-charges\n        description: List charges\n        call: tratta.list-charges\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \      - method: POST\n        name: create-charge\n        description: Process a charge against a payment method\n        call: tratta.create-charge\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/transactions\n      name: transactions\n      description: Transaction history and reporting\n      operations:\n      - method: GET\n        name: list-transactions\n        description: List payment transactions with date filtering\n        call: tratta.list-transactions\n        with:\n          start_date: rest.start_date\n          end_date: rest.end_date\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/customer-sessions\n      name: customer-sessions\n      description: Secure customer portal sessions\n      operations:\n      - method: POST\n        name: create-customer-session\n        description: Generate a magic link for customer portal access\n        call: tratta.create-customer-session\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payment-methods\n      name: payment-methods\n      description: Stored payment methods\n      operations:\n      - method: GET\n        name: list-payment-methods\n        description: List stored payment methods\n        call: tratta.list-payment-methods\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-payment-method\n        description: Store a new payment method\n        call: tratta.create-payment-method\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/webhooks\n      name: webhooks\n      description: Webhook event subscriptions\n      operations:\n      - method: GET\n        name: list-webhooks\n        description: List configured webhooks\n        call: tratta.list-webhooks\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n      \
  \  name: create-webhook\n        description: Create a webhook for payment events\n        call: tratta.create-webhook\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: debt-collection-mcp\n    transport: http\n    description: MCP server for AI-assisted debt collection and payment recovery.\n    tools:\n    - name: list-customers\n      description: List customers in the collections portfolio\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tratta.list-customers\n      with:\n        limit: tools.limit\n        page: tools.page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-customer\n      description: Add a new customer to the collections system\n      hints:\n        readOnly: false\n        openWorld: false\n      call: tratta.create-customer\n      with:\n        first_name: tools.first_name\n        last_name: tools.last_name\n        email:\
  \ tools.email\n        phone: tools.phone\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-debt-accounts\n      description: List debt accounts in the portfolio\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tratta.list-debt-accounts\n      with:\n        limit: tools.limit\n        page: tools.page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-debt-account\n      description: Create a new debt account for a customer\n      hints:\n        readOnly: false\n        openWorld: false\n      call: tratta.create-debt-account\n      with:\n        customer_id: tools.customer_id\n        original_balance: tools.original_balance\n        account_number: tools.account_number\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-payment-plans\n      description: List active and historical payment plans\n      hints:\n        readOnly: true\n        openWorld:\
  \ false\n      call: tratta.list-payment-plans\n      with:\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-payment-plan\n      description: Set up a payment plan for a debt account\n      hints:\n        readOnly: false\n        openWorld: false\n      call: tratta.create-payment-plan\n      with:\n        debt_account_id: tools.debt_account_id\n        total_amount: tools.total_amount\n        installment_amount: tools.installment_amount\n        frequency: tools.frequency\n        start_date: tools.start_date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-transactions\n      description: List payment transactions with optional date range filter\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tratta.list-transactions\n      with:\n        start_date: tools.start_date\n        end_date: tools.end_date\n        limit: tools.limit\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: create-customer-session\n      description: Generate a magic link for a customer to access their payment portal\n      hints:\n        readOnly: false\n        openWorld: false\n      call: tratta.create-customer-session\n      with:\n        customer_id: tools.customer_id\n        redirect_url: tools.redirect_url\n        expires_in: tools.expires_in\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-charge\n      description: Process a one-time charge against a stored payment method\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: tratta.create-charge\n      with:\n        amount: tools.amount\n        payment_method_id: tools.payment_method_id\n        debt_account_id: tools.debt_account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-webhook\n      description: Subscribe to payment plan and\
  \ transaction events via webhook\n      hints:\n        readOnly: false\n        openWorld: false\n      call: tratta.create-webhook\n      with:\n        url: tools.url\n        events: tools.events\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tratta/refs/heads/main/capabilities/debt-collection-workflow.yaml
tags:
- Billing
- Collections
- Payments
- Debt Collection
- Fintech
- Payment Plans
- Transactions
tools:
- description: List customers in the collections portfolio
  hints:
    openWorld: false
    readOnly: true
  name: list-customers
- description: Add a new customer to the collections system
  hints:
    openWorld: false
    readOnly: false
  name: create-customer
- description: List debt accounts in the portfolio
  hints:
    openWorld: false
    readOnly: true
  name: list-debt-accounts
- description: Create a new debt account for a customer
  hints:
    openWorld: false
    readOnly: false
  name: create-debt-account
- description: List active and historical payment plans
  hints:
    openWorld: false
    readOnly: true
  name: list-payment-plans
- description: Set up a payment plan for a debt account
  hints:
    openWorld: false
    readOnly: false
  name: create-payment-plan
- description: List payment transactions with optional date range filter
  hints:
    openWorld: false
    readOnly: true
  name: list-transactions
- description: Generate a magic link for a customer to access their payment portal
  hints:
    openWorld: false
    readOnly: false
  name: create-customer-session
- description: Process a one-time charge against a stored payment method
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-charge
- description: Subscribe to payment plan and transaction events via webhook
  hints:
    openWorld: false
    readOnly: false
  name: create-webhook
---
