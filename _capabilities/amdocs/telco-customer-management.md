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
- Billing Team
- list telecom customer accounts
- list service subscriptions for a customer
- customer management
- handles customer inquiries and account management
- list invoices for a customer
- 5g
- browse available products and plans
- product and service catalog
- list invoices
- add a service subscription
- list subscriptions
- telecom
- BSS Operator
- telecom customer account management
- retrieve billing invoices for a customer
- unified bss workflow for customer onboarding, billing, and service management
- manages telco bss operations and system configuration
- oss
- saas
- customer billing invoices
- billing
- add a service subscription to a customer account
- list subscriptions for a customer
- browse the service catalog and available plans
- mvno
- create customer
- bss
- list all customer accounts
- Customer Care Agent
- amdocs
- list customers
- onboard a new telecom customer
- manages invoicing, payments, and revenue assurance
- customer subscription management
- list products
- onboard a new customer
- create subscription
slug: telco-customer-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Amdocs Telco Customer Management\n  description: >-\n    Unified workflow for telecom operators managing customer accounts, subscriptions,\n    billing, and service catalog via Amdocs connectX BSS API. Supports BSS operators,\n    customer care agents, and billing teams.\n  tags:\n    - Amdocs\n    - Telecom\n    - BSS\n    - Customer Management\n    - Billing\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AMDOCS_CLIENT_ID: AMDOCS_CLIENT_ID\n      AMDOCS_CLIENT_SECRET: AMDOCS_CLIENT_SECRET\n\ncapability:\n  consumes:\n    - import: amdocs-connectx\n      location: ./shared/connectx-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: amdocs-telco-crm-api\n      description: Unified REST API for telco customer management workflows.\n      resources:\n        - path: /v1/customers\n          name: customers\n          description: Telecom customer account\
  \ management\n          operations:\n            - method: GET\n              name: list-customers\n              description: List all customer accounts\n              call: \"amdocs-connectx.list-customers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-customer\n              description: Onboard a new customer\n              call: \"amdocs-connectx.create-customer\"\n              with:\n                firstName: \"rest.firstName\"\n                lastName: \"rest.lastName\"\n                email: \"rest.email\"\n                customerType: \"rest.customerType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/subscriptions\n          name: subscriptions\n          description: Customer subscription management\n          operations:\n            - method: GET\n              name: list-subscriptions\n\
  \              description: List subscriptions for a customer\n              call: \"amdocs-connectx.list-subscriptions\"\n              with:\n                customerId: \"rest.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-subscription\n              description: Add a service subscription\n              call: \"amdocs-connectx.create-subscription\"\n              with:\n                customerId: \"rest.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/invoices\n          name: invoices\n          description: Customer billing invoices\n          operations:\n            - method: GET\n              name: list-invoices\n              description: List invoices for a customer\n              call: \"amdocs-connectx.list-invoices\"\n              with:\n                customerId:\
  \ \"rest.customerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/products\n          name: products\n          description: Product and service catalog\n          operations:\n            - method: GET\n              name: list-products\n              description: Browse available products and plans\n              call: \"amdocs-connectx.list-products\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: amdocs-telco-crm-mcp\n      transport: http\n      description: MCP server for AI-assisted telco customer management and BSS operations.\n      tools:\n        - name: list-customers\n          description: List telecom customer accounts\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"amdocs-connectx.list-customers\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: create-customer\n          description: Onboard a new telecom customer\n          hints:\n            readOnly: false\n          call: \"amdocs-connectx.create-customer\"\n          with:\n            firstName: \"tools.firstName\"\n            lastName: \"tools.lastName\"\n            email: \"tools.email\"\n            customerType: \"tools.customerType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-subscriptions\n          description: List service subscriptions for a customer\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"amdocs-connectx.list-subscriptions\"\n          with:\n            customerId: \"tools.customerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-subscription\n          description: Add a service subscription to a customer account\n\
  \          hints:\n            readOnly: false\n          call: \"amdocs-connectx.create-subscription\"\n          with:\n            customerId: \"tools.customerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-invoices\n          description: Retrieve billing invoices for a customer\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"amdocs-connectx.list-invoices\"\n          with:\n            customerId: \"tools.customerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-products\n          description: Browse the service catalog and available plans\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"amdocs-connectx.list-products\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amdocs/refs/heads/main/capabilities/telco-customer-management.yaml
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
