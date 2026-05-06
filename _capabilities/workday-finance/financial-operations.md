---
categories: []
consumed_apis: []
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
- list financial accounts
- list journal entries
- list requisitions
- create supplier invoice
- accounts payable
- financial dimension worktag management
- purchase order management
- list general ledger accounts in workday finance
- create a supplier invoice
- list supplier accounts in the procurement system
- list cost center organizations
- finance
- list purchase requisitions
- list purchase orders, optionally filtered by status
- cloud
- accounting
- create a new purchase order for a supplier
- fiscal period management
- enterprise
- create a new journal entry in the general ledger
- purchase requisition management
- create purchase order
- general ledger account management
- list financial periods
- erp
- workday
- financial management
- general ledger
- list suppliers
- create journal entry
- list cost centers
- create a purchase order
- list journal entries, optionally filtered by period
- list worktags
- list supplier invoices
- supplier account management
- supplier invoice processing
- list accounts
- list supplier invoices for accounts payable processing
- create a new supplier invoice for payment processing
- list purchase orders
- journal entry management
- list financial dimension worktags
- cost center organization management
- list fiscal periods and their open/close status
- create a journal entry
- procurement
slug: financial-operations
source_filename: financial-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Workday Finance Financial Operations\n  description: Unified capability for financial operations combining general ledger management, procurement, and accounts\n    payable workflows. Enables finance teams to manage the full procure-to-pay and record-to-report lifecycle.\n  tags:\n  - Workday\n  - Finance\n  - Financial Management\n  - Procurement\n  - Accounts Payable\n  - General Ledger\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WORKDAY_FINANCE_ACCESS_TOKEN: WORKDAY_FINANCE_ACCESS_TOKEN\n    WORKDAY_TENANT: WORKDAY_TENANT\ncapability:\n  consumes:\n  - type: http\n    namespace: financial-management\n    baseUri: https://wd2-impl-services1.workday.com/ccx/api/financial-management/v41.2/{tenant}\n    description: Workday financial management core API\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_FINANCE_ACCESS_TOKEN}}'\n    resources:\n    - name: accounts\n      path:\
  \ /accounts\n      description: General ledger account management\n      operations:\n      - name: list-accounts\n        method: GET\n        description: List financial accounts\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Filter by account type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-account\n        method: GET\n        description: Get financial account details\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description:\
  \ Account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: journal-entries\n      path: /journalEntries\n      description: Journal entry management\n      operations:\n      - name: list-journal-entries\n        method: GET\n        description: List journal entries\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: period\n          in: query\n          type: string\n          required: false\n          description: Filter by accounting period\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-journal-entry\n        method: POST\n        description: Create a journal entry\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            period: '{{tools.period}}'\n            lines: '{{tools.lines}}'\n      - name: get-journal-entry\n        method: GET\n        description: Get journal entry details\n        inputParameters:\n        - name: journalEntryId\n          in: path\n          type: string\n          required: true\n          description: Journal entry identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cost-centers\n      path: /costCenters\n      description: Cost center management\n      operations:\n      - name: list-cost-centers\n        method: GET\n        description: List cost centers\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        outputRawFormat: json\n    \
  \    outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: worktags\n      path: /worktags\n      description: Worktag dimension management\n      operations:\n      - name: list-worktags\n        method: GET\n        description: List worktags\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Filter by worktag type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: financial-periods\n      path: /financialPeriods\n      description: Financial period management\n      operations:\n      - name: list-financial-periods\n        method: GET\n        description: List financial periods\n        inputParameters:\n        - name: fiscalYear\n          in: query\n          type: string\n          required: false\n          description: Filter by fiscal year\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: procurement\n    baseUri: https://wd2-impl-services1.workday.com/ccx/api/resource-management/v45.2/{tenant}\n    description: Workday procurement and supplier management API\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_FINANCE_ACCESS_TOKEN}}'\n    resources:\n    - name: suppliers\n      path: /suppliers\n      description: Supplier account management\n      operations:\n      - name: list-suppliers\n        method: GET\n        description: List suppliers\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-supplier\n        method: GET\n        description: Get supplier\
  \ details\n        inputParameters:\n        - name: supplierId\n          in: path\n          type: string\n          required: true\n          description: Supplier identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: purchase-orders\n      path: /purchaseOrders\n      description: Purchase order management\n      operations:\n      - name: list-purchase-orders\n        method: GET\n        description: List purchase orders\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-purchase-order\n        method: POST\n        description: Create a purchase order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            supplier: '{{tools.supplier}}'\n            orderDate: '{{tools.orderDate}}'\n    - name: supplier-invoices\n      path: /supplierInvoices\n      description: Supplier invoice processing\n      operations:\n      - name: list-supplier-invoices\n        method: GET\n        description: List supplier invoices\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-supplier-invoice\n        method: POST\n        description: Create a supplier invoice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n\
  \            supplier: '{{tools.supplier}}'\n            invoiceNumber: '{{tools.invoiceNumber}}'\n            totalAmount: '{{tools.totalAmount}}'\n    - name: requisitions\n      path: /requisitions\n      description: Purchase requisition management\n      operations:\n      - name: list-requisitions\n        method: GET\n        description: List purchase requisitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: workday-finance-api\n    description: Unified REST API for Workday Finance financial operations.\n    resources:\n    - path: /v1/accounts\n      name: accounts\n      description: General ledger account management\n      operations:\n      - method: GET\n        name: list-accounts\n        description: List financial accounts\n        call: financial-management.list-accounts\n        outputParameters:\n        - type: object\n     \
  \     mapping: $.\n    - path: /v1/journal-entries\n      name: journal-entries\n      description: Journal entry management\n      operations:\n      - method: GET\n        name: list-journal-entries\n        description: List journal entries\n        call: financial-management.list-journal-entries\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-journal-entry\n        description: Create a journal entry\n        call: financial-management.create-journal-entry\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cost-centers\n      name: cost-centers\n      description: Cost center organization management\n      operations:\n      - method: GET\n        name: list-cost-centers\n        description: List cost centers\n        call: financial-management.list-cost-centers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/worktags\n      name:\
  \ worktags\n      description: Financial dimension worktag management\n      operations:\n      - method: GET\n        name: list-worktags\n        description: List worktags\n        call: financial-management.list-worktags\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/financial-periods\n      name: financial-periods\n      description: Fiscal period management\n      operations:\n      - method: GET\n        name: list-financial-periods\n        description: List financial periods\n        call: financial-management.list-financial-periods\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/suppliers\n      name: suppliers\n      description: Supplier account management\n      operations:\n      - method: GET\n        name: list-suppliers\n        description: List suppliers\n        call: procurement.list-suppliers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /v1/purchase-orders\n      name: purchase-orders\n      description: Purchase order management\n      operations:\n      - method: GET\n        name: list-purchase-orders\n        description: List purchase orders\n        call: procurement.list-purchase-orders\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-purchase-order\n        description: Create a purchase order\n        call: procurement.create-purchase-order\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/supplier-invoices\n      name: supplier-invoices\n      description: Supplier invoice processing\n      operations:\n      - method: GET\n        name: list-supplier-invoices\n        description: List supplier invoices\n        call: procurement.list-supplier-invoices\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-supplier-invoice\n        description:\
  \ Create a supplier invoice\n        call: procurement.create-supplier-invoice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/requisitions\n      name: requisitions\n      description: Purchase requisition management\n      operations:\n      - method: GET\n        name: list-requisitions\n        description: List purchase requisitions\n        call: procurement.list-requisitions\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: workday-finance-mcp\n    transport: http\n    description: MCP server for AI-assisted Workday Finance operations.\n    tools:\n    - name: list-accounts\n      description: List general ledger accounts in Workday Finance\n      hints:\n        readOnly: true\n        openWorld: true\n      call: financial-management.list-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-journal-entries\n      description:\
  \ List journal entries, optionally filtered by period\n      hints:\n        readOnly: true\n        openWorld: true\n      call: financial-management.list-journal-entries\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-journal-entry\n      description: Create a new journal entry in the general ledger\n      hints:\n        readOnly: false\n        destructive: false\n      call: financial-management.create-journal-entry\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-cost-centers\n      description: List cost center organizations\n      hints:\n        readOnly: true\n        openWorld: true\n      call: financial-management.list-cost-centers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-worktags\n      description: List financial dimension worktags\n      hints:\n        readOnly: true\n        openWorld: true\n      call: financial-management.list-worktags\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-financial-periods\n      description: List fiscal periods and their open/close status\n      hints:\n        readOnly: true\n        openWorld: true\n      call: financial-management.list-financial-periods\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-suppliers\n      description: List supplier accounts in the procurement system\n      hints:\n        readOnly: true\n        openWorld: true\n      call: procurement.list-suppliers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-purchase-orders\n      description: List purchase orders, optionally filtered by status\n      hints:\n        readOnly: true\n        openWorld: true\n      call: procurement.list-purchase-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-purchase-order\n      description: Create a new purchase order for a supplier\n      hints:\n\
  \        readOnly: false\n        destructive: false\n      call: procurement.create-purchase-order\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-supplier-invoices\n      description: List supplier invoices for accounts payable processing\n      hints:\n        readOnly: true\n        openWorld: true\n      call: procurement.list-supplier-invoices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-supplier-invoice\n      description: Create a new supplier invoice for payment processing\n      hints:\n        readOnly: false\n        destructive: false\n      call: procurement.create-supplier-invoice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-requisitions\n      description: List purchase requisitions\n      hints:\n        readOnly: true\n        openWorld: true\n      call: procurement.list-requisitions\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n"
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
