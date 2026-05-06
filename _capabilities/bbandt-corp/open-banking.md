---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Open Banking
operations: []
personas: []
provider_name: BB&T Corp (Truist)
provider_slug: bbandt-corp
search_terms:
- bb&t
- open banking
- truist
- banking
- financial services
slug: open-banking
source_filename: open-banking.yaml
source_heading: Capability Spec
source_yaml: "capability:\n  name: Truist Open Banking\n  description: >-\n    Truist (BB&T + SunTrust) open banking capabilities through the developer.truist.com\n    portal, providing account information and transaction data APIs for personal,\n    small business, and commercial banking customers.\n  categories:\n    - name: Personal and Small Business Accounts\n      description: Account information APIs for retail and small business customers.\n      operations:\n        - name: List Accounts\n          description: Retrieve a list of customer accounts with summary information.\n        - name: Get Account Details\n          description: Retrieve detailed information for a specific account.\n        - name: Get Account Balance\n          description: Retrieve current and available balance for an account.\n    - name: Personal and Small Business Transactions\n      description: Transaction history APIs for retail and small business accounts.\n      operations:\n        - name: List Transactions\n\
  \          description: Retrieve transaction history for an account.\n        - name: Get Transaction Details\n          description: Retrieve details for a specific transaction.\n    - name: Commercial Accounts\n      description: Account information APIs for commercial banking customers.\n      operations:\n        - name: List Commercial Accounts\n          description: Retrieve commercial account list for a business customer.\n        - name: Get Commercial Account Details\n          description: Retrieve details for a commercial account including credit lines.\n        - name: Get Commercial Account Balance\n          description: Retrieve current balance and available credit for a commercial account.\n    - name: Commercial Account Transactions\n      description: Transaction history APIs for commercial banking accounts.\n      operations:\n        - name: List Commercial Transactions\n          description: Retrieve transaction history for commercial accounts.\n    - name: Association\
  \ Services\n      description: Specialized APIs for homeowner and membership association banking.\n      operations:\n        - name: Process Dues Payment\n          description: Accept and process membership dues payments.\n        - name: Generate Financial Report\n          description: Generate financial reports for association board reporting.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bbandt-corp/refs/heads/main/capabilities/open-banking.yaml
tags: []
tools: []
---
