---
categories: []
consumed_apis: []
description: Unified capability for fintech developers, financial aggregators, and plan administration platforms to access TIAA retirement account data. Combines the FDX API for customer-consented data sharing and the SIA API for plan administration, enabling a comprehensive view of participant retirement savings, income projections, and account activity.
layout: capability
name: TIAA Retirement Data Access
operations:
- description: List all TIAA retirement accounts
  method: GET
  name: list-accounts
  path: /v1/accounts
- description: Get specific retirement account details
  method: GET
  name: get-account
  path: /v1/accounts/{accountId}
- description: List transactions for a retirement account
  method: GET
  name: list-transactions
  path: /v1/accounts/{accountId}/transactions
- description: List investment positions in a retirement account
  method: GET
  name: list-positions
  path: /v1/accounts/{accountId}/positions
- description: Get customer profile information
  method: GET
  name: get-customer
  path: /v1/customer
- description: List available tax forms
  method: GET
  name: list-tax-forms
  path: /v1/tax-forms
- description: Get SIA plan configuration
  method: GET
  name: get-plan
  path: /v1/plans/{planId}
- description: List plan participants in SIA
  method: GET
  name: list-participants
  path: /v1/plans/{planId}/participants
- description: Get income projection for a participant
  method: GET
  name: get-income-projection
  path: /v1/plans/{planId}/participants/{participantId}/projections
personas: []
provider_name: TIAA
provider_slug: tiaa
search_terms:
- get income projection for a participant
- get customer profile information
- get income projection
- get participant details
- list available tax forms
- list investment positions in a retirement account
- get customer
- customer profile
- list available tiaa tax forms (1099-r, 5498) for a given tax year
- get sia plan configuration
- finance
- retirement
- plan configuration
- insurance
- account transaction history
- list participants
- get plan details
- list plan participants
- investment management
- get details for a specific tiaa account including current balance and status
- get the authenticated customer's tiaa profile and contact information
- get plan
- list plan participants in sia
- list participants enrolled in the secure income account for a plan
- financial data
- get specific retirement account details
- tax documents
- individual account details
- fdx
- list tax forms
- list current investment positions and holdings in a tiaa account
- plan administration
- list positions
- get projected lifetime monthly and annual income for a participant at a given retirement age
- wealth management
- get customer profile
- list transaction history for a tiaa account within a date range
- customer retirement accounts
- lifetime income projections
- list investment positions
- open finance
- get sia account details and balance for a specific plan participant
- list transactions for a retirement account
- get sia plan configuration, eligibility rules, and allocation limits
- list all tiaa retirement accounts
- list accounts
- investment positions and holdings
- plan participants
- get account
- list transactions
- list all tiaa retirement and brokerage accounts for the authenticated customer
- tiaa
- fintech
slug: retirement-data-access
source_filename: retirement-data-access.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: TIAA Retirement Data Access\n  description: Unified capability for fintech developers, financial aggregators, and plan administration platforms to access\n    TIAA retirement account data. Combines the FDX API for customer-consented data sharing and the SIA API for plan administration,\n    enabling a comprehensive view of participant retirement savings, income projections, and account activity.\n  tags:\n  - TIAA\n  - Financial Data\n  - FDX\n  - Open Finance\n  - Plan Administration\n  - Retirement\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TIAA_FDX_ACCESS_TOKEN: TIAA_FDX_ACCESS_TOKEN\n    TIAA_SIA_ACCESS_TOKEN: TIAA_SIA_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: tiaa-fdx\n    baseUri: https://api.tiaa.org/fdx/v6\n    description: TIAA Financial Data Exchange API for account and transaction data\n    authentication:\n      type: bearer\n      token: '{{TIAA_FDX_ACCESS_TOKEN}}'\n\
  \    resources:\n    - name: accounts\n      path: /accounts\n      description: Customer account management\n      operations:\n      - name: list-accounts\n        method: GET\n        description: List all accounts for the authenticated customer\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of accounts to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-account\n        method: GET\n        description: Get details for a specific account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Unique account identifier\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transactions\n      path: /accounts/{accountId}/transactions\n      description: Account transaction history\n      operations:\n      - name: list-transactions\n        method: GET\n        description: List transactions for a specific account within an optional date range\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Unique account identifier\n        - name: startTime\n          in: query\n          type: string\n          required: false\n          description: Start of transaction date range (ISO 8601)\n        - name: endTime\n          in: query\n          type: string\n          required: false\n          description: End of transaction date range (ISO 8601)\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description:\
  \ Maximum number of transactions to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: positions\n      path: /accounts/{accountId}/positions\n      description: Investment positions and holdings\n      operations:\n      - name: list-positions\n        method: GET\n        description: List investment positions for a specific account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Unique account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customer\n      path: /customer\n      description: Customer profile information\n      operations:\n      - name: get-customer\n        method: GET\n        description: Get the authenticated customer's profile\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: tax-forms\n      path: /tax-forms\n      description: Tax document access\n      operations:\n      - name: list-tax-forms\n        method: GET\n        description: List available tax forms for the customer\n        inputParameters:\n        - name: taxYear\n          in: query\n          type: integer\n          required: false\n          description: Filter by tax year\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: tiaa-sia\n    baseUri: https://api.tiaa.org/sia/v1\n    description: TIAA Secure Income Account API for plan administration\n    authentication:\n      type: bearer\n      token: '{{TIAA_SIA_ACCESS_TOKEN}}'\n    resources:\n    - name: plans\n      path: /plans/{planId}\n      description: Plan configuration and eligibility\n      operations:\n      - name: get-plan\n        method:\
  \ GET\n        description: Get SIA configuration for a plan\n        inputParameters:\n        - name: planId\n          in: path\n          type: string\n          required: true\n          description: Unique plan identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: participants\n      path: /plans/{planId}/participants\n      description: Participant enrollment and management\n      operations:\n      - name: list-participants\n        method: GET\n        description: List plan participants enrolled in SIA\n        inputParameters:\n        - name: planId\n          in: path\n          type: string\n          required: true\n          description: Unique plan identifier\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: pageSize\n          in: query\n          type: integer\n          required:\
  \ false\n          description: Page size\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: enroll-participant\n        method: POST\n        description: Enroll a participant in the SIA product\n        inputParameters:\n        - name: planId\n          in: path\n          type: string\n          required: true\n          description: Unique plan identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n            dateOfBirth: '{{tools.dateOfBirth}}'\n            ssn: '{{tools.ssn}}'\n            email: '{{tools.email}}'\n            allocationPercentage: '{{tools.allocationPercentage}}'\n      - name: get-participant\n        method: GET\n        description: Get SIA account\
  \ details for a participant\n        inputParameters:\n        - name: planId\n          in: path\n          type: string\n          required: true\n          description: Unique plan identifier\n        - name: participantId\n          in: path\n          type: string\n          required: true\n          description: Unique participant identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contributions\n      path: /plans/{planId}/contributions\n      description: Contribution submission\n      operations:\n      - name: submit-contribution\n        method: POST\n        description: Submit a contribution to a participant's SIA account\n        inputParameters:\n        - name: planId\n          in: path\n          type: string\n          required: true\n          description: Unique plan identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n       \
  \   type: object\n          value: $.\n        body:\n          type: json\n          data:\n            participantId: '{{tools.participantId}}'\n            amount: '{{tools.amount}}'\n            contributionType: '{{tools.contributionType}}'\n            payrollDate: '{{tools.payrollDate}}'\n    - name: projections\n      path: /plans/{planId}/participants/{participantId}/projections\n      description: Income projections\n      operations:\n      - name: get-income-projection\n        method: GET\n        description: Get projected lifetime income for a participant\n        inputParameters:\n        - name: planId\n          in: path\n          type: string\n          required: true\n          description: Unique plan identifier\n        - name: participantId\n          in: path\n          type: string\n          required: true\n          description: Unique participant identifier\n        - name: retirementAge\n          in: query\n          type: integer\n          required: false\n\
  \          description: Target retirement age\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: tiaa-retirement-api\n    description: Unified REST API for accessing TIAA retirement account data, plan administration, and income projections.\n    resources:\n    - path: /v1/accounts\n      name: accounts\n      description: Customer retirement accounts\n      operations:\n      - method: GET\n        name: list-accounts\n        description: List all TIAA retirement accounts\n        call: tiaa-fdx.list-accounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{accountId}\n      name: account-detail\n      description: Individual account details\n      operations:\n      - method: GET\n        name: get-account\n        description: Get specific retirement account details\n        call: tiaa-fdx.get-account\n\
  \        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{accountId}/transactions\n      name: transactions\n      description: Account transaction history\n      operations:\n      - method: GET\n        name: list-transactions\n        description: List transactions for a retirement account\n        call: tiaa-fdx.list-transactions\n        with:\n          accountId: rest.accountId\n          startTime: rest.startTime\n          endTime: rest.endTime\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts/{accountId}/positions\n      name: investment-positions\n      description: Investment positions and holdings\n      operations:\n      - method: GET\n        name: list-positions\n        description: List investment positions in a retirement account\n        call: tiaa-fdx.list-positions\n        with:\n          accountId: rest.accountId\n  \
  \      outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/customer\n      name: customer\n      description: Customer profile\n      operations:\n      - method: GET\n        name: get-customer\n        description: Get customer profile information\n        call: tiaa-fdx.get-customer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tax-forms\n      name: tax-forms\n      description: Tax documents\n      operations:\n      - method: GET\n        name: list-tax-forms\n        description: List available tax forms\n        call: tiaa-fdx.list-tax-forms\n        with:\n          taxYear: rest.taxYear\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/plans/{planId}\n      name: plan\n      description: Plan configuration\n      operations:\n      - method: GET\n        name: get-plan\n        description: Get SIA plan configuration\n        call: tiaa-sia.get-plan\n        with:\n\
  \          planId: rest.planId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/plans/{planId}/participants\n      name: participants\n      description: Plan participants\n      operations:\n      - method: GET\n        name: list-participants\n        description: List plan participants in SIA\n        call: tiaa-sia.list-participants\n        with:\n          planId: rest.planId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/plans/{planId}/participants/{participantId}/projections\n      name: income-projections\n      description: Lifetime income projections\n      operations:\n      - method: GET\n        name: get-income-projection\n        description: Get income projection for a participant\n        call: tiaa-sia.get-income-projection\n        with:\n          planId: rest.planId\n          participantId: rest.participantId\n          retirementAge: rest.retirementAge\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: tiaa-retirement-mcp\n    transport: http\n    description: MCP server for AI-assisted TIAA retirement account data access, plan administration, and income planning.\n    tools:\n    - name: list-accounts\n      description: List all TIAA retirement and brokerage accounts for the authenticated customer\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tiaa-fdx.list-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account\n      description: Get details for a specific TIAA account including current balance and status\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tiaa-fdx.get-account\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-transactions\n      description: List transaction history for a TIAA account within\
  \ a date range\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tiaa-fdx.list-transactions\n      with:\n        accountId: tools.accountId\n        startTime: tools.startTime\n        endTime: tools.endTime\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-investment-positions\n      description: List current investment positions and holdings in a TIAA account\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tiaa-fdx.list-positions\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-customer-profile\n      description: Get the authenticated customer's TIAA profile and contact information\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tiaa-fdx.get-customer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tax-forms\n      description: List available\
  \ TIAA tax forms (1099-R, 5498) for a given tax year\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tiaa-fdx.list-tax-forms\n      with:\n        taxYear: tools.taxYear\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-plan-details\n      description: Get SIA plan configuration, eligibility rules, and allocation limits\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tiaa-sia.get-plan\n      with:\n        planId: tools.planId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-plan-participants\n      description: List participants enrolled in the Secure Income Account for a plan\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tiaa-sia.list-participants\n      with:\n        planId: tools.planId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-participant-details\n      description: Get SIA account\
  \ details and balance for a specific plan participant\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tiaa-sia.get-participant\n      with:\n        planId: tools.planId\n        participantId: tools.participantId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-income-projection\n      description: Get projected lifetime monthly and annual income for a participant at a given retirement age\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tiaa-sia.get-income-projection\n      with:\n        planId: tools.planId\n        participantId: tools.participantId\n        retirementAge: tools.retirementAge\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tiaa/refs/heads/main/capabilities/retirement-data-access.yaml
tags:
- TIAA
- Financial Data
- FDX
- Open Finance
- Plan Administration
- Retirement
tools:
- description: List all TIAA retirement and brokerage accounts for the authenticated customer
  hints:
    openWorld: false
    readOnly: true
  name: list-accounts
- description: Get details for a specific TIAA account including current balance and status
  hints:
    openWorld: false
    readOnly: true
  name: get-account
- description: List transaction history for a TIAA account within a date range
  hints:
    openWorld: false
    readOnly: true
  name: list-transactions
- description: List current investment positions and holdings in a TIAA account
  hints:
    openWorld: false
    readOnly: true
  name: list-investment-positions
- description: Get the authenticated customer's TIAA profile and contact information
  hints:
    openWorld: false
    readOnly: true
  name: get-customer-profile
- description: List available TIAA tax forms (1099-R, 5498) for a given tax year
  hints:
    openWorld: false
    readOnly: true
  name: list-tax-forms
- description: Get SIA plan configuration, eligibility rules, and allocation limits
  hints:
    openWorld: false
    readOnly: true
  name: get-plan-details
- description: List participants enrolled in the Secure Income Account for a plan
  hints:
    openWorld: false
    readOnly: true
  name: list-plan-participants
- description: Get SIA account details and balance for a specific plan participant
  hints:
    openWorld: false
    readOnly: true
  name: get-participant-details
- description: Get projected lifetime monthly and annual income for a participant at a given retirement age
  hints:
    openWorld: false
    readOnly: true
  name: get-income-projection
---
