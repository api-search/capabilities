---
categories: []
consumed_apis:
- configuration
description: 'Unified capability for building financial products on Adyen''s balance platform. Combines the Configuration API for account holder and card management with the Transfers API for fund movement. Used by marketplace and platform builders to onboard users, issue cards, and manage fund transfers. Primary persona: Platform Engineer or Marketplace Developer.'
layout: capability
name: Adyen Balance Platform
operations:
- description: Create an account holder.
  method: POST
  name: create-account-holder
  path: /v1/account-holders
- description: Get account holder details.
  method: GET
  name: get-account-holder
  path: /v1/account-holders
- description: Create a balance account.
  method: POST
  name: create-balance-account
  path: /v1/balance-accounts
- description: Get balance account details.
  method: GET
  name: get-balance-account
  path: /v1/balance-accounts
- description: Create a payment instrument (card).
  method: POST
  name: create-payment-instrument
  path: /v1/payment-instruments
personas: []
provider_name: Adyen
provider_slug: adyen
search_terms:
- get balance account
- create payment instrument
- adyen
- create a payment instrument (card).
- get balance account details.
- get account holder
- create a balance account for an account holder.
- balance platform
- issue card
- marketplaces
- manage account holders on the balance platform.
- manage payment instruments including virtual and physical cards.
- financial services
- get balance and details of a balance account.
- transfers
- create a balance account.
- 'unified capability for managing adyen merchant accounts, stores, payment terminals, and dispute resolution. combines management api and disputes api to give operations teams and platform administrators complete control over merchant configuration and chargeback handling. primary persona: merchant operations team or platform administrator.'
- payments
- marketplace and platform fund management.
- issue a virtual or physical payment card for an account holder.
- 'unified capability for accepting and managing online payments. combines the checkout api and payments api to provide merchants and developers with a complete payment acceptance workflow including session creation, payment authorisation, refunds, and cancellations. primary persona: developer or merchant platform engineer.'
- manages merchant accounts, terminals, and dispute responses.
- create a new account holder on the adyen balance platform.
- get account holder details.
- chargeback and dispute handling.
- retrieve details of an account holder.
- builds marketplace and fintech platforms using adyen balance platform.
- online and in-person payment acceptance.
- manage balance accounts.
- create balance account
- create account holder
- create an account holder.
- 'unified capability for building financial products on adyen''s balance platform. combines the configuration api for account holder and card management with the transfers api for fund movement. used by marketplace and platform builders to onboard users, issue cards, and manage fund transfers. primary persona: platform engineer or marketplace developer.'
- fintech
- builds payment integrations using adyen apis and sdks.
- merchant account and balance platform configuration.
- issuing
slug: balance-platform
source_filename: balance-platform.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Adyen Balance Platform\"\n  description: \"Unified capability for building financial products on Adyen's balance platform. Combines the Configuration API for account holder and card management with the Transfers API for fund movement. Used by marketplace and platform builders to onboard users, issue cards, and manage fund transfers. Primary persona: Platform Engineer or Marketplace Developer.\"\n  tags:\n    - Adyen\n    - Balance Platform\n    - Marketplaces\n    - Issuing\n    - Transfers\n    - Fintech\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ADYEN_BALANCE_PLATFORM_API_KEY: ADYEN_BALANCE_PLATFORM_API_KEY\n\ncapability:\n  consumes:\n    - import: configuration\n      location: ./shared/configuration.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: adyen-balance-platform-api\n      description: \"Unified REST API for Adyen balance platform operations.\"\
  \n      resources:\n        - path: /v1/account-holders\n          name: account-holders\n          description: \"Manage account holders on the balance platform.\"\n          operations:\n            - method: POST\n              name: create-account-holder\n              description: \"Create an account holder.\"\n              call: \"configuration.create-account-holder\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-account-holder\n              description: \"Get account holder details.\"\n              call: \"configuration.get-account-holder\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/balance-accounts\n          name: balance-accounts\n          description: \"Manage balance accounts.\"\n          operations:\n            - method: POST\n     \
  \         name: create-balance-account\n              description: \"Create a balance account.\"\n              call: \"configuration.create-balance-account\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-balance-account\n              description: \"Get balance account details.\"\n              call: \"configuration.get-balance-account\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/payment-instruments\n          name: payment-instruments\n          description: \"Manage payment instruments including virtual and physical cards.\"\n          operations:\n            - method: POST\n              name: create-payment-instrument\n              description: \"Create a payment instrument (card).\"\n              call: \"configuration.create-payment-instrument\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9082\n      namespace: adyen-balance-platform-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Adyen balance platform management.\"\n      tools:\n        - name: create-account-holder\n          description: \"Create a new account holder on the Adyen balance platform.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"configuration.create-account-holder\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-account-holder\n          description: \"Retrieve details of an account holder.\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"configuration.get-account-holder\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n   \
  \           mapping: \"$.\"\n        - name: create-balance-account\n          description: \"Create a balance account for an account holder.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"configuration.create-balance-account\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-balance-account\n          description: \"Get balance and details of a balance account.\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"configuration.get-balance-account\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: issue-card\n          description: \"Issue a virtual or physical payment card for an account holder.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"configuration.create-payment-instrument\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/adyen/refs/heads/main/capabilities/balance-platform.yaml
tags:
- Adyen
- Balance Platform
- Marketplaces
- Issuing
- Transfers
- Fintech
tools:
- description: Create a new account holder on the Adyen balance platform.
  hints:
    destructive: false
    readOnly: false
  name: create-account-holder
- description: Retrieve details of an account holder.
  hints:
    destructive: false
    readOnly: true
  name: get-account-holder
- description: Create a balance account for an account holder.
  hints:
    destructive: false
    readOnly: false
  name: create-balance-account
- description: Get balance and details of a balance account.
  hints:
    destructive: false
    readOnly: true
  name: get-balance-account
- description: Issue a virtual or physical payment card for an account holder.
  hints:
    destructive: false
    readOnly: false
  name: issue-card
---
