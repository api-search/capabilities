---
categories:
- procurement-supply-chain
consumed_apis:
- workday-finance
description: Unified financial operations combining Financial Management and procurement data for finance teams to manage accounting, suppliers, expenses, and invoices.
layout: capability
name: Workday Finance and Procurement
operations:
- description: List accounting journals
  method: GET
  name: list-journals
  path: /v1/accounting-journals
- description: List suppliers
  method: GET
  name: list-suppliers
  path: /v1/suppliers
personas: []
provider_name: Workday
provider_slug: workday
search_terms:
- get supplier
- list accounting journals
- list customer invoices
- financial management
- saas
- accounting journals
- cloud computing
- get a supplier by id
- list purchase orders
- procurement
- get expense report
- hcm
- get an expense report by id
- workday
- list journals
- get an accounting journal by id
- list suppliers
- get accounting journal
- suppliers
- list expense reports
- enterprise software
slug: finance-and-procurement
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Workday Finance and Procurement\"\n  description: \"Unified financial operations combining Financial Management and procurement data for finance teams to manage accounting, suppliers, expenses, and invoices.\"\n  tags:\n    - Workday\n    - Financial Management\n    - Procurement\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      WORKDAY_OAUTH_TOKEN: WORKDAY_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: workday-finance\n      location: ./shared/financial-management.yaml\n\n  exposes:\n    - type: rest\n      port: 8084\n      namespace: finance-procurement-api\n      description: \"Unified REST API for finance and procurement.\"\n      resources:\n        - path: /v1/accounting-journals\n          name: journals\n          description: \"Accounting journals\"\n          operations:\n            - method: GET\n              name: list-journals\n              description:\
  \ \"List accounting journals\"\n              call: \"workday-finance.get-accounting-journals\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/suppliers\n          name: suppliers\n          description: \"Suppliers\"\n          operations:\n            - method: GET\n              name: list-suppliers\n              description: \"List suppliers\"\n              call: \"workday-finance.get-suppliers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9084\n      namespace: finance-procurement-mcp\n      transport: http\n      description: \"MCP server for AI-assisted finance and procurement.\"\n      tools:\n        - name: list-accounting-journals\n          description: \"List accounting journals\"\n          hints:\n            readOnly: true\n          call: \"workday-finance.get-accounting-journals\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: get-accounting-journal\n          description: \"Get an accounting journal by ID\"\n          hints:\n            readOnly: true\n          call: \"workday-finance.get-accounting-journal-by-id\"\n          with:\n            ID: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-suppliers\n          description: \"List suppliers\"\n          hints:\n            readOnly: true\n          call: \"workday-finance.get-suppliers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-supplier\n          description: \"Get a supplier by ID\"\n          hints:\n            readOnly: true\n          call: \"workday-finance.get-supplier-by-id\"\n          with:\n            ID: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-purchase-orders\n\
  \          description: \"List purchase orders\"\n          hints:\n            readOnly: true\n          call: \"workday-finance.get-purchase-orders\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-expense-reports\n          description: \"List expense reports\"\n          hints:\n            readOnly: true\n          call: \"workday-finance.get-expense-reports\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-expense-report\n          description: \"Get an expense report by ID\"\n          hints:\n            readOnly: true\n          call: \"workday-finance.get-expense-report-by-id\"\n          with:\n            ID: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-customer-invoices\n          description: \"List customer invoices\"\n          hints:\n            readOnly: true\n        \
  \  call: \"workday-finance.get-customer-invoices\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/workday/refs/heads/main/capabilities/finance-and-procurement.yaml
tags:
- Workday
- Financial Management
- Procurement
tools:
- description: List accounting journals
  hints:
    readOnly: true
  name: list-accounting-journals
- description: Get an accounting journal by ID
  hints:
    readOnly: true
  name: get-accounting-journal
- description: List suppliers
  hints:
    readOnly: true
  name: list-suppliers
- description: Get a supplier by ID
  hints:
    readOnly: true
  name: get-supplier
- description: List purchase orders
  hints:
    readOnly: true
  name: list-purchase-orders
- description: List expense reports
  hints:
    readOnly: true
  name: list-expense-reports
- description: Get an expense report by ID
  hints:
    readOnly: true
  name: get-expense-report
- description: List customer invoices
  hints:
    readOnly: true
  name: list-customer-invoices
---
