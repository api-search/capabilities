---
categories: []
consumed_apis: []
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
- create a balance account for an account holder.
- 'unified capability for managing adyen merchant accounts, stores, payment terminals, and dispute resolution. combines management api and disputes api to give operations teams and platform administrators complete control over merchant configuration and chargeback handling. primary persona: merchant operations team or platform administrator.'
- create an account holder.
- create account holder
- issue a virtual or physical payment card for an account holder.
- marketplace and platform fund management.
- create a payment instrument (card).
- marketplaces
- transfers
- manage payment instruments including virtual and physical cards.
- adyen
- create balance account
- fintech
- 'unified capability for accepting and managing online payments. combines the checkout api and payments api to provide merchants and developers with a complete payment acceptance workflow including session creation, payment authorisation, refunds, and cancellations. primary persona: developer or merchant platform engineer.'
- chargeback and dispute handling.
- create a new account holder on the adyen balance platform.
- online and in-person payment acceptance.
- financial services
- 'unified capability for building financial products on adyen''s balance platform. combines the configuration api for account holder and card management with the transfers api for fund movement. used by marketplace and platform builders to onboard users, issue cards, and manage fund transfers. primary persona: platform engineer or marketplace developer.'
- manage balance accounts.
- builds payment integrations using adyen apis and sdks.
- manages merchant accounts, terminals, and dispute responses.
- issue card
- get balance and details of a balance account.
- balance platform
- create a balance account.
- get account holder
- get balance account details.
- payments
- builds marketplace and fintech platforms using adyen balance platform.
- issuing
- create payment instrument
- retrieve details of an account holder.
- manage account holders on the balance platform.
- merchant account and balance platform configuration.
- get account holder details.
slug: balance-platform
source_filename: balance-platform.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Adyen Balance Platform\n  description: 'Unified capability for building financial products on Adyen''s balance platform. Combines the Configuration\n    API for account holder and card management with the Transfers API for fund movement. Used by marketplace and platform\n    builders to onboard users, issue cards, and manage fund transfers. Primary persona: Platform Engineer or Marketplace Developer.'\n  tags:\n  - Adyen\n  - Balance Platform\n  - Marketplaces\n  - Issuing\n  - Transfers\n  - Fintech\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ADYEN_BALANCE_PLATFORM_API_KEY: ADYEN_BALANCE_PLATFORM_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: configuration\n    baseUri: https://balanceplatform-api-test.adyen.com/bcl/v2\n    description: Adyen Balance Platform Configuration API.\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{ADYEN_BALANCE_PLATFORM_API_KEY}}'\n\
  \      placement: header\n    resources:\n    - name: account-holders\n      path: /accountHolders\n      description: Manage account holders.\n      operations:\n      - name: create-account-holder\n        method: POST\n        description: Create an account holder.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-account-holder\n        method: GET\n        description: Get an account holder.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The account holder identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: balance-accounts\n      path: /balanceAccounts\n      description: Manage balance accounts.\n      operations:\n      - name: create-balance-account\n        method: POST\n        description:\
  \ Create a balance account.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-balance-account\n        method: GET\n        description: Get a balance account.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The balance account identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payment-instruments\n      path: /paymentInstruments\n      description: Manage payment instruments including cards.\n      operations:\n      - name: create-payment-instrument\n        method: POST\n        description: Create a payment instrument (card).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8082\n  \
  \  namespace: adyen-balance-platform-api\n    description: Unified REST API for Adyen balance platform operations.\n    resources:\n    - path: /v1/account-holders\n      name: account-holders\n      description: Manage account holders on the balance platform.\n      operations:\n      - method: POST\n        name: create-account-holder\n        description: Create an account holder.\n        call: configuration.create-account-holder\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-account-holder\n        description: Get account holder details.\n        call: configuration.get-account-holder\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/balance-accounts\n      name: balance-accounts\n      description: Manage balance accounts.\n      operations:\n      - method: POST\n        name: create-balance-account\n        description: Create a balance\
  \ account.\n        call: configuration.create-balance-account\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-balance-account\n        description: Get balance account details.\n        call: configuration.get-balance-account\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payment-instruments\n      name: payment-instruments\n      description: Manage payment instruments including virtual and physical cards.\n      operations:\n      - method: POST\n        name: create-payment-instrument\n        description: Create a payment instrument (card).\n        call: configuration.create-payment-instrument\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9082\n    namespace: adyen-balance-platform-mcp\n    transport: http\n    description: MCP server for AI-assisted Adyen balance platform management.\n\
  \    tools:\n    - name: create-account-holder\n      description: Create a new account holder on the Adyen balance platform.\n      hints:\n        readOnly: false\n        destructive: false\n      call: configuration.create-account-holder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account-holder\n      description: Retrieve details of an account holder.\n      hints:\n        readOnly: true\n        destructive: false\n      call: configuration.get-account-holder\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-balance-account\n      description: Create a balance account for an account holder.\n      hints:\n        readOnly: false\n        destructive: false\n      call: configuration.create-balance-account\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-balance-account\n      description: Get balance and details of a balance account.\n\
  \      hints:\n        readOnly: true\n        destructive: false\n      call: configuration.get-balance-account\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: issue-card\n      description: Issue a virtual or physical payment card for an account holder.\n      hints:\n        readOnly: false\n        destructive: false\n      call: configuration.create-payment-instrument\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
