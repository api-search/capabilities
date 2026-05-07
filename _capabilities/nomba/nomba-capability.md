---
categories: []
consumed_apis: []
description: The Nomba Accounts API enables developers to manage business accounts on the Nomba platform. It provides endpoints for retrieving account details, fetching the parent account balance, and listing terminals assigned to an account. This API serves as the foundation for account management operations within the Nomba ecosystem.
layout: capability
name: Nomba Accounts API
operations:
- description: Fetch parent account details
  method: GET
  name: fetchparentaccountdetails
  path: /v1/accounts
- description: Fetch parent account balance
  method: GET
  name: fetchparentaccountbalance
  path: /v1/accounts/balance
- description: Fetch terminals assigned to an account
  method: GET
  name: fetchterminalsassignedtoaccount
  path: /v1/accounts/{accountId}/terminals
personas: []
provider_name: Nomba
provider_slug: nomba
search_terms:
- fetchparentaccountbalance
- fetch parent account balance
- banking
- cross-border payments
- payments
- fetchterminalsassignedtoaccount
- cards
- fetch terminals assigned to an account
- fintech
- virtual accounts
- fetch parent account details
- nomba
- api
- checkout
- fetchparentaccountdetails
- transfers
slug: nomba-capability
source_filename: nomba-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Nomba Accounts API\n  description: The Nomba Accounts API enables developers to manage business accounts on the Nomba platform. It provides endpoints\n    for retrieving account details, fetching the parent account balance, and listing terminals assigned to an account. This\n    API serves as the foundation for account management operations within the Nomba ecosystem.\n  tags:\n  - Nomba\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: nomba\n    baseUri: https://api.nomba.com\n    description: Nomba Accounts API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{NOMBA_TOKEN}}'\n    resources:\n    - name: v1-accounts\n      path: /v1/accounts\n      operations:\n      - name: fetchparentaccountdetails\n        method: GET\n        description: Fetch parent account details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: v1-accounts-balance\n      path: /v1/accounts/balance\n      operations:\n      - name: fetchparentaccountbalance\n        method: GET\n        description: Fetch parent account balance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-accounts-accountid-terminals\n      path: /v1/accounts/{accountId}/terminals\n      operations:\n      - name: fetchterminalsassignedtoaccount\n        method: GET\n        description: Fetch terminals assigned to an account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: nomba-rest\n    description: REST adapter for Nomba Accounts API.\n    resources:\n    - path: /v1/accounts\n      name: fetchparentaccountdetails\n      operations:\n      - method: GET\n        name:\
  \ fetchparentaccountdetails\n        description: Fetch parent account details\n        call: nomba.fetchparentaccountdetails\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/balance\n      name: fetchparentaccountbalance\n      operations:\n      - method: GET\n        name: fetchparentaccountbalance\n        description: Fetch parent account balance\n        call: nomba.fetchparentaccountbalance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{accountId}/terminals\n      name: fetchterminalsassignedtoaccount\n      operations:\n      - method: GET\n        name: fetchterminalsassignedtoaccount\n        description: Fetch terminals assigned to an account\n        call: nomba.fetchterminalsassignedtoaccount\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: nomba-mcp\n    transport: http\n    description: MCP adapter\
  \ for Nomba Accounts API for AI agent use.\n    tools:\n    - name: fetchparentaccountdetails\n      description: Fetch parent account details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nomba.fetchparentaccountdetails\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: fetchparentaccountbalance\n      description: Fetch parent account balance\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nomba.fetchparentaccountbalance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: fetchterminalsassignedtoaccount\n      description: Fetch terminals assigned to an account\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nomba.fetchterminalsassignedtoaccount\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    NOMBA_TOKEN:\
  \ NOMBA_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/nomba/refs/heads/main/capabilities/nomba-capability.yaml
tags:
- Nomba
- API
tools:
- description: Fetch parent account details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: fetchparentaccountdetails
- description: Fetch parent account balance
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: fetchparentaccountbalance
- description: Fetch terminals assigned to an account
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: fetchterminalsassignedtoaccount
---
