---
categories: []
consumed_apis:
- financial-management
- procurement
description: Unified capability for financial operations combining general ledger management, procurement, and accounts payable workflows. Enables finance teams to manage the full procure-to-pay and record-to-report lifecycle.
layout: capability
name: Workday Finance Financial Operations
operations:
- description: List financial accounts
  method: GET
  name: list-accounts
  path: /v1/accounts
- description: List journal entries
  method: GET
  name: list-journal-entries
  path: /v1/journal-entries
- description: Create a journal entry
  method: POST
  name: create-journal-entry
  path: /v1/journal-entries
- description: List cost centers
  method: GET
  name: list-cost-centers
  path: /v1/cost-centers
- description: List worktags
  method: GET
  name: list-worktags
  path: /v1/worktags
- description: List financial periods
  method: GET
  name: list-financial-periods
  path: /v1/financial-periods
- description: List suppliers
  method: GET
  name: list-suppliers
  path: /v1/suppliers
- description: List purchase orders
  method: GET
  name: list-purchase-orders
  path: /v1/purchase-orders
- description: Create a purchase order
  method: POST
  name: create-purchase-order
  path: /v1/purchase-orders
- description: List supplier invoices
  method: GET
  name: list-supplier-invoices
  path: /v1/supplier-invoices
- description: Create a supplier invoice
  method: POST
  name: create-supplier-invoice
  path: /v1/supplier-invoices
- description: List purchase requisitions
  method: GET
  name: list-requisitions
  path: /v1/requisitions
personas: []
provider_name: Workday Finance
provider_slug: workday-finance
search_terms:
- list worktags
- workday
- list financial accounts
- list requisitions
- list supplier invoices for accounts payable processing
- financial dimension worktag management
- general ledger
- create a purchase order
- list accounts
- list suppliers
- create a new purchase order for a supplier
- cloud
- enterprise
- list fiscal periods and their open/close status
- accounting
- list purchase orders
- create a supplier invoice
- list supplier invoices
- finance
- accounts payable
- list journal entries
- purchase requisition management
- procurement
- erp
- supplier invoice processing
- list supplier accounts in the procurement system
- list cost center organizations
- cost center organization management
- general ledger account management
- list purchase orders, optionally filtered by status
- create purchase order
- list general ledger accounts in workday finance
- create a new journal entry in the general ledger
- journal entry management
- create journal entry
- create a journal entry
- supplier account management
- purchase order management
- list purchase requisitions
- financial management
- fiscal period management
- list financial periods
- list cost centers
- create supplier invoice
- list financial dimension worktags
- list journal entries, optionally filtered by period
- create a new supplier invoice for payment processing
slug: financial-operations
source_filename: financial-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Workday Finance Financial Operations\"\n  description: \"Unified capability for financial operations combining general ledger management, procurement, and accounts payable workflows. Enables finance teams to manage the full procure-to-pay and record-to-report lifecycle.\"\n  tags:\n    - Workday\n    - Finance\n    - Financial Management\n    - Procurement\n    - Accounts Payable\n    - General Ledger\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WORKDAY_FINANCE_ACCESS_TOKEN: WORKDAY_FINANCE_ACCESS_TOKEN\n      WORKDAY_TENANT: WORKDAY_TENANT\n\ncapability:\n  consumes:\n    - import: financial-management\n      location: ./shared/financial-management.yaml\n    - import: procurement\n      location: ./shared/procurement.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: workday-finance-api\n      description: \"Unified REST API for Workday Finance financial\
  \ operations.\"\n      resources:\n        - path: /v1/accounts\n          name: accounts\n          description: \"General ledger account management\"\n          operations:\n            - method: GET\n              name: list-accounts\n              description: \"List financial accounts\"\n              call: \"financial-management.list-accounts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/journal-entries\n          name: journal-entries\n          description: \"Journal entry management\"\n          operations:\n            - method: GET\n              name: list-journal-entries\n              description: \"List journal entries\"\n              call: \"financial-management.list-journal-entries\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-journal-entry\n              description: \"Create a journal\
  \ entry\"\n              call: \"financial-management.create-journal-entry\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cost-centers\n          name: cost-centers\n          description: \"Cost center organization management\"\n          operations:\n            - method: GET\n              name: list-cost-centers\n              description: \"List cost centers\"\n              call: \"financial-management.list-cost-centers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/worktags\n          name: worktags\n          description: \"Financial dimension worktag management\"\n          operations:\n            - method: GET\n              name: list-worktags\n              description: \"List worktags\"\n              call: \"financial-management.list-worktags\"\n              outputParameters:\n                - type: object\n           \
  \       mapping: \"$.\"\n        - path: /v1/financial-periods\n          name: financial-periods\n          description: \"Fiscal period management\"\n          operations:\n            - method: GET\n              name: list-financial-periods\n              description: \"List financial periods\"\n              call: \"financial-management.list-financial-periods\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/suppliers\n          name: suppliers\n          description: \"Supplier account management\"\n          operations:\n            - method: GET\n              name: list-suppliers\n              description: \"List suppliers\"\n              call: \"procurement.list-suppliers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/purchase-orders\n          name: purchase-orders\n          description: \"Purchase order management\"\n      \
  \    operations:\n            - method: GET\n              name: list-purchase-orders\n              description: \"List purchase orders\"\n              call: \"procurement.list-purchase-orders\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-purchase-order\n              description: \"Create a purchase order\"\n              call: \"procurement.create-purchase-order\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/supplier-invoices\n          name: supplier-invoices\n          description: \"Supplier invoice processing\"\n          operations:\n            - method: GET\n              name: list-supplier-invoices\n              description: \"List supplier invoices\"\n              call: \"procurement.list-supplier-invoices\"\n              outputParameters:\n                - type: object\n           \
  \       mapping: \"$.\"\n            - method: POST\n              name: create-supplier-invoice\n              description: \"Create a supplier invoice\"\n              call: \"procurement.create-supplier-invoice\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/requisitions\n          name: requisitions\n          description: \"Purchase requisition management\"\n          operations:\n            - method: GET\n              name: list-requisitions\n              description: \"List purchase requisitions\"\n              call: \"procurement.list-requisitions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: workday-finance-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Workday Finance operations.\"\n      tools:\n        - name: list-accounts\n          description: \"List general\
  \ ledger accounts in Workday Finance\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"financial-management.list-accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-journal-entries\n          description: \"List journal entries, optionally filtered by period\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"financial-management.list-journal-entries\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-journal-entry\n          description: \"Create a new journal entry in the general ledger\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"financial-management.create-journal-entry\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-cost-centers\n          description:\
  \ \"List cost center organizations\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"financial-management.list-cost-centers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-worktags\n          description: \"List financial dimension worktags\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"financial-management.list-worktags\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-financial-periods\n          description: \"List fiscal periods and their open/close status\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"financial-management.list-financial-periods\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-suppliers\n          description: \"List supplier accounts in\
  \ the procurement system\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"procurement.list-suppliers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-purchase-orders\n          description: \"List purchase orders, optionally filtered by status\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"procurement.list-purchase-orders\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-purchase-order\n          description: \"Create a new purchase order for a supplier\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"procurement.create-purchase-order\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-supplier-invoices\n          description: \"List supplier invoices for accounts\
  \ payable processing\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"procurement.list-supplier-invoices\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-supplier-invoice\n          description: \"Create a new supplier invoice for payment processing\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"procurement.create-supplier-invoice\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-requisitions\n          description: \"List purchase requisitions\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"procurement.list-requisitions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/workday-finance/refs/heads/main/capabilities/financial-operations.yaml
tags:
- Workday
- Finance
- Financial Management
- Procurement
- Accounts Payable
- General Ledger
tools:
- description: List general ledger accounts in Workday Finance
  hints:
    openWorld: true
    readOnly: true
  name: list-accounts
- description: List journal entries, optionally filtered by period
  hints:
    openWorld: true
    readOnly: true
  name: list-journal-entries
- description: Create a new journal entry in the general ledger
  hints:
    destructive: false
    readOnly: false
  name: create-journal-entry
- description: List cost center organizations
  hints:
    openWorld: true
    readOnly: true
  name: list-cost-centers
- description: List financial dimension worktags
  hints:
    openWorld: true
    readOnly: true
  name: list-worktags
- description: List fiscal periods and their open/close status
  hints:
    openWorld: true
    readOnly: true
  name: list-financial-periods
- description: List supplier accounts in the procurement system
  hints:
    openWorld: true
    readOnly: true
  name: list-suppliers
- description: List purchase orders, optionally filtered by status
  hints:
    openWorld: true
    readOnly: true
  name: list-purchase-orders
- description: Create a new purchase order for a supplier
  hints:
    destructive: false
    readOnly: false
  name: create-purchase-order
- description: List supplier invoices for accounts payable processing
  hints:
    openWorld: true
    readOnly: true
  name: list-supplier-invoices
- description: Create a new supplier invoice for payment processing
  hints:
    destructive: false
    readOnly: false
  name: create-supplier-invoice
- description: List purchase requisitions
  hints:
    openWorld: true
    readOnly: true
  name: list-requisitions
---
