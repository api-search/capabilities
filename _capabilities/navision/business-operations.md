---
categories:
- procurement-supply-chain
consumed_apis: []
description: Unified workflow for day-to-day business operations in Dynamics 365 Business Central combining the Business Central API v2.0 for managing customers, vendors, items, orders, invoices, and financials. Used by accountants, sales teams, and operations managers.
layout: capability
name: Dynamics NAV Business Operations
operations:
- description: List available companies
  method: GET
  name: list-companies
  path: /v1/companies
- description: List all customers
  method: GET
  name: list-customers
  path: /v1/customers
- description: Create a customer
  method: POST
  name: create-customer
  path: /v1/customers
- description: Get a customer
  method: GET
  name: get-customer
  path: /v1/customers/{customer_id}
- description: List all vendors
  method: GET
  name: list-vendors
  path: /v1/vendors
- description: List all items
  method: GET
  name: list-items
  path: /v1/items
- description: List sales orders
  method: GET
  name: list-sales-orders
  path: /v1/sales-orders
- description: Create a sales order
  method: POST
  name: create-sales-order
  path: /v1/sales-orders
- description: List purchase orders
  method: GET
  name: list-purchase-orders
  path: /v1/purchase-orders
- description: List accounts
  method: GET
  name: list-accounts
  path: /v1/accounts
- description: List journals
  method: GET
  name: list-journals
  path: /v1/journals
- description: List sales invoices
  method: GET
  name: list-sales-invoices
  path: /v1/sales-invoices
personas: []
provider_name: Microsoft Dynamics NAV
provider_slug: navision
search_terms:
- list sales invoices
- create a new vendor
- create customer
- list journals
- general journals
- vendor management
- list items
- create sales order
- list general journals
- purchase orders
- inventory items
- dynamics 365
- list accounts
- business central
- create a new sales order
- dynamics nav
- business management
- list available companies
- create item
- create a customer
- purchasing
- get a customer
- general ledger accounts
- get a customer by id
- list inventory items
- inventory
- list purchase orders
- microsoft
- company information
- finance
- list all items
- list all sales orders
- get customer
- navision
- sales invoices
- create a sales order
- create a new inventory item
- list employees
- single customer
- list purchase invoices
- list customers
- list vendors
- create a new customer
- list all customers
- list all vendors
- create purchase order
- create a new purchase order
- sales
- erp
- create vendor
- customer management
- sales orders
- list all purchase orders
- list companies
- list all employees
- list general ledger accounts
- list sales orders
slug: business-operations
source_filename: business-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Dynamics NAV Business Operations\n  description: Unified workflow for day-to-day business operations in Dynamics 365 Business Central combining the Business\n    Central API v2.0 for managing customers, vendors, items, orders, invoices, and financials. Used by accountants, sales\n    teams, and operations managers.\n  tags:\n  - Business Central\n  - Dynamics 365\n  - ERP\n  - Finance\n  - Sales\n  - Purchasing\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    BC_OAUTH_TOKEN: BC_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: business-central-v2\n    baseUri: https://api.businesscentral.dynamics.com/v2.0/{environment}/api/v2.0\n    description: Dynamics 365 Business Central API v2.0 for business entity management.\n    authentication:\n      type: bearer\n      token: '{{BC_OAUTH_TOKEN}}'\n    resources:\n    - name: companies\n      path: /companies\n      description: Company\
  \ operations.\n      operations:\n      - name: list-companies\n        method: GET\n        description: List available companies.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customers\n      path: /companies({company_id})/customers\n      description: Customer management.\n      operations:\n      - name: list-customers\n        method: GET\n        description: List all customers.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-customer\n        method: POST\n        description: Create a new customer.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n       \
  \   description: Company ID\n        body:\n          type: json\n          data:\n            displayName: '{{tools.displayName}}'\n            email: '{{tools.email}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-customer\n        method: GET\n        description: Get a customer by ID.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        - name: customer_id\n          in: path\n          type: string\n          required: true\n          description: Customer ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-customer\n        method: PATCH\n        description: Update a customer.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n\
  \          required: true\n          description: Company ID\n        - name: customer_id\n          in: path\n          type: string\n          required: true\n          description: Customer ID\n        body:\n          type: json\n          data:\n            displayName: '{{tools.displayName}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-customer\n        method: DELETE\n        description: Delete a customer.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        - name: customer_id\n          in: path\n          type: string\n          required: true\n          description: Customer ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vendors\n      path: /companies({company_id})/vendors\n\
  \      description: Vendor management.\n      operations:\n      - name: list-vendors\n        method: GET\n        description: List all vendors.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-vendor\n        method: POST\n        description: Create a new vendor.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        body:\n          type: json\n          data:\n            displayName: '{{tools.displayName}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-vendor\n        method: GET\n        description: Get a vendor by\
  \ ID.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        - name: vendor_id\n          in: path\n          type: string\n          required: true\n          description: Vendor ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: items\n      path: /companies({company_id})/items\n      description: Inventory item management.\n      operations:\n      - name: list-items\n        method: GET\n        description: List all items.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-item\n        method: POST\n        description: Create\
  \ a new item.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        body:\n          type: json\n          data:\n            number: '{{tools.number}}'\n            displayName: '{{tools.displayName}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-item\n        method: GET\n        description: Get an item by ID.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        - name: item_id\n          in: path\n          type: string\n          required: true\n          description: Item ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sales-orders\n      path: /companies({company_id})/salesOrders\n\
  \      description: Sales order management.\n      operations:\n      - name: list-sales-orders\n        method: GET\n        description: List all sales orders.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-sales-order\n        method: POST\n        description: Create a new sales order.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        body:\n          type: json\n          data:\n            customerNumber: '{{tools.customerNumber}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-sales-order\n        method: GET\n\
  \        description: Get a sales order by ID.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        - name: salesOrder_id\n          in: path\n          type: string\n          required: true\n          description: Sales order ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: purchase-orders\n      path: /companies({company_id})/purchaseOrders\n      description: Purchase order management.\n      operations:\n      - name: list-purchase-orders\n        method: GET\n        description: List all purchase orders.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n      - name: create-purchase-order\n        method: POST\n        description: Create a new purchase order.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        body:\n          type: json\n          data:\n            vendorNumber: '{{tools.vendorNumber}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-purchase-order\n        method: GET\n        description: Get a purchase order by ID.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        - name: purchaseOrder_id\n          in: path\n          type: string\n          required: true\n          description: Purchase order ID\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: accounts\n      path: /companies({company_id})/accounts\n      description: General ledger accounts.\n      operations:\n      - name: list-accounts\n        method: GET\n        description: List all accounts.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: journals\n      path: /companies({company_id})/journals\n      description: General journal management.\n      operations:\n      - name: list-journals\n        method: GET\n        description: List all journals.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: create-journal\n        method: POST\n        description: Create a new journal.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        body:\n          type: json\n          data:\n            code: '{{tools.code}}'\n            displayName: '{{tools.displayName}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sales-invoices\n      path: /companies({company_id})/salesInvoices\n      description: Sales invoice management.\n      operations:\n      - name: list-sales-invoices\n        method: GET\n        description: List all sales invoices.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-sales-invoice\n        method: POST\n        description: Create a new sales invoice.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        body:\n          type: json\n          data:\n            customerNumber: '{{tools.customerNumber}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: purchase-invoices\n      path: /companies({company_id})/purchaseInvoices\n      description: Purchase invoice management.\n      operations:\n      - name: list-purchase-invoices\n        method: GET\n        description: List all purchase invoices.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n      \
  \    required: true\n          description: Company ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: employees\n      path: /companies({company_id})/employees\n      description: Employee management.\n      operations:\n      - name: list-employees\n        method: GET\n        description: List all employees.\n        inputParameters:\n        - name: company_id\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: business-ops-api\n    description: Unified REST API for Business Central day-to-day business operations.\n    resources:\n    - path: /v1/companies\n      name: companies\n      description: Company information\n      operations:\n      - method: GET\n\
  \        name: list-companies\n        description: List available companies\n        call: business-central-v2.list-companies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/customers\n      name: customers\n      description: Customer management\n      operations:\n      - method: GET\n        name: list-customers\n        description: List all customers\n        call: business-central-v2.list-customers\n        with:\n          company_id: rest.company_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-customer\n        description: Create a customer\n        call: business-central-v2.create-customer\n        with:\n          company_id: rest.company_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/customers/{customer_id}\n      name: customer\n      description: Single customer\n      operations:\n      - method: GET\n       \
  \ name: get-customer\n        description: Get a customer\n        call: business-central-v2.get-customer\n        with:\n          company_id: rest.company_id\n          customer_id: rest.customer_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vendors\n      name: vendors\n      description: Vendor management\n      operations:\n      - method: GET\n        name: list-vendors\n        description: List all vendors\n        call: business-central-v2.list-vendors\n        with:\n          company_id: rest.company_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/items\n      name: items\n      description: Inventory items\n      operations:\n      - method: GET\n        name: list-items\n        description: List all items\n        call: business-central-v2.list-items\n        with:\n          company_id: rest.company_id\n        outputParameters:\n        - type: object\n          mapping: $.\n \
  \   - path: /v1/sales-orders\n      name: sales-orders\n      description: Sales orders\n      operations:\n      - method: GET\n        name: list-sales-orders\n        description: List sales orders\n        call: business-central-v2.list-sales-orders\n        with:\n          company_id: rest.company_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-sales-order\n        description: Create a sales order\n        call: business-central-v2.create-sales-order\n        with:\n          company_id: rest.company_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/purchase-orders\n      name: purchase-orders\n      description: Purchase orders\n      operations:\n      - method: GET\n        name: list-purchase-orders\n        description: List purchase orders\n        call: business-central-v2.list-purchase-orders\n        with:\n          company_id: rest.company_id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/accounts\n      name: accounts\n      description: General ledger accounts\n      operations:\n      - method: GET\n        name: list-accounts\n        description: List accounts\n        call: business-central-v2.list-accounts\n        with:\n          company_id: rest.company_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/journals\n      name: journals\n      description: General journals\n      operations:\n      - method: GET\n        name: list-journals\n        description: List journals\n        call: business-central-v2.list-journals\n        with:\n          company_id: rest.company_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sales-invoices\n      name: sales-invoices\n      description: Sales invoices\n      operations:\n      - method: GET\n        name: list-sales-invoices\n        description: List sales invoices\n\
  \        call: business-central-v2.list-sales-invoices\n        with:\n          company_id: rest.company_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: business-ops-mcp\n    transport: http\n    description: MCP server for AI-assisted Business Central business operations.\n    tools:\n    - name: list-companies\n      description: List available companies\n      hints:\n        readOnly: true\n        idempotent: true\n      call: business-central-v2.list-companies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-customers\n      description: List all customers\n      hints:\n        readOnly: true\n        idempotent: true\n      call: business-central-v2.list-customers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-customer\n      description: Create a new customer\n      hints:\n        readOnly: false\n      call: business-central-v2.create-customer\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-customer\n      description: Get a customer by ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: business-central-v2.get-customer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-vendors\n      description: List all vendors\n      hints:\n        readOnly: true\n        idempotent: true\n      call: business-central-v2.list-vendors\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-vendor\n      description: Create a new vendor\n      hints:\n        readOnly: false\n      call: business-central-v2.create-vendor\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-items\n      description: List inventory items\n      hints:\n        readOnly: true\n        idempotent: true\n      call: business-central-v2.list-items\n      outputParameters:\n      - type: object\n   \
  \     mapping: $.\n    - name: create-item\n      description: Create a new inventory item\n      hints:\n        readOnly: false\n      call: business-central-v2.create-item\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-sales-orders\n      description: List all sales orders\n      hints:\n        readOnly: true\n        idempotent: true\n      call: business-central-v2.list-sales-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-sales-order\n      description: Create a new sales order\n      hints:\n        readOnly: false\n      call: business-central-v2.create-sales-order\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-purchase-orders\n      description: List all purchase orders\n      hints:\n        readOnly: true\n        idempotent: true\n      call: business-central-v2.list-purchase-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: create-purchase-order\n      description: Create a new purchase order\n      hints:\n        readOnly: false\n      call: business-central-v2.create-purchase-order\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-accounts\n      description: List general ledger accounts\n      hints:\n        readOnly: true\n        idempotent: true\n      call: business-central-v2.list-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-journals\n      description: List general journals\n      hints:\n        readOnly: true\n        idempotent: true\n      call: business-central-v2.list-journals\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-sales-invoices\n      description: List sales invoices\n      hints:\n        readOnly: true\n        idempotent: true\n      call: business-central-v2.list-sales-invoices\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: list-purchase-invoices\n      description: List purchase invoices\n      hints:\n        readOnly: true\n        idempotent: true\n      call: business-central-v2.list-purchase-invoices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-employees\n      description: List all employees\n      hints:\n        readOnly: true\n        idempotent: true\n      call: business-central-v2.list-employees\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/navision/refs/heads/main/capabilities/business-operations.yaml
tags:
- Business Central
- Dynamics 365
- ERP
- Finance
- Sales
- Purchasing
tools:
- description: List available companies
  hints:
    idempotent: true
    readOnly: true
  name: list-companies
- description: List all customers
  hints:
    idempotent: true
    readOnly: true
  name: list-customers
- description: Create a new customer
  hints:
    readOnly: false
  name: create-customer
- description: Get a customer by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-customer
- description: List all vendors
  hints:
    idempotent: true
    readOnly: true
  name: list-vendors
- description: Create a new vendor
  hints:
    readOnly: false
  name: create-vendor
- description: List inventory items
  hints:
    idempotent: true
    readOnly: true
  name: list-items
- description: Create a new inventory item
  hints:
    readOnly: false
  name: create-item
- description: List all sales orders
  hints:
    idempotent: true
    readOnly: true
  name: list-sales-orders
- description: Create a new sales order
  hints:
    readOnly: false
  name: create-sales-order
- description: List all purchase orders
  hints:
    idempotent: true
    readOnly: true
  name: list-purchase-orders
- description: Create a new purchase order
  hints:
    readOnly: false
  name: create-purchase-order
- description: List general ledger accounts
  hints:
    idempotent: true
    readOnly: true
  name: list-accounts
- description: List general journals
  hints:
    idempotent: true
    readOnly: true
  name: list-journals
- description: List sales invoices
  hints:
    idempotent: true
    readOnly: true
  name: list-sales-invoices
- description: List purchase invoices
  hints:
    idempotent: true
    readOnly: true
  name: list-purchase-invoices
- description: List all employees
  hints:
    idempotent: true
    readOnly: true
  name: list-employees
---
