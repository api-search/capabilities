---
api_specs:
- filename: regions-open-banking-openapi.yml
  format: yaml
  label: regions-open-banking
  slug: regions-open-banking
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/regions-financial/refs/heads/main/openapi/regions-open-banking-openapi.yml
categories: []
consumed_apis:
- regions-open-banking
description: Workflow capability for Regions Bank's open banking platform enabling fintech applications, financial management tools, and data aggregators to securely access customer account data, transaction history, and payment initiation with customer consent under FDX standards and CFPB open banking compliance.
layout: capability
name: Regions Open Banking
operations:
- description: List all accounts for the authenticated customer
  method: GET
  name: list-accounts
  path: /v1/accounts
- description: Get balance and details for a specific account
  method: GET
  name: get-account
  path: /v1/accounts/{accountId}
- description: Retrieve transaction history for an account
  method: GET
  name: list-transactions
  path: /v1/accounts/{accountId}/transactions
- description: Get the authenticated customer's profile
  method: GET
  name: get-current-customer
  path: /v1/customers/current
- description: Initiate a payment or internal transfer
  method: POST
  name: initiate-payment
  path: /v1/payments
- description: Get status for a specific payment
  method: GET
  name: get-payment
  path: /v1/payments/{paymentId}
- description: List active data sharing consents
  method: GET
  name: list-consents
  path: /v1/consents
personas: []
provider_name: regions-financial
provider_slug: regions-financial
search_terms:
- wealth management
- financial services
- payment status
- get payment
- consent management
- get status for a specific payment
- retrieve transaction history for an account
- list consents
- revoke a specific data sharing consent previously granted to a third party
- get balance and details for a specific account
- retrieve transaction history for an account with optional date filtering
- get the authenticated customer's profile including name and contact information
- payment initiation
- individual account details
- banking
- get the authenticated customer's profile
- list all accounts for the authenticated customer
- list active data sharing consents the customer has granted to third parties
- get account
- fortune 500
- payments
- list accounts
- consumer banking
- initiate a payment or internal transfer
- list transactions
- list active data sharing consents
- check the status of a previously initiated payment
- authenticated customer profile
- account aggregation
- revoke consent
- get current customer
- initiate payment
- customer account listing and details
- personal finance
- fdx
- account transaction history
- get balance and full details for a specific regions account
- list all bank accounts including checking, savings, credit cards, and loans for the customer
- open banking
- initiate an ach payment, wire transfer, or internal account transfer
slug: open-banking
source_filename: open-banking.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Regions Open Banking\"\n  description: >-\n    Workflow capability for Regions Bank's open banking platform enabling\n    fintech applications, financial management tools, and data aggregators\n    to securely access customer account data, transaction history, and\n    payment initiation with customer consent under FDX standards and\n    CFPB open banking compliance.\n  tags:\n    - Banking\n    - Open Banking\n    - FDX\n    - Account Aggregation\n    - Personal Finance\n    - Payments\n    - Consumer Banking\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      REGIONS_ACCESS_TOKEN: REGIONS_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: regions-open-banking\n      location: ./shared/regions-open-banking.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: regions-open-banking-api\n      description: \"Unified REST API for Regions open banking account\
  \ data, transactions, and payments.\"\n      resources:\n        - path: /v1/accounts\n          name: accounts\n          description: Customer account listing and details\n          operations:\n            - method: GET\n              name: list-accounts\n              description: List all accounts for the authenticated customer\n              call: \"regions-open-banking.list-accounts\"\n              with:\n                accountType: \"rest.accountType\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/accounts/{accountId}\n          name: account-detail\n          description: Individual account details\n          operations:\n            - method: GET\n              name: get-account\n              description: Get balance and details for a specific account\n              call: \"regions-open-banking.get-account\"\n              with:\n                accountId: \"\
  rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/accounts/{accountId}/transactions\n          name: transactions\n          description: Account transaction history\n          operations:\n            - method: GET\n              name: list-transactions\n              description: Retrieve transaction history for an account\n              call: \"regions-open-banking.list-transactions\"\n              with:\n                accountId: \"rest.accountId\"\n                startDate: \"rest.startDate\"\n                endDate: \"rest.endDate\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/customers/current\n          name: customer\n          description: Authenticated customer profile\n          operations:\n            - method: GET\n              name: get-current-customer\n          \
  \    description: Get the authenticated customer's profile\n              call: \"regions-open-banking.get-current-customer\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/payments\n          name: payments\n          description: Payment initiation\n          operations:\n            - method: POST\n              name: initiate-payment\n              description: Initiate a payment or internal transfer\n              call: \"regions-open-banking.initiate-payment\"\n              with:\n                sourceAccountId: \"rest.sourceAccountId\"\n                destinationAccountId: \"rest.destinationAccountId\"\n                amount: \"rest.amount\"\n                paymentType: \"rest.paymentType\"\n                memo: \"rest.memo\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/payments/{paymentId}\n          name: payment-detail\n \
  \         description: Payment status\n          operations:\n            - method: GET\n              name: get-payment\n              description: Get status for a specific payment\n              call: \"regions-open-banking.get-payment\"\n              with:\n                paymentId: \"rest.paymentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/consents\n          name: consents\n          description: Consent management\n          operations:\n            - method: GET\n              name: list-consents\n              description: List active data sharing consents\n              call: \"regions-open-banking.list-consents\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: regions-open-banking-mcp\n      transport: http\n      description: \"MCP server for AI-assisted financial data aggregation and account\
  \ management.\"\n      tools:\n        - name: list-accounts\n          description: List all bank accounts including checking, savings, credit cards, and loans for the customer\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"regions-open-banking.list-accounts\"\n          with:\n            accountType: \"tools.accountType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-account\n          description: Get balance and full details for a specific Regions account\n          hints:\n            readOnly: true\n          call: \"regions-open-banking.get-account\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-transactions\n          description: Retrieve transaction history for an account with optional date filtering\n          hints:\n            readOnly: true\n\
  \          call: \"regions-open-banking.list-transactions\"\n          with:\n            accountId: \"tools.accountId\"\n            startDate: \"tools.startDate\"\n            endDate: \"tools.endDate\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-current-customer\n          description: Get the authenticated customer's profile including name and contact information\n          hints:\n            readOnly: true\n          call: \"regions-open-banking.get-current-customer\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: initiate-payment\n          description: Initiate an ACH payment, wire transfer, or internal account transfer\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"regions-open-banking.initiate-payment\"\n          with:\n            sourceAccountId:\
  \ \"tools.sourceAccountId\"\n            destinationAccountId: \"tools.destinationAccountId\"\n            amount: \"tools.amount\"\n            paymentType: \"tools.paymentType\"\n            memo: \"tools.memo\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-payment\n          description: Check the status of a previously initiated payment\n          hints:\n            readOnly: true\n          call: \"regions-open-banking.get-payment\"\n          with:\n            paymentId: \"tools.paymentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-consents\n          description: List active data sharing consents the customer has granted to third parties\n          hints:\n            readOnly: true\n          call: \"regions-open-banking.list-consents\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: revoke-consent\n\
  \          description: Revoke a specific data sharing consent previously granted to a third party\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"regions-open-banking.revoke-consent\"\n          with:\n            consentId: \"tools.consentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/regions-financial/refs/heads/main/capabilities/open-banking.yaml
tags:
- Banking
- Open Banking
- FDX
- Account Aggregation
- Personal Finance
- Payments
- Consumer Banking
tools:
- description: List all bank accounts including checking, savings, credit cards, and loans for the customer
  hints:
    openWorld: false
    readOnly: true
  name: list-accounts
- description: Get balance and full details for a specific Regions account
  hints:
    readOnly: true
  name: get-account
- description: Retrieve transaction history for an account with optional date filtering
  hints:
    readOnly: true
  name: list-transactions
- description: Get the authenticated customer's profile including name and contact information
  hints:
    readOnly: true
  name: get-current-customer
- description: Initiate an ACH payment, wire transfer, or internal account transfer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: initiate-payment
- description: Check the status of a previously initiated payment
  hints:
    readOnly: true
  name: get-payment
- description: List active data sharing consents the customer has granted to third parties
  hints:
    readOnly: true
  name: list-consents
- description: Revoke a specific data sharing consent previously granted to a third party
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: revoke-consent
---
