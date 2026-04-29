---
categories: []
consumed_apis:
- management
- disputes
description: 'Unified capability for managing Adyen merchant accounts, stores, payment terminals, and dispute resolution. Combines Management API and Disputes API to give operations teams and platform administrators complete control over merchant configuration and chargeback handling. Primary persona: Merchant Operations Team or Platform Administrator.'
layout: capability
name: Adyen Merchant Account Management
operations:
- description: List all merchant accounts.
  method: GET
  name: list-merchants
  path: /v1/merchants
- description: List stores for a merchant.
  method: GET
  name: list-stores
  path: /v1/merchants/{merchantId}/stores
- description: List terminals for a merchant.
  method: GET
  name: list-terminals
  path: /v1/merchants/{merchantId}/terminals
- description: Retrieve defense reasons for a dispute.
  method: POST
  name: get-defense-reasons
  path: /v1/disputes/defense-reasons
- description: Submit a defense document.
  method: POST
  name: supply-defense-document
  path: /v1/disputes/documents
- description: Accept a chargeback dispute.
  method: POST
  name: accept-dispute
  path: /v1/disputes/accept
personas: []
provider_name: Adyen
provider_slug: adyen
search_terms:
- get applicable defense reasons for a chargeback dispute.
- list payment method settings for a merchant.
- list stores
- disputes
- adyen
- supply defense document
- get dispute defense reasons.
- fintech
- merchant account and balance platform configuration.
- submit dispute defense documents.
- list stores for a merchant.
- 'unified capability for accepting and managing online payments. combines the checkout api and payments api to provide merchants and developers with a complete payment acceptance workflow including session creation, payment authorisation, refunds, and cancellations. primary persona: developer or merchant platform engineer.'
- payments
- online and in-person payment acceptance.
- marketplace and platform fund management.
- get dispute defense reasons
- accept a chargeback dispute.
- merchants
- submit a defense document for a chargeback dispute.
- retrieve defense reasons for a dispute.
- list all merchant accounts.
- operations
- list terminals for a merchant.
- financial services
- accept dispute
- get merchant
- accept a chargeback dispute and let it proceed.
- builds payment integrations using adyen apis and sdks.
- list terminals
- supply dispute defense document
- manage merchant stores.
- list all stores for a merchant account.
- get defense reasons
- chargeback and dispute handling.
- manages merchant accounts, terminals, and dispute responses.
- list all adyen merchant accounts.
- submit a defense document.
- manage payment terminals.
- 'unified capability for building financial products on adyen''s balance platform. combines the configuration api for account holder and card management with the transfers api for fund movement. used by marketplace and platform builders to onboard users, issue cards, and manage fund transfers. primary persona: platform engineer or marketplace developer.'
- builds marketplace and fintech platforms using adyen balance platform.
- list payment method settings
- list merchants
- management
- manage merchant accounts.
- 'unified capability for managing adyen merchant accounts, stores, payment terminals, and dispute resolution. combines management api and disputes api to give operations teams and platform administrators complete control over merchant configuration and chargeback handling. primary persona: merchant operations team or platform administrator.'
- accept a dispute.
- accept chargeback dispute
- list all payment terminals for a merchant account.
- get details of a specific merchant account.
slug: merchant-account-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Adyen Merchant Account Management\"\n  description: \"Unified capability for managing Adyen merchant accounts, stores, payment terminals, and dispute resolution. Combines Management API and Disputes API to give operations teams and platform administrators complete control over merchant configuration and chargeback handling. Primary persona: Merchant Operations Team or Platform Administrator.\"\n  tags:\n    - Adyen\n    - Management\n    - Merchants\n    - Disputes\n    - Operations\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ADYEN_MANAGEMENT_API_KEY: ADYEN_MANAGEMENT_API_KEY\n      ADYEN_API_KEY: ADYEN_API_KEY\n\ncapability:\n  consumes:\n    - import: management\n      location: ./shared/management.yaml\n    - import: disputes\n      location: ./shared/disputes.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: adyen-merchant-management-api\n   \
  \   description: \"Unified REST API for Adyen merchant account management and dispute handling.\"\n      resources:\n        - path: /v1/merchants\n          name: merchants\n          description: \"Manage merchant accounts.\"\n          operations:\n            - method: GET\n              name: list-merchants\n              description: \"List all merchant accounts.\"\n              call: \"management.list-merchants\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/merchants/{merchantId}/stores\n          name: stores\n          description: \"Manage merchant stores.\"\n          operations:\n            - method: GET\n              name: list-stores\n              description: \"List stores for a merchant.\"\n              call: \"management.list-stores\"\n              with:\n                merchantId: \"rest.merchantId\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n        - path: /v1/merchants/{merchantId}/terminals\n          name: terminals\n          description: \"Manage payment terminals.\"\n          operations:\n            - method: GET\n              name: list-terminals\n              description: \"List terminals for a merchant.\"\n              call: \"management.list-terminals\"\n              with:\n                merchantId: \"rest.merchantId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/disputes/defense-reasons\n          name: dispute-defense-reasons\n          description: \"Get dispute defense reasons.\"\n          operations:\n            - method: POST\n              name: get-defense-reasons\n              description: \"Retrieve defense reasons for a dispute.\"\n              call: \"disputes.get-defense-reasons\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/disputes/documents\n\
  \          name: dispute-documents\n          description: \"Submit dispute defense documents.\"\n          operations:\n            - method: POST\n              name: supply-defense-document\n              description: \"Submit a defense document.\"\n              call: \"disputes.supply-defense-document\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/disputes/accept\n          name: dispute-accept\n          description: \"Accept a dispute.\"\n          operations:\n            - method: POST\n              name: accept-dispute\n              description: \"Accept a chargeback dispute.\"\n              call: \"disputes.accept-dispute\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: adyen-merchant-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Adyen merchant management\
  \ and dispute handling.\"\n      tools:\n        - name: list-merchants\n          description: \"List all Adyen merchant accounts.\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"management.list-merchants\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-merchant\n          description: \"Get details of a specific merchant account.\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"management.get-merchant\"\n          with:\n            merchantId: \"tools.merchantId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-stores\n          description: \"List all stores for a merchant account.\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"management.list-stores\"\n          with:\n            merchantId: \"tools.merchantId\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-terminals\n          description: \"List all payment terminals for a merchant account.\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"management.list-terminals\"\n          with:\n            merchantId: \"tools.merchantId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-payment-method-settings\n          description: \"List payment method settings for a merchant.\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"management.list-payment-methods\"\n          with:\n            merchantId: \"tools.merchantId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-dispute-defense-reasons\n          description: \"Get applicable defense reasons for a chargeback dispute.\"\
  \n          hints:\n            readOnly: true\n            destructive: false\n          call: \"disputes.get-defense-reasons\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: supply-dispute-defense-document\n          description: \"Submit a defense document for a chargeback dispute.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"disputes.supply-defense-document\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: accept-chargeback-dispute\n          description: \"Accept a chargeback dispute and let it proceed.\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"disputes.accept-dispute\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/adyen/refs/heads/main/capabilities/merchant-account-management.yaml
tags:
- Adyen
- Management
- Merchants
- Disputes
- Operations
tools:
- description: List all Adyen merchant accounts.
  hints:
    destructive: false
    readOnly: true
  name: list-merchants
- description: Get details of a specific merchant account.
  hints:
    destructive: false
    readOnly: true
  name: get-merchant
- description: List all stores for a merchant account.
  hints:
    destructive: false
    readOnly: true
  name: list-stores
- description: List all payment terminals for a merchant account.
  hints:
    destructive: false
    readOnly: true
  name: list-terminals
- description: List payment method settings for a merchant.
  hints:
    destructive: false
    readOnly: true
  name: list-payment-method-settings
- description: Get applicable defense reasons for a chargeback dispute.
  hints:
    destructive: false
    readOnly: true
  name: get-dispute-defense-reasons
- description: Submit a defense document for a chargeback dispute.
  hints:
    destructive: false
    readOnly: false
  name: supply-dispute-defense-document
- description: Accept a chargeback dispute and let it proceed.
  hints:
    destructive: true
    readOnly: false
  name: accept-chargeback-dispute
---
