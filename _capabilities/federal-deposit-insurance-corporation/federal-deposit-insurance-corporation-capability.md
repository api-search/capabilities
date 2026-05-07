---
categories: []
consumed_apis: []
description: The FDIC BankFind Suite API provides programmatic access to data about FDIC-insured banks and savings institutions, including institution profiles, branch locations, financial summaries, historical records, failures, deposits, and demographic data.
layout: capability
name: FDIC BankFind Suite API
operations:
- description: Search FDIC-insured institutions
  method: GET
  name: listinstitutions
  path: /institutions
- description: Search FDIC-insured branch and office locations
  method: GET
  name: listlocations
  path: /locations
- description: Retrieve financial reports for institutions
  method: GET
  name: listfinancials
  path: /financials
- description: Retrieve institution structure history
  method: GET
  name: listhistory
  path: /history
- description: List failed FDIC-insured institutions
  method: GET
  name: listfailures
  path: /failures
- description: Retrieve Summary of Deposits data
  method: GET
  name: listsummaryofdeposits
  path: /sod
- description: Retrieve demographic data
  method: GET
  name: listdemographics
  path: /demographics
personas: []
provider_name: Federal Deposit Insurance Corporation
provider_slug: federal-deposit-insurance-corporation
search_terms:
- listlocations
- deposit
- retrieve institution structure history
- federal
- corporation
- listfailures
- api
- retrieve financial reports for institutions
- search fdic-insured institutions
- listhistory
- retrieve demographic data
- listfinancials
- search fdic-insured branch and office locations
- listsummaryofdeposits
- financial data
- retrieve summary of deposits data
- list failed fdic-insured institutions
- listdemographics
- listinstitutions
- banking
- insurance
- federal government
slug: federal-deposit-insurance-corporation-capability
source_filename: federal-deposit-insurance-corporation-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: FDIC BankFind Suite API\n  description: The FDIC BankFind Suite API provides programmatic access to data about FDIC-insured banks and savings institutions,\n    including institution profiles, branch locations, financial summaries, historical records, failures, deposits, and demographic\n    data.\n  tags:\n  - Federal\n  - Deposit\n  - Insurance\n  - Corporation\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: federal-deposit-insurance-corporation\n    baseUri: https://banks.data.fdic.gov/api\n    description: FDIC BankFind Suite API HTTP API.\n    resources:\n    - name: institutions\n      path: /institutions\n      operations:\n      - name: listinstitutions\n        method: GET\n        description: Search FDIC-insured institutions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    -\
  \ name: locations\n      path: /locations\n      operations:\n      - name: listlocations\n        method: GET\n        description: Search FDIC-insured branch and office locations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: financials\n      path: /financials\n      operations:\n      - name: listfinancials\n        method: GET\n        description: Retrieve financial reports for institutions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: history\n      path: /history\n      operations:\n      - name: listhistory\n        method: GET\n        description: Retrieve institution structure history\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: failures\n      path: /failures\n      operations:\n      - name: listfailures\n\
  \        method: GET\n        description: List failed FDIC-insured institutions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sod\n      path: /sod\n      operations:\n      - name: listsummaryofdeposits\n        method: GET\n        description: Retrieve Summary of Deposits data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: demographics\n      path: /demographics\n      operations:\n      - name: listdemographics\n        method: GET\n        description: Retrieve demographic data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: federal-deposit-insurance-corporation-rest\n    description: REST adapter for FDIC BankFind Suite API.\n    resources:\n    - path: /institutions\n\
  \      name: listinstitutions\n      operations:\n      - method: GET\n        name: listinstitutions\n        description: Search FDIC-insured institutions\n        call: federal-deposit-insurance-corporation.listinstitutions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /locations\n      name: listlocations\n      operations:\n      - method: GET\n        name: listlocations\n        description: Search FDIC-insured branch and office locations\n        call: federal-deposit-insurance-corporation.listlocations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /financials\n      name: listfinancials\n      operations:\n      - method: GET\n        name: listfinancials\n        description: Retrieve financial reports for institutions\n        call: federal-deposit-insurance-corporation.listfinancials\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /history\n      name: listhistory\n\
  \      operations:\n      - method: GET\n        name: listhistory\n        description: Retrieve institution structure history\n        call: federal-deposit-insurance-corporation.listhistory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /failures\n      name: listfailures\n      operations:\n      - method: GET\n        name: listfailures\n        description: List failed FDIC-insured institutions\n        call: federal-deposit-insurance-corporation.listfailures\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sod\n      name: listsummaryofdeposits\n      operations:\n      - method: GET\n        name: listsummaryofdeposits\n        description: Retrieve Summary of Deposits data\n        call: federal-deposit-insurance-corporation.listsummaryofdeposits\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /demographics\n      name: listdemographics\n      operations:\n   \
  \   - method: GET\n        name: listdemographics\n        description: Retrieve demographic data\n        call: federal-deposit-insurance-corporation.listdemographics\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: federal-deposit-insurance-corporation-mcp\n    transport: http\n    description: MCP adapter for FDIC BankFind Suite API for AI agent use.\n    tools:\n    - name: listinstitutions\n      description: Search FDIC-insured institutions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-deposit-insurance-corporation.listinstitutions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listlocations\n      description: Search FDIC-insured branch and office locations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-deposit-insurance-corporation.listlocations\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfinancials\n      description: Retrieve financial reports for institutions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-deposit-insurance-corporation.listfinancials\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listhistory\n      description: Retrieve institution structure history\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-deposit-insurance-corporation.listhistory\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfailures\n      description: List failed FDIC-insured institutions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-deposit-insurance-corporation.listfailures\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: listsummaryofdeposits\n      description: Retrieve Summary of Deposits data\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-deposit-insurance-corporation.listsummaryofdeposits\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdemographics\n      description: Retrieve demographic data\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: federal-deposit-insurance-corporation.listdemographics\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/federal-deposit-insurance-corporation/refs/heads/main/capabilities/federal-deposit-insurance-corporation-capability.yaml
tags:
- Federal
- Deposit
- Insurance
- Corporation
- API
tools:
- description: Search FDIC-insured institutions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinstitutions
- description: Search FDIC-insured branch and office locations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlocations
- description: Retrieve financial reports for institutions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfinancials
- description: Retrieve institution structure history
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listhistory
- description: List failed FDIC-insured institutions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfailures
- description: Retrieve Summary of Deposits data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsummaryofdeposits
- description: Retrieve demographic data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdemographics
---
