---
categories: []
consumed_apis:
- squarespace-profiles
- squarespace-transactions
- squarespace-webhooks
description: Unified capability combining Squarespace Profiles, Transactions, and Webhook Subscriptions APIs. Enables CRM integrations, financial reporting tools, and event-driven automation workflows. Suited for email marketing platforms, accounting integrations, and real-time order notification systems.
layout: capability
name: Squarespace Customer and Reporting
operations:
- description: Retrieve all customer profiles with optional filters
  method: GET
  name: list-profiles
  path: /v1/profiles
- description: Get a specific customer profile
  method: GET
  name: get-profile
  path: /v1/profiles/{id}
- description: Retrieve financial transactions with optional date filters
  method: GET
  name: list-transactions
  path: /v1/transactions
- description: Get a specific financial transaction
  method: GET
  name: get-transaction
  path: /v1/transactions/{id}
- description: List all webhook subscriptions
  method: GET
  name: list-webhook-subscriptions
  path: /v1/webhook-subscriptions
- description: Create a new webhook subscription
  method: POST
  name: create-webhook-subscription
  path: /v1/webhook-subscriptions
- description: Delete a webhook subscription
  method: DELETE
  name: delete-webhook-subscription
  path: /v1/webhook-subscriptions/{id}
personas: []
provider_name: Squarespace
provider_slug: squarespace
search_terms:
- individual transaction
- retrieve a specific financial transaction by id.
- marketing
- get a specific customer profile
- customer, subscriber, and donor profiles
- analytics
- retrieve a specific customer profile by id.
- list all configured webhook subscriptions for the merchant site.
- retrieve financial transactions with optional date filters
- squarespace
- e-commerce
- get a specific financial transaction
- delete a webhook subscription
- list transactions
- individual customer profile
- financial transaction records
- create webhook subscription
- list webhook subscriptions
- get profile
- webhooks
- retrieve customer, subscriber, and donor profiles from squarespace. filter by customer status or email address.
- payments
- finance
- list all webhook subscriptions
- commerce
- get transaction
- reporting
- create a new webhook subscription
- webhook event subscriptions
- create a new webhook subscription to receive real-time notifications for squarespace commerce events (order created, order updated, etc).
- individual webhook subscription
- retrieve financial transaction records for orders and donations. supports date range filtering for reconciliation workflows.
- retail
- event notifications
- list profiles
- retrieve all customer profiles with optional filters
- website builder
- crm
- delete webhook subscription
- delete a webhook subscription by id.
slug: customer-and-reporting
source_filename: customer-and-reporting.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Squarespace Customer and Reporting\"\n  description: >-\n    Unified capability combining Squarespace Profiles, Transactions, and Webhook\n    Subscriptions APIs. Enables CRM integrations, financial reporting tools, and\n    event-driven automation workflows. Suited for email marketing platforms,\n    accounting integrations, and real-time order notification systems.\n  tags:\n    - Analytics\n    - CRM\n    - Event Notifications\n    - Finance\n    - Reporting\n    - Squarespace\n    - Webhooks\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SQUARESPACE_API_KEY: SQUARESPACE_API_KEY\n\ncapability:\n  consumes:\n    - import: squarespace-profiles\n      location: ./shared/profiles.yaml\n    - import: squarespace-transactions\n      location: ./shared/transactions.yaml\n    - import: squarespace-webhooks\n      location: ./shared/webhook-subscriptions.yaml\n\n  exposes:\n   \
  \ - type: rest\n      port: 8081\n      namespace: squarespace-customer-reporting-api\n      description: \"Unified REST API for Squarespace customer data and financial reporting.\"\n      resources:\n        - path: /v1/profiles\n          name: profiles\n          description: \"Customer, subscriber, and donor profiles\"\n          operations:\n            - method: GET\n              name: list-profiles\n              description: \"Retrieve all customer profiles with optional filters\"\n              call: \"squarespace-profiles.list-profiles\"\n              with:\n                cursor: \"rest.cursor\"\n                isCustomer: \"rest.isCustomer\"\n                email: \"rest.email\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/profiles/{id}\n          name: profile\n          description: \"Individual customer profile\"\n          operations:\n            - method: GET\n              name: get-profile\n\
  \              description: \"Get a specific customer profile\"\n              call: \"squarespace-profiles.get-profile\"\n              with:\n                profileId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/transactions\n          name: transactions\n          description: \"Financial transaction records\"\n          operations:\n            - method: GET\n              name: list-transactions\n              description: \"Retrieve financial transactions with optional date filters\"\n              call: \"squarespace-transactions.list-transactions\"\n              with:\n                cursor: \"rest.cursor\"\n                modifiedAfter: \"rest.modifiedAfter\"\n                modifiedBefore: \"rest.modifiedBefore\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/transactions/{id}\n          name: transaction\n   \
  \       description: \"Individual transaction\"\n          operations:\n            - method: GET\n              name: get-transaction\n              description: \"Get a specific financial transaction\"\n              call: \"squarespace-transactions.get-transaction\"\n              with:\n                transactionId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/webhook-subscriptions\n          name: webhook-subscriptions\n          description: \"Webhook event subscriptions\"\n          operations:\n            - method: GET\n              name: list-webhook-subscriptions\n              description: \"List all webhook subscriptions\"\n              call: \"squarespace-webhooks.list-webhook-subscriptions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-webhook-subscription\n              description:\
  \ \"Create a new webhook subscription\"\n              call: \"squarespace-webhooks.create-webhook-subscription\"\n              with:\n                endpointUrl: \"rest.endpointUrl\"\n                topics: \"rest.topics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/webhook-subscriptions/{id}\n          name: webhook-subscription\n          description: \"Individual webhook subscription\"\n          operations:\n            - method: DELETE\n              name: delete-webhook-subscription\n              description: \"Delete a webhook subscription\"\n              call: \"squarespace-webhooks.delete-webhook-subscription\"\n              with:\n                subscriptionId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: squarespace-customer-reporting-mcp\n      transport: http\n      description:\
  \ \"MCP server for AI-assisted Squarespace customer analytics and reporting.\"\n      tools:\n        - name: list-profiles\n          description: >-\n            Retrieve customer, subscriber, and donor profiles from Squarespace.\n            Filter by customer status or email address.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"squarespace-profiles.list-profiles\"\n          with:\n            cursor: \"tools.cursor\"\n            isCustomer: \"tools.isCustomer\"\n            email: \"tools.email\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-profile\n          description: \"Retrieve a specific customer profile by ID.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"squarespace-profiles.get-profile\"\n          with:\n            profileId: \"tools.profileId\"\n          outputParameters:\n            - type: object\n   \
  \           mapping: \"$.\"\n        - name: list-transactions\n          description: >-\n            Retrieve financial transaction records for orders and donations.\n            Supports date range filtering for reconciliation workflows.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"squarespace-transactions.list-transactions\"\n          with:\n            cursor: \"tools.cursor\"\n            modifiedAfter: \"tools.modifiedAfter\"\n            modifiedBefore: \"tools.modifiedBefore\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-transaction\n          description: \"Retrieve a specific financial transaction by ID.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"squarespace-transactions.get-transaction\"\n          with:\n            transactionId: \"tools.transactionId\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: list-webhook-subscriptions\n          description: \"List all configured webhook subscriptions for the merchant site.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"squarespace-webhooks.list-webhook-subscriptions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-webhook-subscription\n          description: >-\n            Create a new webhook subscription to receive real-time notifications\n            for Squarespace commerce events (order created, order updated, etc).\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"squarespace-webhooks.create-webhook-subscription\"\n          with:\n            endpointUrl: \"tools.endpointUrl\"\n            topics: \"tools.topics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-webhook-subscription\n\
  \          description: \"Delete a webhook subscription by ID.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"squarespace-webhooks.delete-webhook-subscription\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/squarespace/refs/heads/main/capabilities/customer-and-reporting.yaml
tags:
- Analytics
- CRM
- Event Notifications
- Finance
- Reporting
- Squarespace
- Webhooks
tools:
- description: Retrieve customer, subscriber, and donor profiles from Squarespace. Filter by customer status or email address.
  hints:
    idempotent: true
    readOnly: true
  name: list-profiles
- description: Retrieve a specific customer profile by ID.
  hints:
    idempotent: true
    readOnly: true
  name: get-profile
- description: Retrieve financial transaction records for orders and donations. Supports date range filtering for reconciliation workflows.
  hints:
    idempotent: true
    readOnly: true
  name: list-transactions
- description: Retrieve a specific financial transaction by ID.
  hints:
    idempotent: true
    readOnly: true
  name: get-transaction
- description: List all configured webhook subscriptions for the merchant site.
  hints:
    idempotent: true
    readOnly: true
  name: list-webhook-subscriptions
- description: Create a new webhook subscription to receive real-time notifications for Squarespace commerce events (order created, order updated, etc).
  hints:
    idempotent: false
    readOnly: false
  name: create-webhook-subscription
- description: Delete a webhook subscription by ID.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-webhook-subscription
---
