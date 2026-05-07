---
categories: []
consumed_apis: []
description: Prudential Financial provides APIs for accessing insurance and financial services data, including retirement accounts, annuities, and financial product information.
layout: capability
name: Prudential Financial Developer API
operations:
- description: Get Accounts
  method: GET
  name: getaccounts
  path: /accounts
- description: Get Account by ID
  method: GET
  name: getaccountbyid
  path: /accounts/{accountId}
- description: Get Retirement Plans
  method: GET
  name: getretirementplans
  path: /retirement/plans
personas: []
provider_name: Prudential Financial
provider_slug: prudential-financial
search_terms:
- financial
- prudential
- financial services
- get accounts
- getaccounts
- annuities
- getaccountbyid
- get account by id
- get retirement plans
- insurance
- api
- retirement
- getretirementplans
slug: prudential-financial-capability
source_filename: prudential-financial-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Prudential Financial Developer API\n  description: Prudential Financial provides APIs for accessing insurance and financial services data, including retirement\n    accounts, annuities, and financial product information.\n  tags:\n  - Prudential\n  - Financial\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: prudential-financial\n    baseUri: https://developer.apis.prudential.com\n    description: Prudential Financial Developer API HTTP API.\n    resources:\n    - name: accounts\n      path: /accounts\n      operations:\n      - name: getaccounts\n        method: GET\n        description: Get Accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid\n      path: /accounts/{accountId}\n      operations:\n      - name: getaccountbyid\n        method: GET\n     \
  \   description: Get Account by ID\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: retirement-plans\n      path: /retirement/plans\n      operations:\n      - name: getretirementplans\n        method: GET\n        description: Get Retirement Plans\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: prudential-financial-rest\n    description: REST adapter for Prudential Financial Developer API.\n    resources:\n    - path: /accounts\n      name: getaccounts\n      operations:\n      - method: GET\n        name: getaccounts\n        description: Get Accounts\n        call: prudential-financial.getaccounts\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /accounts/{accountId}\n      name: getaccountbyid\n      operations:\n      - method: GET\n        name: getaccountbyid\n        description: Get Account by ID\n        call: prudential-financial.getaccountbyid\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /retirement/plans\n      name: getretirementplans\n      operations:\n      - method: GET\n        name: getretirementplans\n        description: Get Retirement Plans\n        call: prudential-financial.getretirementplans\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: prudential-financial-mcp\n    transport: http\n    description: MCP adapter for Prudential Financial Developer API for AI agent use.\n    tools:\n    - name: getaccounts\n      description: Get Accounts\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: prudential-financial.getaccounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getaccountbyid\n      description: Get Account by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: prudential-financial.getaccountbyid\n      with:\n        accountId: tools.accountId\n      inputParameters:\n      - name: accountId\n        type: string\n        description: accountId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getretirementplans\n      description: Get Retirement Plans\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: prudential-financial.getretirementplans\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/prudential-financial/refs/heads/main/capabilities/prudential-financial-capability.yaml
tags:
- Prudential
- Financial
- API
tools:
- description: Get Accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccounts
- description: Get Account by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccountbyid
- description: Get Retirement Plans
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getretirementplans
---
