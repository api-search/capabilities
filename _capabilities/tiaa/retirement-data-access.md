---
api_specs:
- filename: tiaa-fdx-openapi.yml
  format: yaml
  label: tiaa-fdx
  slug: tiaa-fdx
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/tiaa/refs/heads/main/openapi/tiaa-fdx-openapi.yml
- filename: tiaa-sia-openapi.yml
  format: yaml
  label: tiaa-sia
  slug: tiaa-sia
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/tiaa/refs/heads/main/openapi/tiaa-sia-openapi.yml
categories: []
consumed_apis:
- tiaa-fdx
- tiaa-sia
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
- get details for a specific tiaa account including current balance and status
- get income projection
- list tax forms
- list available tax forms
- get participant details
- list plan participants
- get plan details
- get account
- get sia plan configuration
- list accounts
- list available tiaa tax forms (1099-r, 5498) for a given tax year
- fintech
- list positions
- tiaa
- get the authenticated customer's tiaa profile and contact information
- account transaction history
- customer profile
- retirement
- get sia account details and balance for a specific plan participant
- finance
- get projected lifetime monthly and annual income for a participant at a given retirement age
- financial data
- investment positions and holdings
- list investment positions
- lifetime income projections
- wealth management
- list all tiaa retirement and brokerage accounts for the authenticated customer
- open finance
- list plan participants in sia
- plan administration
- get customer profile information
- insurance
- list transactions for a retirement account
- list current investment positions and holdings in a tiaa account
- get plan
- get customer
- list all tiaa retirement accounts
- get specific retirement account details
- list transactions
- list participants
- customer retirement accounts
- get income projection for a participant
- fdx
- get customer profile
- list participants enrolled in the secure income account for a plan
- get sia plan configuration, eligibility rules, and allocation limits
- plan configuration
- individual account details
- list transaction history for a tiaa account within a date range
- plan participants
- list investment positions in a retirement account
- investment management
- tax documents
slug: retirement-data-access
source_filename: retirement-data-access.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: TIAA Retirement Data Access\n  description: >-\n    Unified capability for fintech developers, financial aggregators, and plan\n    administration platforms to access TIAA retirement account data. Combines the\n    FDX API for customer-consented data sharing and the SIA API for plan\n    administration, enabling a comprehensive view of participant retirement\n    savings, income projections, and account activity.\n  tags:\n    - TIAA\n    - Financial Data\n    - FDX\n    - Open Finance\n    - Plan Administration\n    - Retirement\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TIAA_FDX_ACCESS_TOKEN: TIAA_FDX_ACCESS_TOKEN\n      TIAA_SIA_ACCESS_TOKEN: TIAA_SIA_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: tiaa-fdx\n      location: ./shared/tiaa-fdx.yaml\n    - import: tiaa-sia\n      location: ./shared/tiaa-sia.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n\
  \      namespace: tiaa-retirement-api\n      description: >-\n        Unified REST API for accessing TIAA retirement account data, plan\n        administration, and income projections.\n      resources:\n        - path: /v1/accounts\n          name: accounts\n          description: Customer retirement accounts\n          operations:\n            - method: GET\n              name: list-accounts\n              description: List all TIAA retirement accounts\n              call: \"tiaa-fdx.list-accounts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/accounts/{accountId}\n          name: account-detail\n          description: Individual account details\n          operations:\n            - method: GET\n              name: get-account\n              description: Get specific retirement account details\n              call: \"tiaa-fdx.get-account\"\n              with:\n                accountId: \"rest.accountId\"\n\
  \              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/accounts/{accountId}/transactions\n          name: transactions\n          description: Account transaction history\n          operations:\n            - method: GET\n              name: list-transactions\n              description: List transactions for a retirement account\n              call: \"tiaa-fdx.list-transactions\"\n              with:\n                accountId: \"rest.accountId\"\n                startTime: \"rest.startTime\"\n                endTime: \"rest.endTime\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/accounts/{accountId}/positions\n          name: investment-positions\n          description: Investment positions and holdings\n          operations:\n            - method: GET\n              name: list-positions\n              description: List investment positions in\
  \ a retirement account\n              call: \"tiaa-fdx.list-positions\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/customer\n          name: customer\n          description: Customer profile\n          operations:\n            - method: GET\n              name: get-customer\n              description: Get customer profile information\n              call: \"tiaa-fdx.get-customer\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tax-forms\n          name: tax-forms\n          description: Tax documents\n          operations:\n            - method: GET\n              name: list-tax-forms\n              description: List available tax forms\n              call: \"tiaa-fdx.list-tax-forms\"\n              with:\n                taxYear: \"rest.taxYear\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/plans/{planId}\n          name: plan\n          description: Plan configuration\n          operations:\n            - method: GET\n              name: get-plan\n              description: Get SIA plan configuration\n              call: \"tiaa-sia.get-plan\"\n              with:\n                planId: \"rest.planId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/plans/{planId}/participants\n          name: participants\n          description: Plan participants\n          operations:\n            - method: GET\n              name: list-participants\n              description: List plan participants in SIA\n              call: \"tiaa-sia.list-participants\"\n              with:\n                planId: \"rest.planId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n  \
  \      - path: /v1/plans/{planId}/participants/{participantId}/projections\n          name: income-projections\n          description: Lifetime income projections\n          operations:\n            - method: GET\n              name: get-income-projection\n              description: Get income projection for a participant\n              call: \"tiaa-sia.get-income-projection\"\n              with:\n                planId: \"rest.planId\"\n                participantId: \"rest.participantId\"\n                retirementAge: \"rest.retirementAge\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: tiaa-retirement-mcp\n      transport: http\n      description: >-\n        MCP server for AI-assisted TIAA retirement account data access, plan\n        administration, and income planning.\n      tools:\n        - name: list-accounts\n          description: List all TIAA retirement and brokerage\
  \ accounts for the authenticated customer\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tiaa-fdx.list-accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-account\n          description: Get details for a specific TIAA account including current balance and status\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tiaa-fdx.get-account\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-transactions\n          description: List transaction history for a TIAA account within a date range\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tiaa-fdx.list-transactions\"\n          with:\n            accountId: \"tools.accountId\"\n            startTime: \"tools.startTime\"\
  \n            endTime: \"tools.endTime\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-investment-positions\n          description: List current investment positions and holdings in a TIAA account\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tiaa-fdx.list-positions\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-customer-profile\n          description: Get the authenticated customer's TIAA profile and contact information\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tiaa-fdx.get-customer\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-tax-forms\n          description: List available TIAA tax forms (1099-R, 5498) for a given tax year\n\
  \          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tiaa-fdx.list-tax-forms\"\n          with:\n            taxYear: \"tools.taxYear\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-plan-details\n          description: Get SIA plan configuration, eligibility rules, and allocation limits\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tiaa-sia.get-plan\"\n          with:\n            planId: \"tools.planId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-plan-participants\n          description: List participants enrolled in the Secure Income Account for a plan\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tiaa-sia.list-participants\"\n          with:\n            planId: \"tools.planId\"\n          outputParameters:\n    \
  \        - type: object\n              mapping: \"$.\"\n\n        - name: get-participant-details\n          description: Get SIA account details and balance for a specific plan participant\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tiaa-sia.get-participant\"\n          with:\n            planId: \"tools.planId\"\n            participantId: \"tools.participantId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-income-projection\n          description: Get projected lifetime monthly and annual income for a participant at a given retirement age\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tiaa-sia.get-income-projection\"\n          with:\n            planId: \"tools.planId\"\n            participantId: \"tools.participantId\"\n            retirementAge: \"tools.retirementAge\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n"
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
