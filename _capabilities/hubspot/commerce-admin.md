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
- search subscriptions
- get a subscription by id
- individual payment
- create a commerce subscription
- list subscriptions
- list payments
- list all commerce payments
- operations
- individual subscription
- hubspot
- create payment
- marketing automation
- crm
- search payments
- list all commerce subscriptions
- content
- search commerce subscriptions
- marketing
- get payment
- get subscription
- search commerce payments
- hubdb
- sales
- update a commerce payment
- create subscription
- cms
- customer service
- analytics
- commerce
- get a payment by id
- admin
- update payment
- email marketing
- commerce subscriptions
- commerce payments
- create a commerce payment
slug: commerce-admin
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
