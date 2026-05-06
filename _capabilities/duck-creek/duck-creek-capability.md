---
categories: []
consumed_apis: []
description: Duck Creek Policy Administration API enables product configuration, premium calculation, policy lifecycle management, and policy issuance for P&C and specialty insurance carriers. Duck Creek Anywhere provides 2,600+ RESTful APIs across all Duck Creek applications using open standards. Supports end-to-end policy management from quoting through renewal.
layout: capability
name: Duck Creek Policy Administration API
operations:
- description: List insurance policies
  method: GET
  name: listpolicies
  path: /policies
- description: Create a new policy
  method: POST
  name: createpolicy
  path: /policies
- description: Get policy details
  method: GET
  name: getpolicy
  path: /policies/{policyId}
- description: Update policy (endorsement)
  method: PUT
  name: updatepolicy
  path: /policies/{policyId}
- description: Cancel a policy
  method: POST
  name: cancelpolicy
  path: /policies/{policyId}/cancel
- description: Renew a policy
  method: POST
  name: renewpolicy
  path: /policies/{policyId}/renew
- description: Create a policy quote
  method: POST
  name: createquote
  path: /quotes
- description: List claims
  method: GET
  name: listclaims
  path: /claims
- description: Report a new claim
  method: POST
  name: createclaim
  path: /claims
- description: Get claim details
  method: GET
  name: getclaim
  path: /claims/{claimId}
- description: List billing accounts
  method: GET
  name: listbillingaccounts
  path: /billing/accounts
- description: List invoices for a billing account
  method: GET
  name: listinvoices
  path: /billing/accounts/{accountId}/invoices
- description: List insurance products
  method: GET
  name: listproducts
  path: /products
personas: []
provider_name: duck-creek
provider_slug: duck-creek
search_terms:
- createpolicy
- cancelpolicy
- creek
- list invoices for a billing account
- listclaims
- report a new claim
- get policy details
- listpolicies
- create a new policy
- createquote
- updatepolicy
- list claims
- getpolicy
- listproducts
- list insurance policies
- create a policy quote
- duck
- api
- renewpolicy
- cancel a policy
- list billing accounts
- createclaim
- update policy (endorsement)
- listinvoices
- listbillingaccounts
- list insurance products
- renew a policy
- getclaim
- get claim details
slug: duck-creek-capability
source_filename: duck-creek-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Duck Creek Policy Administration API\n  description: Duck Creek Policy Administration API enables product configuration, premium calculation, policy lifecycle management,\n    and policy issuance for P&C and specialty insurance carriers. Duck Creek Anywhere provides 2,600+ RESTful APIs across\n    all Duck Creek applications using open standards. Supports end-to-end policy management from quoting through renewal.\n  tags:\n  - Duck\n  - Creek\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: duck-creek\n    baseUri: https://api.duckcreek.com/v1\n    description: Duck Creek Policy Administration API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{DUCK_CREEK_TOKEN}}'\n    resources:\n    - name: policies\n      path: /policies\n      operations:\n      - name: listpolicies\n        method: GET\n        description: List insurance policies\n        inputParameters:\n\
  \        - name: status\n          in: query\n          type: string\n          description: Filter by policy status\n        - name: productCode\n          in: query\n          type: string\n          description: Filter by insurance product code\n        - name: effectiveAfter\n          in: query\n          type: string\n          description: Filter policies effective on or after this date (ISO 8601)\n        - name: effectiveBefore\n          in: query\n          type: string\n          description: Filter policies effective on or before this date\n        - name: insuredName\n          in: query\n          type: string\n          description: Filter by insured name (partial match)\n        - name: limit\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createpolicy\n        method:\
  \ POST\n        description: Create a new policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: policies-policyid\n      path: /policies/{policyId}\n      operations:\n      - name: getpolicy\n        method: GET\n        description: Get policy details\n        inputParameters:\n        - name: policyId\n          in: path\n          type: string\n          required: true\n          description: Unique policy identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatepolicy\n        method: PUT\n        description: Update policy (endorsement)\n        inputParameters:\n        - name: policyId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    -\
  \ name: policies-policyid-cancel\n      path: /policies/{policyId}/cancel\n      operations:\n      - name: cancelpolicy\n        method: POST\n        description: Cancel a policy\n        inputParameters:\n        - name: policyId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: policies-policyid-renew\n      path: /policies/{policyId}/renew\n      operations:\n      - name: renewpolicy\n        method: POST\n        description: Renew a policy\n        inputParameters:\n        - name: policyId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: quotes\n      path: /quotes\n      operations:\n      - name: createquote\n        method: POST\n        description: Create a\
  \ policy quote\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: claims\n      path: /claims\n      operations:\n      - name: listclaims\n        method: GET\n        description: List claims\n        inputParameters:\n        - name: policyId\n          in: query\n          type: string\n          description: Filter claims for a specific policy\n        - name: claimStatus\n          in: query\n          type: string\n        - name: lossDateAfter\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createclaim\n        method: POST\n        description: Report a new claim\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: claims-claimid\n      path: /claims/{claimId}\n      operations:\n      - name: getclaim\n        method: GET\n        description: Get claim details\n        inputParameters:\n        - name: claimId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: billing-accounts\n      path: /billing/accounts\n      operations:\n      - name: listbillingaccounts\n        method: GET\n        description: List billing accounts\n        inputParameters:\n        - name: policyId\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: billing-accounts-accountid-invoices\n      path: /billing/accounts/{accountId}/invoices\n      operations:\n\
  \      - name: listinvoices\n        method: GET\n        description: List invoices for a billing account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n        - name: status\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: products\n      path: /products\n      operations:\n      - name: listproducts\n        method: GET\n        description: List insurance products\n        inputParameters:\n        - name: lineOfBusiness\n          in: query\n          type: string\n          description: Filter by line of business\n        - name: state\n          in: query\n          type: string\n          description: Filter products available in a specific US state (2-letter code)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: duck-creek-rest\n    description: REST adapter for Duck Creek Policy Administration API.\n    resources:\n    - path: /policies\n      name: listpolicies\n      operations:\n      - method: GET\n        name: listpolicies\n        description: List insurance policies\n        call: duck-creek.listpolicies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /policies\n      name: createpolicy\n      operations:\n      - method: POST\n        name: createpolicy\n        description: Create a new policy\n        call: duck-creek.createpolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /policies/{policyId}\n      name: getpolicy\n      operations:\n      - method: GET\n        name: getpolicy\n        description: Get policy details\n        call: duck-creek.getpolicy\n        with:\n          policyId: rest.policyId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /policies/{policyId}\n      name: updatepolicy\n      operations:\n      - method: PUT\n        name: updatepolicy\n        description: Update policy (endorsement)\n        call: duck-creek.updatepolicy\n        with:\n          policyId: rest.policyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /policies/{policyId}/cancel\n      name: cancelpolicy\n      operations:\n      - method: POST\n        name: cancelpolicy\n        description: Cancel a policy\n        call: duck-creek.cancelpolicy\n        with:\n          policyId: rest.policyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /policies/{policyId}/renew\n      name: renewpolicy\n      operations:\n      - method: POST\n        name: renewpolicy\n        description: Renew a policy\n        call: duck-creek.renewpolicy\n        with:\n          policyId: rest.policyId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /quotes\n      name: createquote\n      operations:\n      - method: POST\n        name: createquote\n        description: Create a policy quote\n        call: duck-creek.createquote\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /claims\n      name: listclaims\n      operations:\n      - method: GET\n        name: listclaims\n        description: List claims\n        call: duck-creek.listclaims\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /claims\n      name: createclaim\n      operations:\n      - method: POST\n        name: createclaim\n        description: Report a new claim\n        call: duck-creek.createclaim\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /claims/{claimId}\n      name: getclaim\n      operations:\n      - method: GET\n        name: getclaim\n        description: Get claim details\n \
  \       call: duck-creek.getclaim\n        with:\n          claimId: rest.claimId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /billing/accounts\n      name: listbillingaccounts\n      operations:\n      - method: GET\n        name: listbillingaccounts\n        description: List billing accounts\n        call: duck-creek.listbillingaccounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /billing/accounts/{accountId}/invoices\n      name: listinvoices\n      operations:\n      - method: GET\n        name: listinvoices\n        description: List invoices for a billing account\n        call: duck-creek.listinvoices\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /products\n      name: listproducts\n      operations:\n      - method: GET\n        name: listproducts\n        description: List insurance products\n       \
  \ call: duck-creek.listproducts\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: duck-creek-mcp\n    transport: http\n    description: MCP adapter for Duck Creek Policy Administration API for AI agent use.\n    tools:\n    - name: listpolicies\n      description: List insurance policies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: duck-creek.listpolicies\n      with:\n        status: tools.status\n        productCode: tools.productCode\n        effectiveAfter: tools.effectiveAfter\n        effectiveBefore: tools.effectiveBefore\n        insuredName: tools.insuredName\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: status\n        type: string\n        description: Filter by policy status\n      - name: productCode\n        type: string\n        description: Filter by insurance product code\n      - name: effectiveAfter\n\
  \        type: string\n        description: Filter policies effective on or after this date (ISO 8601)\n      - name: effectiveBefore\n        type: string\n        description: Filter policies effective on or before this date\n      - name: insuredName\n        type: string\n        description: Filter by insured name (partial match)\n      - name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createpolicy\n      description: Create a new policy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: duck-creek.createpolicy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpolicy\n      description: Get policy details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: duck-creek.getpolicy\n\
  \      with:\n        policyId: tools.policyId\n      inputParameters:\n      - name: policyId\n        type: string\n        description: Unique policy identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatepolicy\n      description: Update policy (endorsement)\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: duck-creek.updatepolicy\n      with:\n        policyId: tools.policyId\n      inputParameters:\n      - name: policyId\n        type: string\n        description: policyId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancelpolicy\n      description: Cancel a policy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: duck-creek.cancelpolicy\n      with:\n        policyId: tools.policyId\n      inputParameters:\n      - name: policyId\n        type:\
  \ string\n        description: policyId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: renewpolicy\n      description: Renew a policy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: duck-creek.renewpolicy\n      with:\n        policyId: tools.policyId\n      inputParameters:\n      - name: policyId\n        type: string\n        description: policyId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createquote\n      description: Create a policy quote\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: duck-creek.createquote\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listclaims\n      description: List claims\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: duck-creek.listclaims\n\
  \      with:\n        policyId: tools.policyId\n        claimStatus: tools.claimStatus\n        lossDateAfter: tools.lossDateAfter\n        limit: tools.limit\n      inputParameters:\n      - name: policyId\n        type: string\n        description: Filter claims for a specific policy\n      - name: claimStatus\n        type: string\n        description: claimStatus\n      - name: lossDateAfter\n        type: string\n        description: lossDateAfter\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createclaim\n      description: Report a new claim\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: duck-creek.createclaim\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getclaim\n      description: Get claim details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: duck-creek.getclaim\n      with:\n        claimId: tools.claimId\n      inputParameters:\n      - name: claimId\n        type: string\n        description: claimId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listbillingaccounts\n      description: List billing accounts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: duck-creek.listbillingaccounts\n      with:\n        policyId: tools.policyId\n        limit: tools.limit\n      inputParameters:\n      - name: policyId\n        type: string\n        description: policyId\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listinvoices\n      description: List invoices for a billing account\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: duck-creek.listinvoices\n\
  \      with:\n        accountId: tools.accountId\n        status: tools.status\n      inputParameters:\n      - name: accountId\n        type: string\n        description: accountId\n        required: true\n      - name: status\n        type: string\n        description: status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listproducts\n      description: List insurance products\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: duck-creek.listproducts\n      with:\n        lineOfBusiness: tools.lineOfBusiness\n        state: tools.state\n      inputParameters:\n      - name: lineOfBusiness\n        type: string\n        description: Filter by line of business\n      - name: state\n        type: string\n        description: Filter products available in a specific US state (2-letter code)\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    DUCK_CREEK_TOKEN:\
  \ DUCK_CREEK_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/duck-creek/refs/heads/main/capabilities/duck-creek-capability.yaml
tags:
- Duck
- Creek
- API
tools:
- description: List insurance policies
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
- description: Get policy details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpolicy
- description: Update policy (endorsement)
  hints:
    destructive: false
    idempotent: true
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
- description: Create a policy quote
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createquote
- description: List claims
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listclaims
- description: Report a new claim
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
- description: List invoices for a billing account
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinvoices
- description: List insurance products
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listproducts
---
