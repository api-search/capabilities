---
categories: []
consumed_apis: []
description: The Microsoft Dynamics 365 Business Central API (v2.0) provides a RESTful interface for integrating with Business Central. It exposes standard business entities such as customers, vendors, items, sales orders, purchase orders, journals, and general ledger entries. The API uses OData v4 conventions and requires Microsoft Entra ID (Azure AD) authentication.
layout: capability
name: Microsoft Dynamics 365 Business Central API
operations:
- description: Microsoft Dynamics List companies
  method: GET
  name: listcompanies
  path: /companies
- description: Microsoft Dynamics List customers
  method: GET
  name: listcustomers
  path: /companies({companyId})/customers
- description: Microsoft Dynamics Create a customer
  method: POST
  name: createcustomer
  path: /companies({companyId})/customers
- description: Microsoft Dynamics Get a customer
  method: GET
  name: getcustomer
  path: /companies({companyId})/customers({customerId})
- description: Microsoft Dynamics Update a customer
  method: PATCH
  name: updatecustomer
  path: /companies({companyId})/customers({customerId})
- description: Microsoft Dynamics Delete a customer
  method: DELETE
  name: deletecustomer
  path: /companies({companyId})/customers({customerId})
- description: Microsoft Dynamics List vendors
  method: GET
  name: listvendors
  path: /companies({companyId})/vendors
- description: Microsoft Dynamics Create a vendor
  method: POST
  name: createvendor
  path: /companies({companyId})/vendors
- description: Microsoft Dynamics List items
  method: GET
  name: listitems
  path: /companies({companyId})/items
- description: Microsoft Dynamics Create an item
  method: POST
  name: createitem
  path: /companies({companyId})/items
- description: Microsoft Dynamics List sales orders
  method: GET
  name: listsalesorders
  path: /companies({companyId})/salesOrders
- description: Microsoft Dynamics Create a sales order
  method: POST
  name: createsalesorder
  path: /companies({companyId})/salesOrders
- description: Microsoft Dynamics List sales invoices
  method: GET
  name: listsalesinvoices
  path: /companies({companyId})/salesInvoices
- description: Microsoft Dynamics Create a sales invoice
  method: POST
  name: createsalesinvoice
  path: /companies({companyId})/salesInvoices
- description: Microsoft Dynamics List purchase orders
  method: GET
  name: listpurchaseorders
  path: /companies({companyId})/purchaseOrders
- description: Microsoft Dynamics Create a purchase order
  method: POST
  name: createpurchaseorder
  path: /companies({companyId})/purchaseOrders
- description: Microsoft Dynamics List purchase invoices
  method: GET
  name: listpurchaseinvoices
  path: /companies({companyId})/purchaseInvoices
- description: Microsoft Dynamics Create a purchase invoice
  method: POST
  name: createpurchaseinvoice
  path: /companies({companyId})/purchaseInvoices
- description: Microsoft Dynamics List general ledger entries
  method: GET
  name: listgeneralledgerentries
  path: /companies({companyId})/generalLedgerEntries
- description: Microsoft Dynamics List chart of accounts
  method: GET
  name: listaccounts
  path: /companies({companyId})/accounts
- description: Microsoft Dynamics List journals
  method: GET
  name: listjournals
  path: /companies({companyId})/journals
- description: Microsoft Dynamics Create a journal
  method: POST
  name: createjournal
  path: /companies({companyId})/journals
- description: Microsoft Dynamics List employees
  method: GET
  name: listemployees
  path: /companies({companyId})/employees
- description: Microsoft Dynamics Create an employee
  method: POST
  name: createemployee
  path: /companies({companyId})/employees
personas: []
provider_name: Microsoft Dynamics
provider_slug: microsoft-dynamics
search_terms:
- microsoft dynamics list vendors
- microsoft dynamics delete a customer
- microsoft dynamics list sales invoices
- listaccounts
- microsoft dynamics create a sales order
- microsoft dynamics list chart of accounts
- dynamics
- microsoft dynamics get a customer
- microsoft dynamics create an employee
- microsoft dynamics list general ledger entries
- listjournals
- microsoft dynamics list purchase invoices
- listitems
- createsalesinvoice
- listvendors
- createpurchaseinvoice
- listcustomers
- microsoft dynamics list customers
- microsoft dynamics create a purchase invoice
- erp
- microsoft dynamics create a customer
- createsalesorder
- createitem
- getcustomer
- microsoft dynamics list sales orders
- createjournal
- crm
- api
- microsoft dynamics update a customer
- microsoft dynamics
- listsalesorders
- createcustomer
- microsoft dynamics list items
- listsalesinvoices
- listpurchaseinvoices
- listcompanies
- microsoft dynamics create an item
- updatecustomer
- microsoft dynamics create a journal
- createvendor
- microsoft dynamics list purchase orders
- deletecustomer
- microsoft dynamics list journals
- listemployees
- createemployee
- listgeneralledgerentries
- listpurchaseorders
- microsoft dynamics create a purchase order
- microsoft dynamics list companies
- microsoft
- microsoft dynamics create a vendor
- createpurchaseorder
- microsoft dynamics list employees
- microsoft dynamics create a sales invoice
slug: microsoft-dynamics-capability
source_filename: microsoft-dynamics-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Microsoft Dynamics 365 Business Central API\n  description: The Microsoft Dynamics 365 Business Central API (v2.0) provides a RESTful interface for integrating with Business\n    Central. It exposes standard business entities such as customers, vendors, items, sales orders, purchase orders, journals,\n    and general ledger entries. The API uses OData v4 conventions and requires Microsoft Entra ID (Azure AD) authentication.\n  tags:\n  - Microsoft\n  - Dynamics\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: microsoft-dynamics\n    baseUri: https://api.businesscentral.dynamics.com/v2.0/common/production/api/v2.0\n    description: Microsoft Dynamics 365 Business Central API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{MICROSOFT_DYNAMICS_TOKEN}}'\n    resources:\n    - name: companies\n      path: /companies\n      operations:\n      - name: listcompanies\n\
  \        method: GET\n        description: Microsoft Dynamics List companies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: companies-companyid-customers\n      path: /companies({companyId})/customers\n      operations:\n      - name: listcustomers\n        method: GET\n        description: Microsoft Dynamics List customers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcustomer\n        method: POST\n        description: Microsoft Dynamics Create a customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: companies-companyid-customers-customerid\n      path: /companies({companyId})/customers({customerId})\n      operations:\n      - name: getcustomer\n        method: GET\n        description: Microsoft Dynamics\
  \ Get a customer\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecustomer\n        method: PATCH\n        description: Microsoft Dynamics Update a customer\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecustomer\n        method: DELETE\n        description: Microsoft Dynamics Delete a customer\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n   \
  \ - name: companies-companyid-vendors\n      path: /companies({companyId})/vendors\n      operations:\n      - name: listvendors\n        method: GET\n        description: Microsoft Dynamics List vendors\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createvendor\n        method: POST\n        description: Microsoft Dynamics Create a vendor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: companies-companyid-items\n      path: /companies({companyId})/items\n      operations:\n      - name: listitems\n        method: GET\n        description: Microsoft Dynamics List items\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createitem\n        method: POST\n        description: Microsoft Dynamics Create an item\n   \
  \     outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: companies-companyid-salesorders\n      path: /companies({companyId})/salesOrders\n      operations:\n      - name: listsalesorders\n        method: GET\n        description: Microsoft Dynamics List sales orders\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsalesorder\n        method: POST\n        description: Microsoft Dynamics Create a sales order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: companies-companyid-salesinvoices\n      path: /companies({companyId})/salesInvoices\n      operations:\n      - name: listsalesinvoices\n        method: GET\n        description: Microsoft Dynamics List sales invoices\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: createsalesinvoice\n        method: POST\n        description: Microsoft Dynamics Create a sales invoice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: companies-companyid-purchaseorders\n      path: /companies({companyId})/purchaseOrders\n      operations:\n      - name: listpurchaseorders\n        method: GET\n        description: Microsoft Dynamics List purchase orders\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createpurchaseorder\n        method: POST\n        description: Microsoft Dynamics Create a purchase order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: companies-companyid-purchaseinvoices\n      path: /companies({companyId})/purchaseInvoices\n\
  \      operations:\n      - name: listpurchaseinvoices\n        method: GET\n        description: Microsoft Dynamics List purchase invoices\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createpurchaseinvoice\n        method: POST\n        description: Microsoft Dynamics Create a purchase invoice\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: companies-companyid-generalledgerentries\n      path: /companies({companyId})/generalLedgerEntries\n      operations:\n      - name: listgeneralledgerentries\n        method: GET\n        description: Microsoft Dynamics List general ledger entries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: companies-companyid-accounts\n      path: /companies({companyId})/accounts\n  \
  \    operations:\n      - name: listaccounts\n        method: GET\n        description: Microsoft Dynamics List chart of accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: companies-companyid-journals\n      path: /companies({companyId})/journals\n      operations:\n      - name: listjournals\n        method: GET\n        description: Microsoft Dynamics List journals\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createjournal\n        method: POST\n        description: Microsoft Dynamics Create a journal\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: companies-companyid-employees\n      path: /companies({companyId})/employees\n      operations:\n      - name: listemployees\n        method: GET\n        description:\
  \ Microsoft Dynamics List employees\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createemployee\n        method: POST\n        description: Microsoft Dynamics Create an employee\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: microsoft-dynamics-rest\n    description: REST adapter for Microsoft Dynamics 365 Business Central API.\n    resources:\n    - path: /companies\n      name: listcompanies\n      operations:\n      - method: GET\n        name: listcompanies\n        description: Microsoft Dynamics List companies\n        call: microsoft-dynamics.listcompanies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /companies({companyId})/customers\n      name: listcustomers\n      operations:\n      - method: GET\n    \
  \    name: listcustomers\n        description: Microsoft Dynamics List customers\n        call: microsoft-dynamics.listcustomers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /companies({companyId})/customers\n      name: createcustomer\n      operations:\n      - method: POST\n        name: createcustomer\n        description: Microsoft Dynamics Create a customer\n        call: microsoft-dynamics.createcustomer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /companies({companyId})/customers({customerId})\n      name: getcustomer\n      operations:\n      - method: GET\n        name: getcustomer\n        description: Microsoft Dynamics Get a customer\n        call: microsoft-dynamics.getcustomer\n        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /companies({companyId})/customers({customerId})\n      name: updatecustomer\n\
  \      operations:\n      - method: PATCH\n        name: updatecustomer\n        description: Microsoft Dynamics Update a customer\n        call: microsoft-dynamics.updatecustomer\n        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /companies({companyId})/customers({customerId})\n      name: deletecustomer\n      operations:\n      - method: DELETE\n        name: deletecustomer\n        description: Microsoft Dynamics Delete a customer\n        call: microsoft-dynamics.deletecustomer\n        with:\n          customerId: rest.customerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /companies({companyId})/vendors\n      name: listvendors\n      operations:\n      - method: GET\n        name: listvendors\n        description: Microsoft Dynamics List vendors\n        call: microsoft-dynamics.listvendors\n        outputParameters:\n        - type: object\n    \
  \      mapping: $.\n    - path: /companies({companyId})/vendors\n      name: createvendor\n      operations:\n      - method: POST\n        name: createvendor\n        description: Microsoft Dynamics Create a vendor\n        call: microsoft-dynamics.createvendor\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /companies({companyId})/items\n      name: listitems\n      operations:\n      - method: GET\n        name: listitems\n        description: Microsoft Dynamics List items\n        call: microsoft-dynamics.listitems\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /companies({companyId})/items\n      name: createitem\n      operations:\n      - method: POST\n        name: createitem\n        description: Microsoft Dynamics Create an item\n        call: microsoft-dynamics.createitem\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /companies({companyId})/salesOrders\n  \
  \    name: listsalesorders\n      operations:\n      - method: GET\n        name: listsalesorders\n        description: Microsoft Dynamics List sales orders\n        call: microsoft-dynamics.listsalesorders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /companies({companyId})/salesOrders\n      name: createsalesorder\n      operations:\n      - method: POST\n        name: createsalesorder\n        description: Microsoft Dynamics Create a sales order\n        call: microsoft-dynamics.createsalesorder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /companies({companyId})/salesInvoices\n      name: listsalesinvoices\n      operations:\n      - method: GET\n        name: listsalesinvoices\n        description: Microsoft Dynamics List sales invoices\n        call: microsoft-dynamics.listsalesinvoices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /companies({companyId})/salesInvoices\n\
  \      name: createsalesinvoice\n      operations:\n      - method: POST\n        name: createsalesinvoice\n        description: Microsoft Dynamics Create a sales invoice\n        call: microsoft-dynamics.createsalesinvoice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /companies({companyId})/purchaseOrders\n      name: listpurchaseorders\n      operations:\n      - method: GET\n        name: listpurchaseorders\n        description: Microsoft Dynamics List purchase orders\n        call: microsoft-dynamics.listpurchaseorders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /companies({companyId})/purchaseOrders\n      name: createpurchaseorder\n      operations:\n      - method: POST\n        name: createpurchaseorder\n        description: Microsoft Dynamics Create a purchase order\n        call: microsoft-dynamics.createpurchaseorder\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /companies({companyId})/purchaseInvoices\n      name: listpurchaseinvoices\n      operations:\n      - method: GET\n        name: listpurchaseinvoices\n        description: Microsoft Dynamics List purchase invoices\n        call: microsoft-dynamics.listpurchaseinvoices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /companies({companyId})/purchaseInvoices\n      name: createpurchaseinvoice\n      operations:\n      - method: POST\n        name: createpurchaseinvoice\n        description: Microsoft Dynamics Create a purchase invoice\n        call: microsoft-dynamics.createpurchaseinvoice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /companies({companyId})/generalLedgerEntries\n      name: listgeneralledgerentries\n      operations:\n      - method: GET\n        name: listgeneralledgerentries\n        description: Microsoft Dynamics List general ledger entries\n        call: microsoft-dynamics.listgeneralledgerentries\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /companies({companyId})/accounts\n      name: listaccounts\n      operations:\n      - method: GET\n        name: listaccounts\n        description: Microsoft Dynamics List chart of accounts\n        call: microsoft-dynamics.listaccounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /companies({companyId})/journals\n      name: listjournals\n      operations:\n      - method: GET\n        name: listjournals\n        description: Microsoft Dynamics List journals\n        call: microsoft-dynamics.listjournals\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /companies({companyId})/journals\n      name: createjournal\n      operations:\n      - method: POST\n        name: createjournal\n        description: Microsoft Dynamics Create a journal\n        call: microsoft-dynamics.createjournal\n        outputParameters:\n       \
  \ - type: object\n          mapping: $.\n    - path: /companies({companyId})/employees\n      name: listemployees\n      operations:\n      - method: GET\n        name: listemployees\n        description: Microsoft Dynamics List employees\n        call: microsoft-dynamics.listemployees\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /companies({companyId})/employees\n      name: createemployee\n      operations:\n      - method: POST\n        name: createemployee\n        description: Microsoft Dynamics Create an employee\n        call: microsoft-dynamics.createemployee\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: microsoft-dynamics-mcp\n    transport: http\n    description: MCP adapter for Microsoft Dynamics 365 Business Central API for AI agent use.\n    tools:\n    - name: listcompanies\n      description: Microsoft Dynamics List companies\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: microsoft-dynamics.listcompanies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcustomers\n      description: Microsoft Dynamics List customers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-dynamics.listcustomers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcustomer\n      description: Microsoft Dynamics Create a customer\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-dynamics.createcustomer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcustomer\n      description: Microsoft Dynamics Get a customer\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-dynamics.getcustomer\n      with:\n        customerId:\
  \ tools.customerId\n      inputParameters:\n      - name: customerId\n        type: string\n        description: customerId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecustomer\n      description: Microsoft Dynamics Update a customer\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-dynamics.updatecustomer\n      with:\n        customerId: tools.customerId\n      inputParameters:\n      - name: customerId\n        type: string\n        description: customerId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecustomer\n      description: Microsoft Dynamics Delete a customer\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: microsoft-dynamics.deletecustomer\n      with:\n        customerId: tools.customerId\n      inputParameters:\n      - name:\
  \ customerId\n        type: string\n        description: customerId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listvendors\n      description: Microsoft Dynamics List vendors\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-dynamics.listvendors\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createvendor\n      description: Microsoft Dynamics Create a vendor\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-dynamics.createvendor\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listitems\n      description: Microsoft Dynamics List items\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-dynamics.listitems\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: createitem\n      description: Microsoft Dynamics Create an item\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-dynamics.createitem\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsalesorders\n      description: Microsoft Dynamics List sales orders\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-dynamics.listsalesorders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsalesorder\n      description: Microsoft Dynamics Create a sales order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-dynamics.createsalesorder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsalesinvoices\n      description: Microsoft Dynamics List sales invoices\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: microsoft-dynamics.listsalesinvoices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsalesinvoice\n      description: Microsoft Dynamics Create a sales invoice\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-dynamics.createsalesinvoice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpurchaseorders\n      description: Microsoft Dynamics List purchase orders\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-dynamics.listpurchaseorders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createpurchaseorder\n      description: Microsoft Dynamics Create a purchase order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-dynamics.createpurchaseorder\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpurchaseinvoices\n      description: Microsoft Dynamics List purchase invoices\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-dynamics.listpurchaseinvoices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createpurchaseinvoice\n      description: Microsoft Dynamics Create a purchase invoice\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-dynamics.createpurchaseinvoice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listgeneralledgerentries\n      description: Microsoft Dynamics List general ledger entries\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-dynamics.listgeneralledgerentries\n      outputParameters:\n      - type: object\n    \
  \    mapping: $.\n    - name: listaccounts\n      description: Microsoft Dynamics List chart of accounts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-dynamics.listaccounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listjournals\n      description: Microsoft Dynamics List journals\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-dynamics.listjournals\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createjournal\n      description: Microsoft Dynamics Create a journal\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-dynamics.createjournal\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listemployees\n      description: Microsoft Dynamics List employees\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: microsoft-dynamics.listemployees\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createemployee\n      description: Microsoft Dynamics Create an employee\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-dynamics.createemployee\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MICROSOFT_DYNAMICS_TOKEN: MICROSOFT_DYNAMICS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-dynamics/refs/heads/main/capabilities/microsoft-dynamics-capability.yaml
tags:
- Microsoft
- Dynamics
- API
tools:
- description: Microsoft Dynamics List companies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcompanies
- description: Microsoft Dynamics List customers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcustomers
- description: Microsoft Dynamics Create a customer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcustomer
- description: Microsoft Dynamics Get a customer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcustomer
- description: Microsoft Dynamics Update a customer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatecustomer
- description: Microsoft Dynamics Delete a customer
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecustomer
- description: Microsoft Dynamics List vendors
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvendors
- description: Microsoft Dynamics Create a vendor
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createvendor
- description: Microsoft Dynamics List items
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listitems
- description: Microsoft Dynamics Create an item
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createitem
- description: Microsoft Dynamics List sales orders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsalesorders
- description: Microsoft Dynamics Create a sales order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsalesorder
- description: Microsoft Dynamics List sales invoices
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsalesinvoices
- description: Microsoft Dynamics Create a sales invoice
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsalesinvoice
- description: Microsoft Dynamics List purchase orders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpurchaseorders
- description: Microsoft Dynamics Create a purchase order
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpurchaseorder
- description: Microsoft Dynamics List purchase invoices
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpurchaseinvoices
- description: Microsoft Dynamics Create a purchase invoice
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpurchaseinvoice
- description: Microsoft Dynamics List general ledger entries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgeneralledgerentries
- description: Microsoft Dynamics List chart of accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaccounts
- description: Microsoft Dynamics List journals
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listjournals
- description: Microsoft Dynamics Create a journal
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createjournal
- description: Microsoft Dynamics List employees
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listemployees
- description: Microsoft Dynamics Create an employee
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createemployee
---
