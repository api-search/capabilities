---
categories:
- payments
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
- manages invoicing, payments, and revenue assurance
- list service subscriptions for a customer
- manages telco bss operations and system configuration
- list telecom customer accounts
- BSS Operator
- handles customer inquiries and account management
- Billing Team
- retrieve billing invoices for a customer
- browse the service catalog and available plans
- customer billing invoices
- list subscriptions
- list all customer accounts
- list invoices for a customer
- billing
- telecom
- Customer Care Agent
- list invoices
- add a service subscription to a customer account
- 5g
- customer management
- unified bss workflow for customer onboarding, billing, and service management
- browse available products and plans
- product and service catalog
- list customers
- create subscription
- onboard a new customer
- oss
- telecom customer account management
- onboard a new telecom customer
- add a service subscription
- list products
- customer subscription management
- bss
- list subscriptions for a customer
- saas
- amdocs
- mvno
- create customer
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
