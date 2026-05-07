---
categories: []
consumed_apis: []
description: Unified capability for the procure-to-pay process combining supplier management, purchase requisitions, purchase orders, goods receipts, and supplier invoice processing.
layout: capability
name: Workday Financials Procure To Pay
operations:
- description: List suppliers
  method: GET
  name: list-suppliers
  path: /v1/suppliers
- description: List purchase requisitions
  method: GET
  name: list-purchase-requisitions
  path: /v1/purchase-requisitions
- description: Create a purchase requisition
  method: POST
  name: create-purchase-requisition
  path: /v1/purchase-requisitions
- description: List purchase orders
  method: GET
  name: list-purchase-orders
  path: /v1/purchase-orders
- description: List supplier invoices
  method: GET
  name: list-supplier-invoices
  path: /v1/supplier-invoices
personas: []
provider_name: Workday Financials
provider_slug: workday-financials
search_terms:
- procurement
- list suppliers
- accounting
- get details of a specific purchase order
- financials
- list supplier invoices for payment processing
- accounts payable
- workday
- list supplier accounts in workday financials
- list purchase orders
- create a purchase requisition
- cloud erp
- list supplier invoices
- get supplier
- get purchase order
- procure to pay
- financial management
- list purchase requisitions
- purchase order management
- suppliers
- supplier account management
- create purchase requisition
- get details of a specific supplier
- supplier invoice processing
- create a new purchase requisition
- purchase requisition management
slug: procure-to-pay
source_filename: procure-to-pay.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Workday Financials Procure To Pay\n  description: Unified capability for the procure-to-pay process combining supplier management, purchase requisitions, purchase\n    orders, goods receipts, and supplier invoice processing.\n  tags:\n  - Workday\n  - Financials\n  - Procurement\n  - Procure To Pay\n  - Accounts Payable\n  - Suppliers\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WORKDAY_FINANCIALS_ACCESS_TOKEN: WORKDAY_FINANCIALS_ACCESS_TOKEN\n    WORKDAY_TENANT: WORKDAY_TENANT\ncapability:\n  consumes:\n  - type: http\n    namespace: financials-procurement\n    baseUri: https://{tenant}.workday.com/api/procurement/v38.2\n    description: Workday Financials procurement API\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_FINANCIALS_ACCESS_TOKEN}}'\n    resources:\n    - name: suppliers\n      path: /suppliers\n      description: Supplier management\n      operations:\n    \
  \  - name: list-suppliers\n        method: GET\n        description: List suppliers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-supplier\n        method: GET\n        description: Get a supplier\n        inputParameters:\n        - name: supplierId\n          in: path\n          type: string\n          required: true\n          description: Supplier identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: purchase-orders\n      path: /purchaseOrders\n      description: Purchase order management\n      operations:\n      - name: list-purchase-orders\n        method: GET\n        description: List purchase orders\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-purchase-order\n        method: GET\n \
  \       description: Get a purchase order\n        inputParameters:\n        - name: poId\n          in: path\n          type: string\n          required: true\n          description: Purchase order identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: requisitions\n      path: /purchaseRequisitions\n      description: Purchase requisition management\n      operations:\n      - name: list-purchase-requisitions\n        method: GET\n        description: List purchase requisitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-purchase-requisition\n        method: POST\n        description: Create a purchase requisition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n         \
  \ data:\n            description: '{{tools.description}}'\n            lines: '{{tools.lines}}'\n  - type: http\n    namespace: financials-core\n    baseUri: https://{tenant}.workday.com/api/financialManagement/v38.2\n    description: Workday Financials core financial management API\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_FINANCIALS_ACCESS_TOKEN}}'\n    resources:\n    - name: ledger-accounts\n      path: /ledgerAccounts\n      description: General ledger account management\n      operations:\n      - name: list-ledger-accounts\n        method: GET\n        description: List ledger accounts\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-ledger-account\n        method: GET\n        description: Get a ledger\
  \ account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Ledger account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: journal-entries\n      path: /journalEntries\n      description: Journal entry management\n      operations:\n      - name: list-journal-entries\n        method: GET\n        description: List journal entries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-journal-entry\n        method: POST\n        description: Create a journal entry\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            period: '{{tools.period}}'\n            lines:\
  \ '{{tools.lines}}'\n    - name: supplier-invoices\n      path: /supplierInvoices\n      description: Supplier invoice management\n      operations:\n      - name: list-supplier-invoices\n        method: GET\n        description: List supplier invoices\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-supplier-invoice\n        method: GET\n        description: Get a supplier invoice\n        inputParameters:\n        - name: invoiceId\n          in: path\n          type: string\n          required: true\n          description: Invoice identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customer-invoices\n      path: /customerInvoices\n      description: Customer invoice management\n      operations:\n      - name: list-customer-invoices\n        method: GET\n        description: List customer invoices\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cost-centers\n      path: /costCenters\n      description: Cost center management\n      operations:\n      - name: list-cost-centers\n        method: GET\n        description: List cost centers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: companies\n      path: /companies\n      description: Company entity management\n      operations:\n      - name: list-companies\n        method: GET\n        description: List companies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: workday-financials-p2p-api\n    description: Unified REST API for Workday Financials procure-to-pay process.\n    resources:\n    - path: /v1/suppliers\n\
  \      name: suppliers\n      description: Supplier account management\n      operations:\n      - method: GET\n        name: list-suppliers\n        description: List suppliers\n        call: financials-procurement.list-suppliers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/purchase-requisitions\n      name: purchase-requisitions\n      description: Purchase requisition management\n      operations:\n      - method: GET\n        name: list-purchase-requisitions\n        description: List purchase requisitions\n        call: financials-procurement.list-purchase-requisitions\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-purchase-requisition\n        description: Create a purchase requisition\n        call: financials-procurement.create-purchase-requisition\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/purchase-orders\n      name:\
  \ purchase-orders\n      description: Purchase order management\n      operations:\n      - method: GET\n        name: list-purchase-orders\n        description: List purchase orders\n        call: financials-procurement.list-purchase-orders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/supplier-invoices\n      name: supplier-invoices\n      description: Supplier invoice processing\n      operations:\n      - method: GET\n        name: list-supplier-invoices\n        description: List supplier invoices\n        call: financials-core.list-supplier-invoices\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: workday-financials-p2p-mcp\n    transport: http\n    description: MCP server for AI-assisted Workday Financials procure-to-pay process.\n    tools:\n    - name: list-suppliers\n      description: List supplier accounts in Workday Financials\n      hints:\n        readOnly:\
  \ true\n        openWorld: true\n      call: financials-procurement.list-suppliers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-supplier\n      description: Get details of a specific supplier\n      hints:\n        readOnly: true\n        openWorld: true\n      call: financials-procurement.get-supplier\n      with:\n        supplierId: tools.supplierId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-purchase-requisitions\n      description: List purchase requisitions\n      hints:\n        readOnly: true\n        openWorld: true\n      call: financials-procurement.list-purchase-requisitions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-purchase-requisition\n      description: Create a new purchase requisition\n      hints:\n        readOnly: false\n        destructive: false\n      call: financials-procurement.create-purchase-requisition\n      outputParameters:\n   \
  \   - type: object\n        mapping: $.\n    - name: list-purchase-orders\n      description: List purchase orders\n      hints:\n        readOnly: true\n        openWorld: true\n      call: financials-procurement.list-purchase-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-purchase-order\n      description: Get details of a specific purchase order\n      hints:\n        readOnly: true\n        openWorld: true\n      call: financials-procurement.get-purchase-order\n      with:\n        poId: tools.poId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-supplier-invoices\n      description: List supplier invoices for payment processing\n      hints:\n        readOnly: true\n        openWorld: true\n      call: financials-core.list-supplier-invoices\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/workday-financials/refs/heads/main/capabilities/procure-to-pay.yaml
tags:
- Workday
- Financials
- Procurement
- Procure To Pay
- Accounts Payable
- Suppliers
tools:
- description: List supplier accounts in Workday Financials
  hints:
    openWorld: true
    readOnly: true
  name: list-suppliers
- description: Get details of a specific supplier
  hints:
    openWorld: true
    readOnly: true
  name: get-supplier
- description: List purchase requisitions
  hints:
    openWorld: true
    readOnly: true
  name: list-purchase-requisitions
- description: Create a new purchase requisition
  hints:
    destructive: false
    readOnly: false
  name: create-purchase-requisition
- description: List purchase orders
  hints:
    openWorld: true
    readOnly: true
  name: list-purchase-orders
- description: Get details of a specific purchase order
  hints:
    openWorld: true
    readOnly: true
  name: get-purchase-order
- description: List supplier invoices for payment processing
  hints:
    openWorld: true
    readOnly: true
  name: list-supplier-invoices
---
