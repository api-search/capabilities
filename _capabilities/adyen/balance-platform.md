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
- builds marketplace and fintech platforms using adyen balance platform.
- 'unified capability for building financial products on adyen''s balance platform. combines the configuration api for account holder and card management with the transfers api for fund movement. used by marketplace and platform builders to onboard users, issue cards, and manage fund transfers. primary persona: platform engineer or marketplace developer.'
- create balance account
- marketplaces
- manage payment instruments including virtual and physical cards.
- create payment instrument
- create a balance account.
- get account holder
- merchant account and balance platform configuration.
- issuing
- get balance account details.
- get balance account
- adyen
- create a payment instrument (card).
- issue a virtual or physical payment card for an account holder.
- builds payment integrations using adyen apis and sdks.
- create account holder
- create an account holder.
- create a balance account for an account holder.
- issue card
- online and in-person payment acceptance.
- manage balance accounts.
- transfers
- fintech
- financial services
- manage account holders on the balance platform.
- get balance and details of a balance account.
- chargeback and dispute handling.
- payments
- marketplace and platform fund management.
- balance platform
- 'unified capability for managing adyen merchant accounts, stores, payment terminals, and dispute resolution. combines management api and disputes api to give operations teams and platform administrators complete control over merchant configuration and chargeback handling. primary persona: merchant operations team or platform administrator.'
- create a new account holder on the adyen balance platform.
- manages merchant accounts, terminals, and dispute responses.
- 'unified capability for accepting and managing online payments. combines the checkout api and payments api to provide merchants and developers with a complete payment acceptance workflow including session creation, payment authorisation, refunds, and cancellations. primary persona: developer or merchant platform engineer.'
- retrieve details of an account holder.
- get account holder details.
slug: balance-platform
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
