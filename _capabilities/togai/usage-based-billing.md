---
categories: []
consumed_apis:
- togai
description: Unified capability for managing the full usage-based billing lifecycle with Togai. Covers customer onboarding, account management, usage event ingestion, price plan configuration, invoice generation, and credit management for SaaS and cloud products.
layout: capability
name: Togai Usage-Based Billing
operations:
- description: List all billing customers
  method: GET
  name: list-customers
  path: /v1/customers
- description: Create a new billing customer
  method: POST
  name: create-customer
  path: /v1/customers
- description: Get customer details
  method: GET
  name: get-customer
  path: /v1/customers/{customerId}
- description: List accounts for a customer
  method: GET
  name: list-accounts
  path: /v1/customers/{customerId}/accounts
- description: Create a new account
  method: POST
  name: create-account
  path: /v1/customers/{customerId}/accounts
- description: Ingest usage events for metering
  method: POST
  name: ingest-events
  path: /v1/events
- description: List all price plans
  method: GET
  name: list-price-plans
  path: /v1/price-plans
- description: Create a new price plan
  method: POST
  name: create-price-plan
  path: /v1/price-plans
- description: List invoices for an account
  method: GET
  name: list-invoices
  path: /v1/accounts/{accountId}/invoices
- description: List credits for an account
  method: GET
  name: list-credits
  path: /v1/accounts/{accountId}/credits
- description: Grant credit to an account
  method: POST
  name: grant-credit
  path: /v1/accounts/{accountId}/credits
personas: []
provider_name: Togai
provider_slug: togai
search_terms:
- list accounts for a customer
- list price plans
- customer lifecycle management
- list invoices for an account
- ingest usage events into togai for metering and billing
- create a new customer in togai billing system
- list credits for an account
- list invoices for a togai account
- create a new usage-based price plan in togai
- saas
- create a new billing customer
- create a new account
- list all price plans
- individual customer operations
- usage event ingestion
- create price plan
- list accounts for a togai customer
- grant credit
- ingest events
- list usage meters for a togai event schema
- ingest usage events for metering
- invoice management
- revenue management
- create account
- list invoices
- account management
- get customer details
- create a new price plan
- list accounts
- metering
- price plan management
- list customers
- list all billing customers
- list credits
- list usage meters
- get customer
- togai
- usage-based pricing
- create customer
- get details of a specific togai customer
- billing
- grant billing credits to a togai account
- list all togai price plans
- fintech
- credit management
- grant credit to an account
- list all billing customers in togai
slug: usage-based-billing
source_filename: usage-based-billing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Togai Usage-Based Billing\"\n  description: >-\n    Unified capability for managing the full usage-based billing lifecycle with Togai.\n    Covers customer onboarding, account management, usage event ingestion, price plan\n    configuration, invoice generation, and credit management for SaaS and cloud products.\n  tags:\n    - Togai\n    - Billing\n    - Metering\n    - Usage-Based Pricing\n    - Revenue Management\n    - SaaS\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TOGAI_API_TOKEN: TOGAI_API_TOKEN\n\ncapability:\n  consumes:\n    - import: togai\n      location: ./shared/togai-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: togai-billing-api\n      description: \"Unified REST API for Togai usage-based billing operations.\"\n      resources:\n        - path: /v1/customers\n          name: customers\n          description: \"Customer lifecycle\
  \ management\"\n          operations:\n            - method: GET\n              name: list-customers\n              description: \"List all billing customers\"\n              call: \"togai.list-customers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-customer\n              description: \"Create a new billing customer\"\n              call: \"togai.create-customer\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/customers/{customerId}\n          name: customer\n          description: \"Individual customer operations\"\n          operations:\n            - method: GET\n              name: get-customer\n              description: \"Get customer details\"\n              call: \"togai.get-customer\"\n              with:\n                customerId: \"rest.customerId\"\n              outputParameters:\n     \
  \           - type: object\n                  mapping: \"$.\"\n        - path: /v1/customers/{customerId}/accounts\n          name: accounts\n          description: \"Account management\"\n          operations:\n            - method: GET\n              name: list-accounts\n              description: \"List accounts for a customer\"\n              call: \"togai.list-accounts\"\n              with:\n                customerId: \"rest.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-account\n              description: \"Create a new account\"\n              call: \"togai.create-account\"\n              with:\n                customerId: \"rest.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/events\n          name: events\n          description: \"Usage event ingestion\"\n          operations:\n\
  \            - method: POST\n              name: ingest-events\n              description: \"Ingest usage events for metering\"\n              call: \"togai.ingest-events\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/price-plans\n          name: price-plans\n          description: \"Price plan management\"\n          operations:\n            - method: GET\n              name: list-price-plans\n              description: \"List all price plans\"\n              call: \"togai.list-price-plans\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-price-plan\n              description: \"Create a new price plan\"\n              call: \"togai.create-price-plan\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/accounts/{accountId}/invoices\n \
  \         name: invoices\n          description: \"Invoice management\"\n          operations:\n            - method: GET\n              name: list-invoices\n              description: \"List invoices for an account\"\n              call: \"togai.list-invoices\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/accounts/{accountId}/credits\n          name: credits\n          description: \"Credit management\"\n          operations:\n            - method: GET\n              name: list-credits\n              description: \"List credits for an account\"\n              call: \"togai.list-credits\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: grant-credit\n              description: \"\
  Grant credit to an account\"\n              call: \"togai.grant-credit\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: togai-billing-mcp\n      transport: http\n      description: \"MCP server for AI-assisted usage-based billing operations with Togai.\"\n      tools:\n        - name: list-customers\n          description: \"List all billing customers in Togai\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"togai.list-customers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-customer\n          description: \"Create a new customer in Togai billing system\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"togai.create-customer\"\
  \n          with:\n            name: \"tools.name\"\n            id: \"tools.id\"\n            primaryEmail: \"tools.primaryEmail\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-customer\n          description: \"Get details of a specific Togai customer\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"togai.get-customer\"\n          with:\n            customerId: \"tools.customerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-accounts\n          description: \"List accounts for a Togai customer\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"togai.list-accounts\"\n          with:\n            customerId: \"tools.customerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ingest-events\n          description:\
  \ \"Ingest usage events into Togai for metering and billing\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"togai.ingest-events\"\n          with:\n            events: \"tools.events\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-price-plans\n          description: \"List all Togai price plans\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"togai.list-price-plans\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-price-plan\n          description: \"Create a new usage-based price plan in Togai\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"togai.create-price-plan\"\n          with:\n            name: \"tools.name\"\n            type: \"tools.type\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-invoices\n          description: \"List invoices for a Togai account\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"togai.list-invoices\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: grant-credit\n          description: \"Grant billing credits to a Togai account\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"togai.grant-credit\"\n          with:\n            accountId: \"tools.accountId\"\n            creditAmount: \"tools.creditAmount\"\n            effectiveFrom: \"tools.effectiveFrom\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-usage-meters\n          description:\
  \ \"List usage meters for a Togai event schema\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"togai.list-usage-meters\"\n          with:\n            eventSchemaName: \"tools.eventSchemaName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/togai/refs/heads/main/capabilities/usage-based-billing.yaml
tags:
- Togai
- Billing
- Metering
- Usage-Based Pricing
- Revenue Management
- SaaS
tools:
- description: List all billing customers in Togai
  hints:
    openWorld: false
    readOnly: true
  name: list-customers
- description: Create a new customer in Togai billing system
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-customer
- description: Get details of a specific Togai customer
  hints:
    openWorld: false
    readOnly: true
  name: get-customer
- description: List accounts for a Togai customer
  hints:
    openWorld: false
    readOnly: true
  name: list-accounts
- description: Ingest usage events into Togai for metering and billing
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: ingest-events
- description: List all Togai price plans
  hints:
    openWorld: false
    readOnly: true
  name: list-price-plans
- description: Create a new usage-based price plan in Togai
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-price-plan
- description: List invoices for a Togai account
  hints:
    openWorld: false
    readOnly: true
  name: list-invoices
- description: Grant billing credits to a Togai account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: grant-credit
- description: List usage meters for a Togai event schema
  hints:
    openWorld: false
    readOnly: true
  name: list-usage-meters
---
