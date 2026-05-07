---
categories: []
consumed_apis: []
description: Majesco cloud-based insurance platform API for policy administration, claims management, billing, and distribution. Supports P&C, L&A, and specialty lines with REST interfaces for digital insurance operations.
layout: capability
name: Majesco Insurance Policy Administration API
operations:
- description: List policies
  method: GET
  name: listpolicies
  path: /policies
- description: Create a new policy
  method: POST
  name: createpolicy
  path: /policies
- description: Get a policy by policy number
  method: GET
  name: getpolicy
  path: /policies/{policyNumber}
- description: Update (endorse) a policy
  method: PATCH
  name: updatepolicy
  path: /policies/{policyNumber}
- description: Cancel a policy
  method: POST
  name: cancelpolicy
  path: /policies/{policyNumber}/cancel
- description: Renew a policy
  method: POST
  name: renewpolicy
  path: /policies/{policyNumber}/renew
- description: List claims
  method: GET
  name: listclaims
  path: /claims
- description: Create a new claim
  method: POST
  name: createclaim
  path: /claims
- description: Get claim details
  method: GET
  name: getclaim
  path: /claims/{claimNumber}
- description: List billing accounts
  method: GET
  name: listbillingaccounts
  path: /billing/accounts
- description: Record a payment
  method: POST
  name: recordpayment
  path: /billing/accounts/{accountId}/payments
- description: Generate an insurance quote
  method: POST
  name: createquote
  path: /quotes
personas: []
provider_name: majesco
provider_slug: majesco
search_terms:
- listpolicies
- createclaim
- list billing accounts
- list claims
- cancelpolicy
- renewpolicy
- update (endorse) a policy
- api
- getpolicy
- updatepolicy
- recordpayment
- generate an insurance quote
- get claim details
- getclaim
- get a policy by policy number
- create a new policy
- createquote
- createpolicy
- list policies
- create a new claim
- cancel a policy
- majesco
- listbillingaccounts
- record a payment
- listclaims
- renew a policy
slug: majesco-capability
source_filename: majesco-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Majesco Insurance Policy Administration API\n  description: Majesco cloud-based insurance platform API for policy administration, claims management, billing, and distribution.\n    Supports P&C, L&A, and specialty lines with REST interfaces for digital insurance operations.\n  tags:\n  - Majesco\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: majesco\n    baseUri: https://api.majesco.example.com/v1\n    description: Majesco Insurance Policy Administration API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{MAJESCO_TOKEN}}'\n    resources:\n    - name: policies\n      path: /policies\n      operations:\n      - name: listpolicies\n        method: GET\n        description: List policies\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Filter by policy status\n        - name: productType\n\
  \          in: query\n          type: string\n          description: Filter by insurance product type\n        - name: policyholderName\n          in: query\n          type: string\n        - name: effectiveDateFrom\n          in: query\n          type: string\n        - name: effectiveDateTo\n          in: query\n          type: string\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createpolicy\n        method: POST\n        description: Create a new policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: policies-policynumber\n      path: /policies/{policyNumber}\n      operations:\n      - name: getpolicy\n        method: GET\n        description: Get a policy\
  \ by policy number\n        inputParameters:\n        - name: policyNumber\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatepolicy\n        method: PATCH\n        description: Update (endorse) a policy\n        inputParameters:\n        - name: policyNumber\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: policies-policynumber-cancel\n      path: /policies/{policyNumber}/cancel\n      operations:\n      - name: cancelpolicy\n        method: POST\n        description: Cancel a policy\n        inputParameters:\n        - name: policyNumber\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: policies-policynumber-renew\n      path: /policies/{policyNumber}/renew\n      operations:\n      - name: renewpolicy\n        method: POST\n        description: Renew a policy\n        inputParameters:\n        - name: policyNumber\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: claims\n      path: /claims\n      operations:\n      - name: listclaims\n        method: GET\n        description: List claims\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n        - name: policyNumber\n          in: query\n          type: string\n        - name: claimDateFrom\n          in: query\n          type: string\n        - name: pageSize\n          in: query\n          type: integer\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createclaim\n        method: POST\n        description: Create a new claim\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: claims-claimnumber\n      path: /claims/{claimNumber}\n      operations:\n      - name: getclaim\n        method: GET\n        description: Get claim details\n        inputParameters:\n        - name: claimNumber\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: billing-accounts\n      path: /billing/accounts\n      operations:\n      - name: listbillingaccounts\n        method: GET\n        description: List billing accounts\n        inputParameters:\n        - name: policyNumber\n          in: query\n     \
  \     type: string\n        - name: pageSize\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: billing-accounts-accountid-payments\n      path: /billing/accounts/{accountId}/payments\n      operations:\n      - name: recordpayment\n        method: POST\n        description: Record a payment\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: quotes\n      path: /quotes\n      operations:\n      - name: createquote\n        method: POST\n        description: Generate an insurance quote\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port:\
  \ 8080\n    namespace: majesco-rest\n    description: REST adapter for Majesco Insurance Policy Administration API.\n    resources:\n    - path: /policies\n      name: listpolicies\n      operations:\n      - method: GET\n        name: listpolicies\n        description: List policies\n        call: majesco.listpolicies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /policies\n      name: createpolicy\n      operations:\n      - method: POST\n        name: createpolicy\n        description: Create a new policy\n        call: majesco.createpolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /policies/{policyNumber}\n      name: getpolicy\n      operations:\n      - method: GET\n        name: getpolicy\n        description: Get a policy by policy number\n        call: majesco.getpolicy\n        with:\n          policyNumber: rest.policyNumber\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /policies/{policyNumber}\n      name: updatepolicy\n      operations:\n      - method: PATCH\n        name: updatepolicy\n        description: Update (endorse) a policy\n        call: majesco.updatepolicy\n        with:\n          policyNumber: rest.policyNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /policies/{policyNumber}/cancel\n      name: cancelpolicy\n      operations:\n      - method: POST\n        name: cancelpolicy\n        description: Cancel a policy\n        call: majesco.cancelpolicy\n        with:\n          policyNumber: rest.policyNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /policies/{policyNumber}/renew\n      name: renewpolicy\n      operations:\n      - method: POST\n        name: renewpolicy\n        description: Renew a policy\n        call: majesco.renewpolicy\n        with:\n          policyNumber: rest.policyNumber\n        outputParameters:\n   \
  \     - type: object\n          mapping: $.\n    - path: /claims\n      name: listclaims\n      operations:\n      - method: GET\n        name: listclaims\n        description: List claims\n        call: majesco.listclaims\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /claims\n      name: createclaim\n      operations:\n      - method: POST\n        name: createclaim\n        description: Create a new claim\n        call: majesco.createclaim\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /claims/{claimNumber}\n      name: getclaim\n      operations:\n      - method: GET\n        name: getclaim\n        description: Get claim details\n        call: majesco.getclaim\n        with:\n          claimNumber: rest.claimNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /billing/accounts\n      name: listbillingaccounts\n      operations:\n      - method: GET\n        name:\
  \ listbillingaccounts\n        description: List billing accounts\n        call: majesco.listbillingaccounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /billing/accounts/{accountId}/payments\n      name: recordpayment\n      operations:\n      - method: POST\n        name: recordpayment\n        description: Record a payment\n        call: majesco.recordpayment\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /quotes\n      name: createquote\n      operations:\n      - method: POST\n        name: createquote\n        description: Generate an insurance quote\n        call: majesco.createquote\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: majesco-mcp\n    transport: http\n    description: MCP adapter for Majesco Insurance Policy Administration API for AI agent use.\n    tools:\n   \
  \ - name: listpolicies\n      description: List policies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: majesco.listpolicies\n      with:\n        status: tools.status\n        productType: tools.productType\n        policyholderName: tools.policyholderName\n        effectiveDateFrom: tools.effectiveDateFrom\n        effectiveDateTo: tools.effectiveDateTo\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: status\n        type: string\n        description: Filter by policy status\n      - name: productType\n        type: string\n        description: Filter by insurance product type\n      - name: policyholderName\n        type: string\n        description: policyholderName\n      - name: effectiveDateFrom\n        type: string\n        description: effectiveDateFrom\n      - name: effectiveDateTo\n        type: string\n        description: effectiveDateTo\n      - name: pageSize\n\
  \        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createpolicy\n      description: Create a new policy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: majesco.createpolicy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpolicy\n      description: Get a policy by policy number\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: majesco.getpolicy\n      with:\n        policyNumber: tools.policyNumber\n      inputParameters:\n      - name: policyNumber\n        type: string\n        description: policyNumber\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatepolicy\n      description: Update (endorse) a policy\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: false\n      call: majesco.updatepolicy\n      with:\n        policyNumber: tools.policyNumber\n      inputParameters:\n      - name: policyNumber\n        type: string\n        description: policyNumber\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancelpolicy\n      description: Cancel a policy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: majesco.cancelpolicy\n      with:\n        policyNumber: tools.policyNumber\n      inputParameters:\n      - name: policyNumber\n        type: string\n        description: policyNumber\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: renewpolicy\n      description: Renew a policy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: majesco.renewpolicy\n\
  \      with:\n        policyNumber: tools.policyNumber\n      inputParameters:\n      - name: policyNumber\n        type: string\n        description: policyNumber\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listclaims\n      description: List claims\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: majesco.listclaims\n      with:\n        status: tools.status\n        policyNumber: tools.policyNumber\n        claimDateFrom: tools.claimDateFrom\n        pageSize: tools.pageSize\n      inputParameters:\n      - name: status\n        type: string\n        description: status\n      - name: policyNumber\n        type: string\n        description: policyNumber\n      - name: claimDateFrom\n        type: string\n        description: claimDateFrom\n      - name: pageSize\n        type: integer\n        description: pageSize\n      outputParameters:\n      - type: object\n     \
  \   mapping: $.\n    - name: createclaim\n      description: Create a new claim\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: majesco.createclaim\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getclaim\n      description: Get claim details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: majesco.getclaim\n      with:\n        claimNumber: tools.claimNumber\n      inputParameters:\n      - name: claimNumber\n        type: string\n        description: claimNumber\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listbillingaccounts\n      description: List billing accounts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: majesco.listbillingaccounts\n      with:\n        policyNumber: tools.policyNumber\n        pageSize: tools.pageSize\n\
  \      inputParameters:\n      - name: policyNumber\n        type: string\n        description: policyNumber\n      - name: pageSize\n        type: integer\n        description: pageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: recordpayment\n      description: Record a payment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: majesco.recordpayment\n      with:\n        accountId: tools.accountId\n      inputParameters:\n      - name: accountId\n        type: string\n        description: accountId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createquote\n      description: Generate an insurance quote\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: majesco.createquote\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n   \
  \ MAJESCO_TOKEN: MAJESCO_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/majesco/refs/heads/main/capabilities/majesco-capability.yaml
tags:
- Majesco
- API
tools:
- description: List policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpolicies
- description: Create a new policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpolicy
- description: Get a policy by policy number
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpolicy
- description: Update (endorse) a policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatepolicy
- description: Cancel a policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: cancelpolicy
- description: Renew a policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: renewpolicy
- description: List claims
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listclaims
- description: Create a new claim
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createclaim
- description: Get claim details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclaim
- description: List billing accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbillingaccounts
- description: Record a payment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: recordpayment
- description: Generate an insurance quote
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createquote
---
