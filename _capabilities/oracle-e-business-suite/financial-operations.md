---
categories:
- procurement-supply-chain
consumed_apis: []
description: End-to-end financial operations combining General Ledger, AP/AR, procurement, and cash management. Used by finance teams and controllers for the procure-to-pay and order-to-cash cycles.
layout: capability
name: Oracle EBS Financial Operations
operations:
- description: List journal entries.
  method: GET
  name: get-journals
  path: /v1/journals
- description: List AP invoices.
  method: GET
  name: get-ap-invoices
  path: /v1/ap-invoices
- description: List AR invoices.
  method: GET
  name: get-ar-invoices
  path: /v1/ar-invoices
- description: List purchase orders.
  method: GET
  name: get-purchase-orders
  path: /v1/purchase-orders
- description: List suppliers.
  method: GET
  name: get-suppliers
  path: /v1/suppliers
personas: []
provider_name: Oracle E-Business Suite
provider_slug: oracle-e-business-suite
search_terms:
- get ap invoices
- ar get receipts
- po get requisitions
- procurement
- retrieve purchase orders.
- retrieve suppliers.
- e-business suite
- ap invoice management.
- get ar invoices
- retrieve payments.
- create an ap invoice.
- po get purchase orders
- get ap invoice by id.
- po get suppliers
- list suppliers.
- purchase order management.
- retrieve ap invoices.
- ap get payments
- business applications
- ap create invoice
- get purchase order by id.
- ce get bank accounts
- retrieve requisitions.
- retrieve fixed assets.
- get suppliers
- create an ar invoice.
- gl get journals
- gl create journal
- ap get invoices
- po create purchase order
- get purchase orders
- retrieve receipts.
- list ar invoices.
- retrieve bank accounts.
- create a purchase order.
- enterprise
- ar create invoice
- oracle
- ap get invoice by id
- list purchase orders.
- ar invoice management.
- journal entry management.
- list ap invoices.
- fa get assets
- retrieve general ledger journal entries.
- erp
- ar get invoices
- supplier management.
- po get purchase order by id
- get journals
- retrieve ar invoices.
- list journal entries.
- financials
- create a journal entry.
slug: financial-operations
source_filename: financial-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Oracle EBS Financial Operations\n  description: End-to-end financial operations combining General Ledger, AP/AR, procurement, and cash management. Used by\n    finance teams and controllers for the procure-to-pay and order-to-cash cycles.\n  tags:\n  - Oracle\n  - Financials\n  - Procurement\n  - ERP\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ORACLE_EBS_TOKEN: ORACLE_EBS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: oracle-financial-services\n    baseUri: https://{instance}.oracle.com/webservices/rest\n    description: Oracle EBS Financial Services API for managing financial transactions.\n    authentication:\n      type: bearer\n      token: '{{ORACLE_EBS_TOKEN}}'\n    resources:\n    - name: journals\n      path: /gl/journals\n      description: General Ledger journal entries.\n      operations:\n      - name: get-journals\n        method: GET\n        description: Retrieve\
  \ General Ledger journal entries.\n        inputParameters:\n        - name: ledgerId\n          in: query\n          type: integer\n          required: false\n          description: Ledger identifier.\n        - name: periodName\n          in: query\n          type: string\n          required: false\n          description: Accounting period name.\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Journal status (U=Unposted, A=Approved, P=Posted).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-journal\n        method: POST\n        description: Create a new journal entry.\n        body:\n          type: json\n          data:\n            ledgerId: '{{tools.ledger_id}}'\n            periodName: '{{tools.period_name}}'\n            journalCategory: '{{tools.journal_category}}'\n            lines: '{{tools.lines}}'\n   \
  \     outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ap-invoices\n      path: /ap/invoices\n      description: Accounts Payable invoices.\n      operations:\n      - name: get-ap-invoices\n        method: GET\n        description: Retrieve AP invoices.\n        inputParameters:\n        - name: vendorId\n          in: query\n          type: integer\n          required: false\n          description: Vendor identifier.\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Invoice status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-ap-invoice\n        method: POST\n        description: Create an AP invoice.\n        body:\n          type: json\n          data:\n            vendorId: '{{tools.vendor_id}}'\n            invoiceAmount: '{{tools.invoice_amount}}'\n\
  \            invoiceDate: '{{tools.invoice_date}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ap-invoice\n      path: /ap/invoices/{invoiceId}\n      description: Specific AP invoice.\n      operations:\n      - name: get-ap-invoice-by-id\n        method: GET\n        description: Get AP invoice by ID.\n        inputParameters:\n        - name: invoiceId\n          in: path\n          type: integer\n          required: true\n          description: Invoice identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payments\n      path: /ap/payments\n      description: AP payments.\n      operations:\n      - name: get-payments\n        method: GET\n        description: Retrieve payments.\n        inputParameters:\n        - name: vendorId\n          in: query\n          type: integer\n          required:\
  \ false\n          description: Vendor identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ar-invoices\n      path: /ar/invoices\n      description: Accounts Receivable invoices.\n      operations:\n      - name: get-ar-invoices\n        method: GET\n        description: Retrieve AR invoices.\n        inputParameters:\n        - name: customerId\n          in: query\n          type: integer\n          required: false\n          description: Customer identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-ar-invoice\n        method: POST\n        description: Create an AR invoice.\n        body:\n          type: json\n          data:\n            customerId: '{{tools.customer_id}}'\n            amount: '{{tools.amount}}'\n        outputRawFormat: json\n        outputParameters:\n     \
  \   - name: result\n          type: object\n          value: $.\n    - name: receipts\n      path: /ar/receipts\n      description: AR receipts.\n      operations:\n      - name: get-receipts\n        method: GET\n        description: Retrieve receipts.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets\n      path: /fa/assets\n      description: Fixed assets.\n      operations:\n      - name: get-assets\n        method: GET\n        description: Retrieve fixed assets.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bank-accounts\n      path: /ce/bank-accounts\n      description: Cash management bank accounts.\n      operations:\n      - name: get-bank-accounts\n        method: GET\n        description: Retrieve bank accounts.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n  - type: http\n    namespace: oracle-supply-chain\n    baseUri: https://{instance}.oracle.com/webservices/rest\n    description: Oracle EBS Supply Chain API for managing procurement and inventory.\n    authentication:\n      type: bearer\n      token: '{{ORACLE_EBS_TOKEN}}'\n    resources:\n    - name: purchase-orders\n      path: /po/purchase-orders\n      description: Purchase order management.\n      operations:\n      - name: get-purchase-orders\n        method: GET\n        description: Retrieve purchase orders.\n        inputParameters:\n        - name: vendorId\n          in: query\n          type: integer\n          required: false\n          description: Vendor identifier.\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: PO status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: create-purchase-order\n        method: POST\n        description: Create a purchase order.\n        body:\n          type: json\n          data:\n            vendorId: '{{tools.vendor_id}}'\n            lines: '{{tools.lines}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: purchase-order\n      path: /po/purchase-orders/{poHeaderId}\n      description: Specific purchase order.\n      operations:\n      - name: get-purchase-order-by-id\n        method: GET\n        description: Get purchase order by ID.\n        inputParameters:\n        - name: poHeaderId\n          in: path\n          type: integer\n          required: true\n          description: PO header identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-purchase-order\n        method: PUT\n        description:\
  \ Update a purchase order.\n        inputParameters:\n        - name: poHeaderId\n          in: path\n          type: integer\n          required: true\n          description: PO header identifier.\n        body:\n          type: json\n          data:\n            status: '{{tools.status}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: requisitions\n      path: /po/requisitions\n      description: Purchase requisitions.\n      operations:\n      - name: get-requisitions\n        method: GET\n        description: Retrieve requisitions.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: suppliers\n      path: /po/suppliers\n      description: Supplier management.\n      operations:\n      - name: get-suppliers\n        method: GET\n        description: Retrieve suppliers.\n        outputRawFormat: json\n   \
  \     outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sales-orders\n      path: /oe/sales-orders\n      description: Sales order management.\n      operations:\n      - name: get-sales-orders\n        method: GET\n        description: Retrieve sales orders.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-sales-order\n        method: POST\n        description: Create a sales order.\n        body:\n          type: json\n          data:\n            customerId: '{{tools.customer_id}}'\n            lines: '{{tools.lines}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: inventory-items\n      path: /inv/items\n      description: Inventory items.\n      operations:\n      - name: get-inventory-items\n        method: GET\n        description: Retrieve\
  \ inventory items.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: onhand-quantities\n      path: /inv/onhand\n      description: On-hand inventory quantities.\n      operations:\n      - name: get-onhand-quantities\n        method: GET\n        description: Retrieve on-hand quantities.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deliveries\n      path: /wsh/deliveries\n      description: Shipping deliveries.\n      operations:\n      - name: get-deliveries\n        method: GET\n        description: Retrieve deliveries.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: financial-operations-api\n    description: Unified REST API for Oracle EBS financial operations.\n\
  \    resources:\n    - path: /v1/journals\n      name: journals\n      description: Journal entry management.\n      operations:\n      - method: GET\n        name: get-journals\n        description: List journal entries.\n        call: oracle-financial-services.get-journals\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ap-invoices\n      name: ap-invoices\n      description: AP invoice management.\n      operations:\n      - method: GET\n        name: get-ap-invoices\n        description: List AP invoices.\n        call: oracle-financial-services.get-ap-invoices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ar-invoices\n      name: ar-invoices\n      description: AR invoice management.\n      operations:\n      - method: GET\n        name: get-ar-invoices\n        description: List AR invoices.\n        call: oracle-financial-services.get-ar-invoices\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/purchase-orders\n      name: purchase-orders\n      description: Purchase order management.\n      operations:\n      - method: GET\n        name: get-purchase-orders\n        description: List purchase orders.\n        call: oracle-supply-chain.get-purchase-orders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/suppliers\n      name: suppliers\n      description: Supplier management.\n      operations:\n      - method: GET\n        name: get-suppliers\n        description: List suppliers.\n        call: oracle-supply-chain.get-suppliers\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: financial-operations-mcp\n    transport: http\n    description: MCP server for AI-assisted Oracle EBS financial operations.\n    tools:\n    - name: gl-get-journals\n      description: Retrieve General Ledger journal entries.\n      hints:\n        readOnly:\
  \ true\n        openWorld: true\n      call: oracle-financial-services.get-journals\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gl-create-journal\n      description: Create a journal entry.\n      hints:\n        readOnly: false\n      call: oracle-financial-services.create-journal\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ap-get-invoices\n      description: Retrieve AP invoices.\n      hints:\n        readOnly: true\n      call: oracle-financial-services.get-ap-invoices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ap-create-invoice\n      description: Create an AP invoice.\n      hints:\n        readOnly: false\n      call: oracle-financial-services.create-ap-invoice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ap-get-invoice-by-id\n      description: Get AP invoice by ID.\n      hints:\n        readOnly: true\n      call: oracle-financial-services.get-ap-invoice-by-id\n\
  \      with:\n        invoiceId: tools.invoice_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ap-get-payments\n      description: Retrieve payments.\n      hints:\n        readOnly: true\n      call: oracle-financial-services.get-payments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ar-get-invoices\n      description: Retrieve AR invoices.\n      hints:\n        readOnly: true\n      call: oracle-financial-services.get-ar-invoices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ar-create-invoice\n      description: Create an AR invoice.\n      hints:\n        readOnly: false\n      call: oracle-financial-services.create-ar-invoice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ar-get-receipts\n      description: Retrieve receipts.\n      hints:\n        readOnly: true\n      call: oracle-financial-services.get-receipts\n      outputParameters:\n  \
  \    - type: object\n        mapping: $.\n    - name: fa-get-assets\n      description: Retrieve fixed assets.\n      hints:\n        readOnly: true\n      call: oracle-financial-services.get-assets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ce-get-bank-accounts\n      description: Retrieve bank accounts.\n      hints:\n        readOnly: true\n      call: oracle-financial-services.get-bank-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: po-get-purchase-orders\n      description: Retrieve purchase orders.\n      hints:\n        readOnly: true\n      call: oracle-supply-chain.get-purchase-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: po-create-purchase-order\n      description: Create a purchase order.\n      hints:\n        readOnly: false\n      call: oracle-supply-chain.create-purchase-order\n      outputParameters:\n      - type: object\n        mapping: $.\n    -\
  \ name: po-get-purchase-order-by-id\n      description: Get purchase order by ID.\n      hints:\n        readOnly: true\n      call: oracle-supply-chain.get-purchase-order-by-id\n      with:\n        poHeaderId: tools.po_header_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: po-get-requisitions\n      description: Retrieve requisitions.\n      hints:\n        readOnly: true\n      call: oracle-supply-chain.get-requisitions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: po-get-suppliers\n      description: Retrieve suppliers.\n      hints:\n        readOnly: true\n      call: oracle-supply-chain.get-suppliers\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/oracle-e-business-suite/refs/heads/main/capabilities/financial-operations.yaml
tags:
- Oracle
- Financials
- Procurement
- ERP
tools:
- description: Retrieve General Ledger journal entries.
  hints:
    openWorld: true
    readOnly: true
  name: gl-get-journals
- description: Create a journal entry.
  hints:
    readOnly: false
  name: gl-create-journal
- description: Retrieve AP invoices.
  hints:
    readOnly: true
  name: ap-get-invoices
- description: Create an AP invoice.
  hints:
    readOnly: false
  name: ap-create-invoice
- description: Get AP invoice by ID.
  hints:
    readOnly: true
  name: ap-get-invoice-by-id
- description: Retrieve payments.
  hints:
    readOnly: true
  name: ap-get-payments
- description: Retrieve AR invoices.
  hints:
    readOnly: true
  name: ar-get-invoices
- description: Create an AR invoice.
  hints:
    readOnly: false
  name: ar-create-invoice
- description: Retrieve receipts.
  hints:
    readOnly: true
  name: ar-get-receipts
- description: Retrieve fixed assets.
  hints:
    readOnly: true
  name: fa-get-assets
- description: Retrieve bank accounts.
  hints:
    readOnly: true
  name: ce-get-bank-accounts
- description: Retrieve purchase orders.
  hints:
    readOnly: true
  name: po-get-purchase-orders
- description: Create a purchase order.
  hints:
    readOnly: false
  name: po-create-purchase-order
- description: Get purchase order by ID.
  hints:
    readOnly: true
  name: po-get-purchase-order-by-id
- description: Retrieve requisitions.
  hints:
    readOnly: true
  name: po-get-requisitions
- description: Retrieve suppliers.
  hints:
    readOnly: true
  name: po-get-suppliers
---
