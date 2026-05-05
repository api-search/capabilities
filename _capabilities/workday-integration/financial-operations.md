---
categories: []
consumed_apis: []
description: Integrated financial operations workflow combining general ledger, accounts payable, accounts receivable, procurement, cash management, and financial reporting capabilities in Workday.
layout: capability
name: Workday Financial Operations Workflow
operations:
- description: ''
  method: GET
  name: list-ledger-accounts
  path: /v1/ledger-accounts
- description: ''
  method: GET
  name: list-journal-entries
  path: /v1/journal-entries
personas: []
provider_name: Workday Integration
provider_slug: workday-integration
search_terms:
- workday
- list bank transactions
- integration
- enterprise
- get journal entry
- hcm
- accounting
- cash management
- finance
- list ledger accounts
- payroll
- list journal entries
- get details of a journal entry
- procurement
- erp
- list financial cost centers
- list transactions
- list general ledger accounts
- list bank accounts
- financial management
- list cost centers
- list accounting journal entries
slug: financial-operations
source_filename: financial-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Workday Financial Operations Workflow\"\n  description: \"Integrated financial operations workflow combining general ledger, accounts payable, accounts receivable, procurement, cash management, and financial reporting capabilities in Workday.\"\n  tags:\n    - Workday\n    - Integration\n    - Financial Management\n    - Accounting\n    - Procurement\n    - Cash Management\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WORKDAY_INTEGRATION_ACCESS_TOKEN: WORKDAY_INTEGRATION_ACCESS_TOKEN\n      WORKDAY_TENANT: WORKDAY_TENANT\n\ncapability:\n  consumes:\n    - type: http\n      namespace: financials\n      baseUri: https://wd2-impl-services1.workday.com/ccx/service/{tenant}\n      description: \"Workday Financial Management API\"\n      authentication:\n        type: bearer\n        token: \"{{WORKDAY_INTEGRATION_ACCESS_TOKEN}}\"\n      resources:\n        - name: ledger-accounts\n\
  \          path: /ledgerAccounts\n          operations:\n            - name: list-ledger-accounts\n              method: GET\n              description: \"List ledger accounts\"\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n        - name: journal-entries\n          path: /journalEntries\n          operations:\n            - name: list-journal-entries\n              method: GET\n              description: \"List journal entries\"\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n            - name: get-journal-entry\n              method: GET\n              description: \"Get a journal entry\"\n              inputParameters:\n                - name: journalEntryId\n                  in: path\n                  type: string\n                  required:\
  \ true\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n        - name: cost-centers\n          path: /costCenters\n          operations:\n            - name: list-cost-centers\n              method: GET\n              description: \"List cost centers\"\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n    - type: http\n      namespace: cash-management\n      baseUri: https://wd2-impl-services1.workday.com/ccx/service/{tenant}\n      description: \"Workday Cash Management API\"\n      authentication:\n        type: bearer\n        token: \"{{WORKDAY_INTEGRATION_ACCESS_TOKEN}}\"\n      resources:\n        - name: bank-accounts\n          path: /bankAccounts\n          operations:\n            - name: list-bank-accounts\n              method: GET\n      \
  \        description: \"List bank accounts\"\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n        - name: transactions\n          path: /bankTransactions\n          operations:\n            - name: list-transactions\n              method: GET\n              description: \"List bank transactions\"\n              inputParameters:\n                - name: period\n                  in: query\n                  type: string\n                  required: false\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n\n  exposes:\n    - type: rest\n      port: 8083\n      namespace: financial-operations-rest-api\n      resources:\n        - path: /v1/ledger-accounts\n          name: ledger-accounts\n          operations:\n            - method: GET\n              name:\
  \ list-ledger-accounts\n              call: \"financials.list-ledger-accounts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/journal-entries\n          name: journal-entries\n          operations:\n            - method: GET\n              name: list-journal-entries\n              call: \"financials.list-journal-entries\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9093\n      namespace: financial-operations-mcp\n      transport: http\n      tools:\n        - name: list-ledger-accounts\n          description: \"List general ledger accounts\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"financials.list-ledger-accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-journal-entries\n          description: \"List accounting\
  \ journal entries\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"financials.list-journal-entries\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-journal-entry\n          description: \"Get details of a journal entry\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"financials.get-journal-entry\"\n          with:\n            journalEntryId: \"tools.journalEntryId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-cost-centers\n          description: \"List financial cost centers\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"financials.list-cost-centers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-bank-accounts\n          description: \"List bank accounts\"\
  \n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cash-management.list-bank-accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-transactions\n          description: \"List bank transactions\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cash-management.list-transactions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/workday-integration/refs/heads/main/capabilities/financial-operations.yaml
tags:
- Workday
- Integration
- Financial Management
- Accounting
- Procurement
- Cash Management
tools:
- description: List general ledger accounts
  hints:
    openWorld: true
    readOnly: true
  name: list-ledger-accounts
- description: List accounting journal entries
  hints:
    openWorld: true
    readOnly: true
  name: list-journal-entries
- description: Get details of a journal entry
  hints:
    openWorld: false
    readOnly: true
  name: get-journal-entry
- description: List financial cost centers
  hints:
    openWorld: true
    readOnly: true
  name: list-cost-centers
- description: List bank accounts
  hints:
    openWorld: true
    readOnly: true
  name: list-bank-accounts
- description: List bank transactions
  hints:
    openWorld: true
    readOnly: true
  name: list-transactions
---
