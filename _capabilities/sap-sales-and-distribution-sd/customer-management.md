---
categories: []
consumed_apis:
- customer-master-data
- credit-management
description: Unified capability for customer and credit management operations in SAP S/4HANA Sales and Distribution. Combines Customer Master Data, Credit Management, and Customer Material APIs for sales administrators and credit controllers. Covers business partner maintenance, credit limit management, and customer-specific product mapping workflows.
layout: capability
name: SAP SD Customer Management
operations:
- description: List all customers / business partners
  method: GET
  name: list-customers
  path: /v1/customers
- description: Create a new customer / business partner
  method: POST
  name: create-customer
  path: /v1/customers
- description: Get a specific customer / business partner
  method: GET
  name: get-customer
  path: /v1/customers/{id}
- description: List credit management accounts
  method: GET
  name: list-credit-accounts
  path: /v1/credit-accounts
- description: List credit limits
  method: GET
  name: list-credit-limits
  path: /v1/credit-limits
personas: []
provider_name: SAP Sales and Distribution (SD)
provider_slug: sap-sales-and-distribution-sd
search_terms:
- create a new customer / business partner
- customer credit limits
- list all business partners and customers from sap s/4hana
- list credit limits for customers
- sap
- get credit account details for a specific business partner
- list credit management accounts
- sales
- create customer
- customer management
- credit management account operations
- list credit management accounts from sap s/4hana
- credit management
- s/4hana
- get a specific customer / business partner
- get a specific business partner / customer by number
- erp
- list customers
- list credit limits
- create a new business partner / customer record
- distribution
- update customer
- get customer
- list credit accounts
- single customer / business partner
- update an existing business partner / customer
- list all customers / business partners
- odata
- get credit account
- sales and distribution
- customer / business partner management
slug: customer-management
source_filename: customer-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SAP SD Customer Management\"\n  description: >-\n    Unified capability for customer and credit management operations in SAP\n    S/4HANA Sales and Distribution. Combines Customer Master Data, Credit\n    Management, and Customer Material APIs for sales administrators and\n    credit controllers. Covers business partner maintenance, credit limit\n    management, and customer-specific product mapping workflows.\n  tags:\n    - SAP\n    - Sales and Distribution\n    - Customer Management\n    - Credit Management\n    - OData\n    - S/4HANA\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SAP_SD_API_KEY: SAP_SD_API_KEY\n\ncapability:\n  consumes:\n    - import: customer-master-data\n      location: ./shared/customer-master-data.yaml\n    - import: credit-management\n      location: ./shared/credit-management.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace:\
  \ customer-management-api\n      description: \"Unified REST API for SAP SD customer and credit management.\"\n      resources:\n        - path: /v1/customers\n          name: customers\n          description: Customer / business partner management\n          operations:\n            - method: GET\n              name: list-customers\n              description: List all customers / business partners\n              call: \"customer-master-data.list-business-partners\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-customer\n              description: Create a new customer / business partner\n              call: \"customer-master-data.create-business-partner\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/customers/{id}\n          name: customer-by-id\n          description: Single customer / business partner\n\
  \          operations:\n            - method: GET\n              name: get-customer\n              description: Get a specific customer / business partner\n              call: \"customer-master-data.get-business-partner\"\n              with:\n                BusinessPartner: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/credit-accounts\n          name: credit-accounts\n          description: Credit management account operations\n          operations:\n            - method: GET\n              name: list-credit-accounts\n              description: List credit management accounts\n              call: \"credit-management.list-credit-accounts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/credit-limits\n          name: credit-limits\n          description: Customer credit limits\n          operations:\n            - method: GET\n\
  \              name: list-credit-limits\n              description: List credit limits\n              call: \"credit-management.list-credit-limits\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: customer-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted customer and credit management in SAP SD.\"\n      tools:\n        - name: list-customers\n          description: List all business partners and customers from SAP S/4HANA\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"customer-master-data.list-business-partners\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-customer\n          description: Get a specific business partner / customer by number\n          hints:\n            readOnly: true\n            openWorld: false\n          call:\
  \ \"customer-master-data.get-business-partner\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-customer\n          description: Create a new business partner / customer record\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"customer-master-data.create-business-partner\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-customer\n          description: Update an existing business partner / customer\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"customer-master-data.update-business-partner\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-credit-accounts\n          description: List credit management accounts from SAP S/4HANA\n          hints:\n            readOnly: true\n\
  \            openWorld: true\n          call: \"credit-management.list-credit-accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-credit-account\n          description: Get credit account details for a specific business partner\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"credit-management.get-credit-account\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-credit-limits\n          description: List credit limits for customers\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"credit-management.list-credit-limits\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sap-sales-and-distribution-sd/refs/heads/main/capabilities/customer-management.yaml
tags:
- SAP
- Sales and Distribution
- Customer Management
- Credit Management
- OData
- S/4HANA
tools:
- description: List all business partners and customers from SAP S/4HANA
  hints:
    openWorld: true
    readOnly: true
  name: list-customers
- description: Get a specific business partner / customer by number
  hints:
    openWorld: false
    readOnly: true
  name: get-customer
- description: Create a new business partner / customer record
  hints:
    destructive: false
    readOnly: false
  name: create-customer
- description: Update an existing business partner / customer
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-customer
- description: List credit management accounts from SAP S/4HANA
  hints:
    openWorld: true
    readOnly: true
  name: list-credit-accounts
- description: Get credit account details for a specific business partner
  hints:
    openWorld: false
    readOnly: true
  name: get-credit-account
- description: List credit limits for customers
  hints:
    openWorld: true
    readOnly: true
  name: list-credit-limits
---
