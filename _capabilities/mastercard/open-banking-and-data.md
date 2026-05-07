---
categories: []
consumed_apis: []
description: Unified workflow for fintech developers and data analysts to access open banking data, consumer-permissioned financial data, and credit analytics across Mastercard's data platform.
layout: capability
name: Mastercard Open Banking and Data Analytics
operations:
- description: Retrieve consumer accounts
  method: GET
  name: get-accounts
  path: /v1/accounts
- description: Get consumer credit analytics
  method: POST
  name: get-consumer-analytics
  path: /v1/consumer-analytics
- description: Get small business credit analytics
  method: POST
  name: get-small-business-analytics
  path: /v1/small-business-analytics
personas: []
provider_name: Mastercard
provider_slug: mastercard
search_terms:
- get consumer analytics
- get consumer accounts
- fraud detection
- open banking account data
- data analytics
- small business credit analytics
- retrieve consumer accounts via open banking
- get consumer credit analytics and spending insights
- get accounts
- fintech
- consumer credit analytics
- get small business analytics
- financial services
- credit analytics
- credit cards
- retrieve consumer accounts
- get consumer credit analytics
- open banking
- get small business credit analytics
- payments
- retrieve account transactions via open banking
- digital identity
- get account transactions
- mastercard
slug: open-banking-and-data
source_filename: open-banking-and-data.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Mastercard Open Banking and Data Analytics\n  description: Unified workflow for fintech developers and data analysts to access open banking data, consumer-permissioned\n    financial data, and credit analytics across Mastercard's data platform.\n  tags:\n  - Mastercard\n  - Open Banking\n  - Data Analytics\n  - Credit Analytics\n  - Fintech\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    MASTERCARD_CONSUMER_KEY: MASTERCARD_CONSUMER_KEY\n    MASTERCARD_SIGNING_KEY: MASTERCARD_SIGNING_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: open-banking\n    baseUri: https://api.mastercard.com/open-banking\n    description: Mastercard Open Banking Solutions API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: accounts\n      path: /accounts\n      description: Open banking\
  \ account operations\n      operations:\n      - name: get-accounts\n        method: GET\n        description: Retrieve consumer accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-transactions\n        method: GET\n        description: Retrieve account transactions\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: consumer-credit-analytics\n    baseUri: https://api.mastercard.com/credit-analytics/consumer\n    description: Mastercard Consumer Credit Analytics API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n\
  \    - name: analytics\n      path: /analytics\n      description: Credit analytics operations\n      operations:\n      - name: get-credit-analytics\n        method: POST\n        description: Get consumer credit analytics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n  - type: http\n    namespace: small-biz-credit-analytics\n    baseUri: https://api.mastercard.com/credit-analytics/small-business\n    description: Mastercard Small Business Credit Analytics API\n    authentication:\n      type: oauth1\n      consumerKey: '{{MASTERCARD_CONSUMER_KEY}}'\n      signingKey: '{{MASTERCARD_SIGNING_KEY}}'\n    resources:\n    - name: analytics\n      path: /analytics\n      description: Small business credit analytics\n      operations:\n      - name: get-sb-credit-analytics\n        method: POST\n        description: Get\
  \ small business credit analytics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n  exposes:\n  - type: rest\n    port: 8086\n    namespace: open-banking-data-api\n    description: Unified REST API for open banking and data analytics.\n    resources:\n    - path: /v1/accounts\n      name: accounts\n      description: Open banking account data\n      operations:\n      - method: GET\n        name: get-accounts\n        description: Retrieve consumer accounts\n        call: open-banking.get-accounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/consumer-analytics\n      name: consumer-analytics\n      description: Consumer credit analytics\n      operations:\n      - method: POST\n        name: get-consumer-analytics\n        description: Get consumer credit analytics\n    \
  \    call: consumer-credit-analytics.get-credit-analytics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/small-business-analytics\n      name: small-business-analytics\n      description: Small business credit analytics\n      operations:\n      - method: POST\n        name: get-small-business-analytics\n        description: Get small business credit analytics\n        call: small-biz-credit-analytics.get-sb-credit-analytics\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9096\n    namespace: open-banking-data-mcp\n    transport: http\n    description: MCP server for AI-assisted open banking and data analytics.\n    tools:\n    - name: get-consumer-accounts\n      description: Retrieve consumer accounts via open banking\n      hints:\n        readOnly: true\n      call: open-banking.get-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account-transactions\n\
  \      description: Retrieve account transactions via open banking\n      hints:\n        readOnly: true\n      call: open-banking.get-transactions\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-consumer-credit-analytics\n      description: Get consumer credit analytics and spending insights\n      hints:\n        readOnly: true\n      call: consumer-credit-analytics.get-credit-analytics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-small-business-credit-analytics\n      description: Get small business credit analytics\n      hints:\n        readOnly: true\n      call: small-biz-credit-analytics.get-sb-credit-analytics\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mastercard/refs/heads/main/capabilities/open-banking-and-data.yaml
tags:
- Mastercard
- Open Banking
- Data Analytics
- Credit Analytics
- Fintech
tools:
- description: Retrieve consumer accounts via open banking
  hints:
    readOnly: true
  name: get-consumer-accounts
- description: Retrieve account transactions via open banking
  hints:
    readOnly: true
  name: get-account-transactions
- description: Get consumer credit analytics and spending insights
  hints:
    readOnly: true
  name: get-consumer-credit-analytics
- description: Get small business credit analytics
  hints:
    readOnly: true
  name: get-small-business-credit-analytics
---
