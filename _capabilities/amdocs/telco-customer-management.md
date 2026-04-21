---
consumed_apis:
- amdocs-connectx
description: Unified workflow for telecom operators managing customer accounts, subscriptions, billing, and service catalog via Amdocs connectX BSS API. Supports BSS operators, customer care agents, and billing teams.
layout: capability
name: Amdocs Telco Customer Management
operations:
- description: List all customer accounts
  method: GET
  name: list-customers
  path: /v1/customers
- description: Onboard a new customer
  method: POST
  name: create-customer
  path: /v1/customers
- description: List subscriptions for a customer
  method: GET
  name: list-subscriptions
  path: /v1/subscriptions
- description: Add a service subscription
  method: POST
  name: create-subscription
  path: /v1/subscriptions
- description: List invoices for a customer
  method: GET
  name: list-invoices
  path: /v1/invoices
- description: Browse available products and plans
  method: GET
  name: list-products
  path: /v1/products
personas: []
provider_name: Amdocs
provider_slug: amdocs
search_terms:
- BSS Operator
- browse the service catalog and available plans
- onboard a new customer
- browse available products and plans
- amdocs
- mvno
- oss
- unified bss workflow for customer onboarding, billing, and service management
- telecom
- customer subscription management
- 5g
- customer management
- list subscriptions
- add a service subscription to a customer account
- list subscriptions for a customer
- telecom customer account management
- billing
- list customers
- list products
- onboard a new telecom customer
- manages telco bss operations and system configuration
- list invoices for a customer
- customer billing invoices
- Customer Care Agent
- add a service subscription
- list invoices
- handles customer inquiries and account management
- manages invoicing, payments, and revenue assurance
- Billing Team
- create subscription
- list telecom customer accounts
- retrieve billing invoices for a customer
- list all customer accounts
- list service subscriptions for a customer
- create customer
- bss
- product and service catalog
- saas
slug: telco-customer-management
tags:
- Amdocs
- Telecom
- BSS
- Customer Management
- Billing
tools:
- description: List telecom customer accounts
  hints:
    openWorld: true
    readOnly: true
  name: list-customers
- description: Onboard a new telecom customer
  hints:
    readOnly: false
  name: create-customer
- description: List service subscriptions for a customer
  hints:
    openWorld: true
    readOnly: true
  name: list-subscriptions
- description: Add a service subscription to a customer account
  hints:
    readOnly: false
  name: create-subscription
- description: Retrieve billing invoices for a customer
  hints:
    openWorld: true
    readOnly: true
  name: list-invoices
- description: Browse the service catalog and available plans
  hints:
    openWorld: true
    readOnly: true
  name: list-products
---
