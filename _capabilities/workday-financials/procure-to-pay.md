---
categories: []
consumed_apis:
- financials-procurement
- financials-core
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
- financials
- accounts payable
- workday
- accounting
- suppliers
- purchase order management
- create purchase requisition
- purchase requisition management
- supplier invoice processing
- list purchase requisitions
- list supplier invoices
- get purchase order
- create a purchase requisition
- list supplier invoices for payment processing
- create a new purchase requisition
- list purchase orders
- procurement
- get supplier
- list suppliers
- list supplier accounts in workday financials
- supplier account management
- financial management
- get details of a specific purchase order
- cloud erp
- get details of a specific supplier
- procure to pay
slug: procure-to-pay
source_filename: procure-to-pay.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Workday Financials Procure To Pay\"\n  description: \"Unified capability for the procure-to-pay process combining supplier management, purchase requisitions, purchase orders, goods receipts, and supplier invoice processing.\"\n  tags:\n    - Workday\n    - Financials\n    - Procurement\n    - Procure To Pay\n    - Accounts Payable\n    - Suppliers\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WORKDAY_FINANCIALS_ACCESS_TOKEN: WORKDAY_FINANCIALS_ACCESS_TOKEN\n      WORKDAY_TENANT: WORKDAY_TENANT\n\ncapability:\n  consumes:\n    - import: financials-procurement\n      location: ./shared/procurement.yaml\n    - import: financials-core\n      location: ./shared/financial-management.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: workday-financials-p2p-api\n      description: \"Unified REST API for Workday Financials procure-to-pay process.\"\n      resources:\n\
  \        - path: /v1/suppliers\n          name: suppliers\n          description: \"Supplier account management\"\n          operations:\n            - method: GET\n              name: list-suppliers\n              description: \"List suppliers\"\n              call: \"financials-procurement.list-suppliers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/purchase-requisitions\n          name: purchase-requisitions\n          description: \"Purchase requisition management\"\n          operations:\n            - method: GET\n              name: list-purchase-requisitions\n              description: \"List purchase requisitions\"\n              call: \"financials-procurement.list-purchase-requisitions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-purchase-requisition\n              description: \"Create a\
  \ purchase requisition\"\n              call: \"financials-procurement.create-purchase-requisition\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/purchase-orders\n          name: purchase-orders\n          description: \"Purchase order management\"\n          operations:\n            - method: GET\n              name: list-purchase-orders\n              description: \"List purchase orders\"\n              call: \"financials-procurement.list-purchase-orders\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/supplier-invoices\n          name: supplier-invoices\n          description: \"Supplier invoice processing\"\n          operations:\n            - method: GET\n              name: list-supplier-invoices\n              description: \"List supplier invoices\"\n              call: \"financials-core.list-supplier-invoices\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: workday-financials-p2p-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Workday Financials procure-to-pay process.\"\n      tools:\n        - name: list-suppliers\n          description: \"List supplier accounts in Workday Financials\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"financials-procurement.list-suppliers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-supplier\n          description: \"Get details of a specific supplier\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"financials-procurement.get-supplier\"\n          with:\n            supplierId: \"tools.supplierId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name:\
  \ list-purchase-requisitions\n          description: \"List purchase requisitions\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"financials-procurement.list-purchase-requisitions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-purchase-requisition\n          description: \"Create a new purchase requisition\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"financials-procurement.create-purchase-requisition\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-purchase-orders\n          description: \"List purchase orders\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"financials-procurement.list-purchase-orders\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-purchase-order\n\
  \          description: \"Get details of a specific purchase order\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"financials-procurement.get-purchase-order\"\n          with:\n            poId: \"tools.poId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-supplier-invoices\n          description: \"List supplier invoices for payment processing\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"financials-core.list-supplier-invoices\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
