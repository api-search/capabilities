---
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
- list all merchant accounts.
- list payment method settings for a merchant.
- online and in-person payment acceptance.
- chargeback and dispute handling.
- list merchants
- builds marketplace and fintech platforms using adyen balance platform.
- management
- list all stores for a merchant account.
- submit dispute defense documents.
- get applicable defense reasons for a chargeback dispute.
- merchants
- adyen
- list stores
- list stores for a merchant.
- supply defense document
- accept a chargeback dispute.
- get merchant
- list payment method settings
- accept dispute
- get dispute defense reasons
- disputes
- get defense reasons
- list terminals
- submit a defense document for a chargeback dispute.
- list terminals for a merchant.
- manage payment terminals.
- manages merchant accounts, terminals, and dispute responses.
- builds payment integrations using adyen apis and sdks.
- get details of a specific merchant account.
- marketplace and platform fund management.
- manage merchant stores.
- submit a defense document.
- list all adyen merchant accounts.
- list all payment terminals for a merchant account.
- accept a dispute.
- manage merchant accounts.
- retrieve defense reasons for a dispute.
- fintech
- supply dispute defense document
- get dispute defense reasons.
- 'unified capability for building financial products on adyen''s balance platform. combines the configuration api for account holder and card management with the transfers api for fund movement. used by marketplace and platform builders to onboard users, issue cards, and manage fund transfers. primary persona: platform engineer or marketplace developer.'
- accept a chargeback dispute and let it proceed.
- payments
- financial services
- 'unified capability for managing adyen merchant accounts, stores, payment terminals, and dispute resolution. combines management api and disputes api to give operations teams and platform administrators complete control over merchant configuration and chargeback handling. primary persona: merchant operations team or platform administrator.'
- operations
- 'unified capability for accepting and managing online payments. combines the checkout api and payments api to provide merchants and developers with a complete payment acceptance workflow including session creation, payment authorisation, refunds, and cancellations. primary persona: developer or merchant platform engineer.'
- merchant account and balance platform configuration.
- accept chargeback dispute
slug: merchant-account-management
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
