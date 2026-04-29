---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Blackstone Investor Portal
operations: []
personas: []
provider_name: Blackstone
provider_slug: blackstone
search_terms:
- alternative assets
- private equity
- finance
- real estate
- investment management
slug: blackstone-investor-portal
source_yaml: "name: Blackstone Investor Portal Capability\ndescription: >-\n  Naftiko capability definition for Blackstone Investor Portal providing fund\n  reporting, capital account statements, and investor document access for\n  institutional limited partners.\nversion: 1.0.0\ncapabilities:\n  - name: listFunds\n    description: List Blackstone funds accessible to the authenticated investor\n    method: GET\n    path: /funds\n  - name: getFund\n    description: Retrieve details and performance metrics for a specific fund\n    method: GET\n    path: /funds/{fundId}\n    parameters:\n      - name: fundId\n        type: string\n        required: true\n  - name: getInvestorAccount\n    description: Retrieve capital account details for a specific investor commitment\n    method: GET\n    path: /accounts/{accountId}\n    parameters:\n      - name: accountId\n        type: string\n        required: true\n  - name: listDocuments\n    description: List investor documents including capital call\
  \ and distribution notices\n    method: GET\n    path: /accounts/{accountId}/documents\n    parameters:\n      - name: accountId\n        type: string\n        required: true\n      - name: type\n        type: string\n        required: false\n        description: Filter by document type (capital_call, distribution, financial_statement, tax)\n  - name: getDocument\n    description: Download a specific investor document\n    method: GET\n    path: /documents/{documentId}\n  - name: listCapitalCalls\n    description: List capital call notices for an investor account\n    method: GET\n    path: /accounts/{accountId}/capital-calls\n  - name: listDistributions\n    description: List distribution notices for an investor account\n    method: GET\n    path: /accounts/{accountId}/distributions\nauthentication:\n  type: oauth2\n  flows:\n    authorizationCode:\n      authorizationUrl: https://investor.blackstone.com/oauth/authorize\n      tokenUrl: https://investor.blackstone.com/oauth/token\n  \
  \    scopes:\n        accounts:read: Read investor account data\n        documents:read: Access investor documents\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/blackstone/refs/heads/main/capabilities/blackstone-investor-portal.yaml
tags: []
tools: []
---
