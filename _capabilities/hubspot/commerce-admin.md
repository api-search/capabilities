---
categories:
- content-management
consumed_apis:
- commerce-payments
- commerce-subscriptions
- cms-hubdb
- cms-pages
- domains
description: Unified workflow for admins to manage commerce payments, subscriptions, HubDB data tables, CMS pages, and domains. Combines commerce operations with CMS data management for platform administration.
layout: capability
name: HubSpot Commerce Admin
operations:
- description: List payments
  method: GET
  name: list-payments
  path: /v1/payments
- description: Create payment
  method: POST
  name: create-payment
  path: /v1/payments
- description: Get payment
  method: GET
  name: get-payment
  path: /v1/payments/{commercePaymentId}
- description: List subscriptions
  method: GET
  name: list-subscriptions
  path: /v1/subscriptions
- description: Get subscription
  method: GET
  name: get-subscription
  path: /v1/subscriptions/{subscriptionId}
personas: []
provider_name: HubSpot
provider_slug: hubspot
search_terms:
- admin
- get payment
- crm
- commerce
- analytics
- sales
- list payments
- get a payment by id
- list subscriptions
- get a subscription by id
- update payment
- operations
- customer service
- update a commerce payment
- create a commerce subscription
- create a commerce payment
- individual payment
- content
- email marketing
- cms
- hubspot
- search commerce payments
- search payments
- hubdb
- marketing
- commerce payments
- individual subscription
- get subscription
- list all commerce subscriptions
- commerce subscriptions
- search subscriptions
- list all commerce payments
- marketing automation
- search commerce subscriptions
- create subscription
- create payment
slug: commerce-admin
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"HubSpot Commerce Admin\"\n  description: \"Unified workflow for admins to manage commerce payments, subscriptions, HubDB data tables, CMS pages, and domains. Combines commerce operations with CMS data management for platform administration.\"\n  tags:\n    - HubSpot\n    - Commerce\n    - Admin\n    - CMS\n    - HubDB\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      HUBSPOT_ACCESS_TOKEN: HUBSPOT_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: commerce-payments\n      location: ./shared/commerce-payments.yaml\n    - import: commerce-subscriptions\n      location: ./shared/commerce-subscriptions.yaml\n    - import: cms-hubdb\n      location: ./shared/cms-hubdb-api.yaml\n    - import: cms-pages\n      location: ./shared/cms-pages-api.yaml\n    - import: domains\n      location: ./shared/domains-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8084\n      namespace:\
  \ commerce-admin-api\n      description: \"Unified REST API for commerce operations, data table management, and CMS administration.\"\n      resources:\n        - path: /v1/payments\n          name: payments\n          description: \"Commerce payments\"\n          operations:\n            - { method: GET, name: list-payments, description: \"List payments\", call: \"commerce-payments.list-payments\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n            - { method: POST, name: create-payment, description: \"Create payment\", call: \"commerce-payments.create-payment\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - path: /v1/payments/{commercePaymentId}\n          name: payment-by-id\n          description: \"Individual payment\"\n          operations:\n            - { method: GET, name: get-payment, description: \"Get payment\", call: \"commerce-payments.get-payment\", with: { commercePaymentId: \"rest.commercePaymentId\" }, outputParameters: [{ type:\
  \ object, mapping: \"$.\" }] }\n        - path: /v1/subscriptions\n          name: subscriptions\n          description: \"Commerce subscriptions\"\n          operations:\n            - { method: GET, name: list-subscriptions, description: \"List subscriptions\", call: \"commerce-subscriptions.list-subscriptions\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - path: /v1/subscriptions/{subscriptionId}\n          name: subscription-by-id\n          description: \"Individual subscription\"\n          operations:\n            - { method: GET, name: get-subscription, description: \"Get subscription\", call: \"commerce-subscriptions.get-subscription\", with: { subscriptionId: \"rest.subscriptionId\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n\n    - type: mcp\n      port: 9094\n      namespace: commerce-admin-mcp\n      transport: http\n      description: \"MCP server for AI-assisted commerce administration, payment tracking, and data management.\"\n   \
  \   tools:\n        - { name: list-payments, description: \"List all commerce payments\", hints: { readOnly: true, idempotent: true }, call: \"commerce-payments.list-payments\", with: { limit: \"tools.limit\", after: \"tools.after\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: get-payment, description: \"Get a payment by ID\", hints: { readOnly: true, idempotent: true }, call: \"commerce-payments.get-payment\", with: { commercePaymentId: \"tools.commercePaymentId\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: create-payment, description: \"Create a commerce payment\", hints: { readOnly: false }, call: \"commerce-payments.create-payment\", with: { properties: \"tools.properties\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: update-payment, description: \"Update a commerce payment\", hints: { readOnly: false, idempotent: true }, call: \"commerce-payments.update-payment\", with: { commercePaymentId:\
  \ \"tools.commercePaymentId\", properties: \"tools.properties\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: search-payments, description: \"Search commerce payments\", hints: { readOnly: true, idempotent: true }, call: \"commerce-payments.search-payments\", with: { filterGroups: \"tools.filterGroups\", query: \"tools.query\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-subscriptions, description: \"List all commerce subscriptions\", hints: { readOnly: true, idempotent: true }, call: \"commerce-subscriptions.list-subscriptions\", with: { limit: \"tools.limit\", after: \"tools.after\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: get-subscription, description: \"Get a subscription by ID\", hints: { readOnly: true, idempotent: true }, call: \"commerce-subscriptions.get-subscription\", with: { subscriptionId: \"tools.subscriptionId\" }, outputParameters: [{ type: object, mapping: \"$.\"\
  \ }] }\n        - { name: create-subscription, description: \"Create a commerce subscription\", hints: { readOnly: false }, call: \"commerce-subscriptions.create-subscription\", with: { properties: \"tools.properties\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: search-subscriptions, description: \"Search commerce subscriptions\", hints: { readOnly: true, idempotent: true }, call: \"commerce-subscriptions.search-subscriptions\", with: { filterGroups: \"tools.filterGroups\", query: \"tools.query\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hubspot/refs/heads/main/capabilities/commerce-admin.yaml
tags:
- HubSpot
- Commerce
- Admin
- CMS
- HubDB
tools:
- description: List all commerce payments
  hints:
    idempotent: true
    readOnly: true
  name: list-payments
- description: Get a payment by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-payment
- description: Create a commerce payment
  hints:
    readOnly: false
  name: create-payment
- description: Update a commerce payment
  hints:
    idempotent: true
    readOnly: false
  name: update-payment
- description: Search commerce payments
  hints:
    idempotent: true
    readOnly: true
  name: search-payments
- description: List all commerce subscriptions
  hints:
    idempotent: true
    readOnly: true
  name: list-subscriptions
- description: Get a subscription by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-subscription
- description: Create a commerce subscription
  hints:
    readOnly: false
  name: create-subscription
- description: Search commerce subscriptions
  hints:
    idempotent: true
    readOnly: true
  name: search-subscriptions
---
