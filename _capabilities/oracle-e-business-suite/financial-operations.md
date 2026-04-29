---
categories:
- procurement-supply-chain
consumed_apis:
- oracle-financial-services
- oracle-supply-chain
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
- retrieve purchase orders.
- journal entry management.
- get ar invoices
- retrieve bank accounts.
- get ap invoice by id.
- po get purchase orders
- retrieve fixed assets.
- get purchase orders
- create a journal entry.
- ap get payments
- list ar invoices.
- get suppliers
- erp
- retrieve general ledger journal entries.
- ar get invoices
- retrieve requisitions.
- po get purchase order by id
- retrieve receipts.
- ap get invoice by id
- ar invoice management.
- get ap invoices
- list journal entries.
- gl get journals
- purchase order management.
- retrieve suppliers.
- financials
- list ap invoices.
- create an ar invoice.
- po get suppliers
- e-business suite
- enterprise
- get journals
- ap invoice management.
- retrieve ap invoices.
- ap create invoice
- po create purchase order
- fa get assets
- gl create journal
- create a purchase order.
- oracle
- po get requisitions
- get purchase order by id.
- ar get receipts
- ce get bank accounts
- list purchase orders.
- list suppliers.
- create an ap invoice.
- supplier management.
- procurement
- retrieve payments.
- ar create invoice
- business applications
- ap get invoices
- retrieve ar invoices.
slug: financial-operations
source_filename: financial-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Oracle EBS Financial Operations\"\n  description: \"End-to-end financial operations combining General Ledger, AP/AR, procurement, and cash management. Used by finance teams and controllers for the procure-to-pay and order-to-cash cycles.\"\n  tags:\n    - Oracle\n    - Financials\n    - Procurement\n    - ERP\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      ORACLE_EBS_TOKEN: ORACLE_EBS_TOKEN\n\ncapability:\n  consumes:\n    - import: oracle-financial-services\n      location: ./shared/financial-services.yaml\n    - import: oracle-supply-chain\n      location: ./shared/supply-chain.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: financial-operations-api\n      description: \"Unified REST API for Oracle EBS financial operations.\"\n      resources:\n        - path: /v1/journals\n          name: journals\n          description: \"Journal entry management.\"\
  \n          operations:\n            - method: GET\n              name: get-journals\n              description: \"List journal entries.\"\n              call: \"oracle-financial-services.get-journals\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/ap-invoices\n          name: ap-invoices\n          description: \"AP invoice management.\"\n          operations:\n            - method: GET\n              name: get-ap-invoices\n              description: \"List AP invoices.\"\n              call: \"oracle-financial-services.get-ap-invoices\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/ar-invoices\n          name: ar-invoices\n          description: \"AR invoice management.\"\n          operations:\n            - method: GET\n              name: get-ar-invoices\n              description: \"List AR invoices.\"\n              call: \"oracle-financial-services.get-ar-invoices\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/purchase-orders\n          name: purchase-orders\n          description: \"Purchase order management.\"\n          operations:\n            - method: GET\n              name: get-purchase-orders\n              description: \"List purchase orders.\"\n              call: \"oracle-supply-chain.get-purchase-orders\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/suppliers\n          name: suppliers\n          description: \"Supplier management.\"\n          operations:\n            - method: GET\n              name: get-suppliers\n              description: \"List suppliers.\"\n              call: \"oracle-supply-chain.get-suppliers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: financial-operations-mcp\n\
  \      transport: http\n      description: \"MCP server for AI-assisted Oracle EBS financial operations.\"\n      tools:\n        - name: gl-get-journals\n          description: \"Retrieve General Ledger journal entries.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"oracle-financial-services.get-journals\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: gl-create-journal\n          description: \"Create a journal entry.\"\n          hints:\n            readOnly: false\n          call: \"oracle-financial-services.create-journal\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ap-get-invoices\n          description: \"Retrieve AP invoices.\"\n          hints:\n            readOnly: true\n          call: \"oracle-financial-services.get-ap-invoices\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: ap-create-invoice\n          description: \"Create an AP invoice.\"\n          hints:\n            readOnly: false\n          call: \"oracle-financial-services.create-ap-invoice\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ap-get-invoice-by-id\n          description: \"Get AP invoice by ID.\"\n          hints:\n            readOnly: true\n          call: \"oracle-financial-services.get-ap-invoice-by-id\"\n          with:\n            invoiceId: \"tools.invoice_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ap-get-payments\n          description: \"Retrieve payments.\"\n          hints:\n            readOnly: true\n          call: \"oracle-financial-services.get-payments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ar-get-invoices\n          description: \"Retrieve AR invoices.\"\
  \n          hints:\n            readOnly: true\n          call: \"oracle-financial-services.get-ar-invoices\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ar-create-invoice\n          description: \"Create an AR invoice.\"\n          hints:\n            readOnly: false\n          call: \"oracle-financial-services.create-ar-invoice\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ar-get-receipts\n          description: \"Retrieve receipts.\"\n          hints:\n            readOnly: true\n          call: \"oracle-financial-services.get-receipts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: fa-get-assets\n          description: \"Retrieve fixed assets.\"\n          hints:\n            readOnly: true\n          call: \"oracle-financial-services.get-assets\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: ce-get-bank-accounts\n          description: \"Retrieve bank accounts.\"\n          hints:\n            readOnly: true\n          call: \"oracle-financial-services.get-bank-accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: po-get-purchase-orders\n          description: \"Retrieve purchase orders.\"\n          hints:\n            readOnly: true\n          call: \"oracle-supply-chain.get-purchase-orders\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: po-create-purchase-order\n          description: \"Create a purchase order.\"\n          hints:\n            readOnly: false\n          call: \"oracle-supply-chain.create-purchase-order\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: po-get-purchase-order-by-id\n          description: \"Get purchase order by ID.\"\
  \n          hints:\n            readOnly: true\n          call: \"oracle-supply-chain.get-purchase-order-by-id\"\n          with:\n            poHeaderId: \"tools.po_header_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: po-get-requisitions\n          description: \"Retrieve requisitions.\"\n          hints:\n            readOnly: true\n          call: \"oracle-supply-chain.get-requisitions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: po-get-suppliers\n          description: \"Retrieve suppliers.\"\n          hints:\n            readOnly: true\n          call: \"oracle-supply-chain.get-suppliers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
