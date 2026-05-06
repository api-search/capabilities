---
categories: []
consumed_apis: []
description: Unified capability combining Yardi Voyager's property management operations for property managers and operations teams. Enables tenant management, billing, maintenance tracking, and financial reporting across real estate portfolios.
layout: capability
name: Yardi Property Management
operations:
- description: List resident transactions for a property
  method: GET
  name: list-transactions
  path: /v1/properties/{propertyId}/transactions
- description: Import resident transactions into Voyager
  method: POST
  name: import-transactions
  path: /v1/properties/{propertyId}/transactions
- description: Get budget data for a property
  method: GET
  name: get-budget
  path: /v1/properties/{propertyId}/budgets
- description: List all units for a property
  method: GET
  name: list-units
  path: /v1/properties/{propertyId}/units
- description: List all tenants for a property
  method: GET
  name: list-tenants
  path: /v1/properties/{propertyId}/tenants
- description: Get the chart of accounts for a property
  method: GET
  name: get-chart-of-accounts
  path: /v1/properties/{propertyId}/accounts
- description: List service requests and work orders
  method: GET
  name: list-service-requests
  path: /v1/properties/{propertyId}/service-requests
- description: Submit new service requests to Voyager
  method: POST
  name: import-service-requests
  path: /v1/properties/{propertyId}/service-requests
- description: List vendor invoices for a property
  method: GET
  name: list-vendor-invoices
  path: /v1/properties/{propertyId}/vendor-invoices
- description: Import vendor invoices into accounts payable
  method: POST
  name: import-vendor-invoices
  path: /v1/properties/{propertyId}/vendor-invoices
- description: Get job cost data for a project
  method: GET
  name: get-job-costs
  path: /v1/properties/{propertyId}/job-costs
personas: []
provider_name: Yardi
provider_slug: yardi
search_terms:
- retrieve resident billing and payment transactions for a property
- commercial real estate
- list service requests
- budget data and financial planning
- list property units
- get budget data for a property
- residential
- construction and renovation project financials
- list vendor invoices for a property
- retrieve maintenance work orders and service requests
- import resident transactions into voyager
- import vendor invoices
- tenant records and lease information
- property management
- coworking
- self storage
- retrieve construction project cost tracking data
- list vendor invoices
- maintenance
- accounting
- list service requests and work orders
- billing
- get the chart of accounts for a property
- investment management
- real estate
- list resident transactions
- retrieve vendor invoices and accounts payable data
- maintenance work orders and service requests
- list all tenants for a property
- list all units for a property
- import vendor invoices into accounts payable
- get budget data
- chart of accounts for property financials
- submit vendor invoices to accounts payable
- list tenants
- submit service requests
- list units
- get chart of accounts
- get budget
- import service requests
- resident billing and payment transactions
- vendor invoices and accounts payable
- get job cost data
- list all units in a property with occupancy and market rent
- senior living
- get job cost data for a project
- list resident transactions for a property
- leasing
- retrieve chart of accounts for property financial reporting
- import transactions
- yardi
- submit new service requests to voyager
- list transactions
- get job costs
- unit inventory and configuration
- create new maintenance service requests in voyager
- retrieve budget and actual financial data for a property
- retrieve tenant records, lease details, and contact information
- multifamily
slug: property-management
source_filename: property-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Yardi Property Management\n  description: Unified capability combining Yardi Voyager's property management operations for property managers and operations\n    teams. Enables tenant management, billing, maintenance tracking, and financial reporting across real estate portfolios.\n  tags:\n  - Accounting\n  - Billing\n  - Leasing\n  - Maintenance\n  - Property Management\n  - Real Estate\n  - Yardi\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    YARDI_USERNAME: YARDI_USERNAME\n    YARDI_PASSWORD: YARDI_PASSWORD\n    YARDI_SERVER_NAME: YARDI_SERVER_NAME\n    YARDI_DATABASE: YARDI_DATABASE\n    YARDI_INTERFACE_ENTITY: YARDI_INTERFACE_ENTITY\n    YARDI_INTERFACE_LICENSE: YARDI_INTERFACE_LICENSE\ncapability:\n  consumes:\n  - type: http\n    namespace: yardi-voyager\n    baseUri: https://www.yardiasp13.yardi.com/{clientUrl}/webservices\n    description: Yardi Voyager SOAP web services for property\
  \ management\n    authentication:\n      type: basic\n      username: '{{YARDI_USERNAME}}'\n      password: '{{YARDI_PASSWORD}}'\n    resources:\n    - name: billing-and-payments\n      path: /ItfResidentTransactions20.asmx\n      description: Resident transaction and billing operations\n      operations:\n      - name: get-resident-transactions\n        method: POST\n        description: Retrieve resident transaction records for a property and date range\n        inputParameters:\n        - name: YardiPropertyId\n          in: body\n          type: string\n          required: true\n          description: Yardi property identifier\n        - name: FromDate\n          in: body\n          type: string\n          required: false\n          description: Start date for transaction query (YYYY-MM-DD)\n        - name: ToDate\n          in: body\n          type: string\n          required: false\n          description: End date for transaction query (YYYY-MM-DD)\n        outputRawFormat: xml\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-resident-transactions-by-charge-date\n        method: POST\n        description: Retrieve resident transactions filtered by charge date\n        inputParameters:\n        - name: YardiPropertyId\n          in: body\n          type: string\n          required: true\n          description: Yardi property identifier\n        - name: ChargeFromDate\n          in: body\n          type: string\n          required: false\n          description: Start charge date\n        - name: ChargeToDate\n          in: body\n          type: string\n          required: false\n          description: End charge date\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: import-resident-transactions\n        method: POST\n        description: Import resident transactions into Voyager\n        inputParameters:\n\
  \        - name: YardiPropertyId\n          in: body\n          type: string\n          required: true\n          description: Yardi property identifier\n        - name: TransactionXml\n          in: body\n          type: string\n          required: true\n          description: XML payload containing transaction data\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-budget-data\n        method: POST\n        description: Retrieve budget data for a property\n        inputParameters:\n        - name: YardiPropertyId\n          in: body\n          type: string\n          required: true\n          description: Yardi property identifier\n        - name: BudgetName\n          in: body\n          type: string\n          required: false\n          description: Budget name\n        - name: FiscalYear\n          in: body\n          type: string\n          required: false\n          description: Fiscal\
  \ year\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: common-data\n      path: /ItfCommonData.asmx\n      description: Property, unit, tenant, and chart of accounts data\n      operations:\n      - name: get-property-configurations\n        method: POST\n        description: Retrieve property configuration data\n        inputParameters:\n        - name: YardiPropertyId\n          in: body\n          type: string\n          required: true\n          description: Yardi property identifier\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-unit-information\n        method: POST\n        description: Retrieve unit information for a property\n        inputParameters:\n        - name: YardiPropertyId\n          in: body\n          type: string\n          required: true\n          description: Yardi property identifier\n\
  \        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-tenants\n        method: POST\n        description: Retrieve tenant records for a property\n        inputParameters:\n        - name: YardiPropertyId\n          in: body\n          type: string\n          required: true\n          description: Yardi property identifier\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-chart-of-accounts\n        method: POST\n        description: Retrieve chart of accounts for a property\n        inputParameters:\n        - name: YardiPropertyId\n          in: body\n          type: string\n          required: true\n          description: Yardi property identifier\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: service-requests\n\
  \      path: /ItfServiceRequests.asmx\n      description: Maintenance work order and service request operations\n      operations:\n      - name: get-service-requests\n        method: POST\n        description: Retrieve service requests and work orders for a property\n        inputParameters:\n        - name: YardiPropertyId\n          in: body\n          type: string\n          required: true\n          description: Yardi property identifier\n        - name: FromDate\n          in: body\n          type: string\n          required: false\n          description: Start date\n        - name: ToDate\n          in: body\n          type: string\n          required: false\n          description: End date\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: import-service-requests\n        method: POST\n        description: Create or update service requests in Voyager\n        inputParameters:\n        - name:\
  \ YardiPropertyId\n          in: body\n          type: string\n          required: true\n          description: Yardi property identifier\n        - name: ServiceRequestXml\n          in: body\n          type: string\n          required: true\n          description: XML payload containing service request data\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vendor-invoicing\n      path: /ItfVendorInvoice.asmx\n      description: Vendor invoice and accounts payable operations\n      operations:\n      - name: get-vendor-invoices\n        method: POST\n        description: Retrieve vendor invoice records\n        inputParameters:\n        - name: YardiPropertyId\n          in: body\n          type: string\n          required: true\n          description: Yardi property identifier\n        - name: FromDate\n          in: body\n          type: string\n          required: false\n          description:\
  \ Start date\n        - name: ToDate\n          in: body\n          type: string\n          required: false\n          description: End date\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: import-vendor-invoices\n        method: POST\n        description: Import vendor invoices into Voyager accounts payable\n        inputParameters:\n        - name: YardiPropertyId\n          in: body\n          type: string\n          required: true\n          description: Yardi property identifier\n        - name: InvoiceXml\n          in: body\n          type: string\n          required: true\n          description: XML payload containing vendor invoice data\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-cost\n      path: /ItfJobCost.asmx\n      description: Job cost tracking and construction project financials\n\
  \      operations:\n      - name: get-job-cost-data\n        method: POST\n        description: Retrieve job cost tracking data for a project\n        inputParameters:\n        - name: YardiPropertyId\n          in: body\n          type: string\n          required: true\n          description: Yardi property identifier\n        - name: JobId\n          in: body\n          type: string\n          required: false\n          description: Job or project identifier\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: yardi-property-management-api\n    description: Unified REST API for Yardi property management operations.\n    resources:\n    - path: /v1/properties/{propertyId}/transactions\n      name: transactions\n      description: Resident billing and payment transactions\n      operations:\n      - method: GET\n        name: list-transactions\n        description:\
  \ List resident transactions for a property\n        call: yardi-voyager.get-resident-transactions\n        with:\n          YardiPropertyId: rest.propertyId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: import-transactions\n        description: Import resident transactions into Voyager\n        call: yardi-voyager.import-resident-transactions\n        with:\n          YardiPropertyId: rest.propertyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/properties/{propertyId}/budgets\n      name: budgets\n      description: Budget data and financial planning\n      operations:\n      - method: GET\n        name: get-budget\n        description: Get budget data for a property\n        call: yardi-voyager.get-budget-data\n        with:\n          YardiPropertyId: rest.propertyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/properties/{propertyId}/units\n\
  \      name: units\n      description: Unit inventory and configuration\n      operations:\n      - method: GET\n        name: list-units\n        description: List all units for a property\n        call: yardi-voyager.get-unit-information\n        with:\n          YardiPropertyId: rest.propertyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/properties/{propertyId}/tenants\n      name: tenants\n      description: Tenant records and lease information\n      operations:\n      - method: GET\n        name: list-tenants\n        description: List all tenants for a property\n        call: yardi-voyager.get-tenants\n        with:\n          YardiPropertyId: rest.propertyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/properties/{propertyId}/accounts\n      name: chart-of-accounts\n      description: Chart of accounts for property financials\n      operations:\n      - method: GET\n        name: get-chart-of-accounts\n\
  \        description: Get the chart of accounts for a property\n        call: yardi-voyager.get-chart-of-accounts\n        with:\n          YardiPropertyId: rest.propertyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/properties/{propertyId}/service-requests\n      name: service-requests\n      description: Maintenance work orders and service requests\n      operations:\n      - method: GET\n        name: list-service-requests\n        description: List service requests and work orders\n        call: yardi-voyager.get-service-requests\n        with:\n          YardiPropertyId: rest.propertyId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: import-service-requests\n        description: Submit new service requests to Voyager\n        call: yardi-voyager.import-service-requests\n        with:\n          YardiPropertyId: rest.propertyId\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/properties/{propertyId}/vendor-invoices\n      name: vendor-invoices\n      description: Vendor invoices and accounts payable\n      operations:\n      - method: GET\n        name: list-vendor-invoices\n        description: List vendor invoices for a property\n        call: yardi-voyager.get-vendor-invoices\n        with:\n          YardiPropertyId: rest.propertyId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: import-vendor-invoices\n        description: Import vendor invoices into accounts payable\n        call: yardi-voyager.import-vendor-invoices\n        with:\n          YardiPropertyId: rest.propertyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/properties/{propertyId}/job-costs\n      name: job-costs\n      description: Construction and renovation project financials\n      operations:\n      - method: GET\n        name: get-job-costs\n\
  \        description: Get job cost data for a project\n        call: yardi-voyager.get-job-cost-data\n        with:\n          YardiPropertyId: rest.propertyId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: yardi-property-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Yardi property management workflows.\n    tools:\n    - name: list-resident-transactions\n      description: Retrieve resident billing and payment transactions for a property\n      hints:\n        readOnly: true\n        openWorld: true\n      call: yardi-voyager.get-resident-transactions\n      with:\n        YardiPropertyId: tools.property_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-budget-data\n      description: Retrieve budget and actual financial data for a property\n      hints:\n        readOnly: true\n      call: yardi-voyager.get-budget-data\n      with:\n     \
  \   YardiPropertyId: tools.property_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-property-units\n      description: List all units in a property with occupancy and market rent\n      hints:\n        readOnly: true\n        openWorld: true\n      call: yardi-voyager.get-unit-information\n      with:\n        YardiPropertyId: tools.property_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tenants\n      description: Retrieve tenant records, lease details, and contact information\n      hints:\n        readOnly: true\n        openWorld: true\n      call: yardi-voyager.get-tenants\n      with:\n        YardiPropertyId: tools.property_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-chart-of-accounts\n      description: Retrieve chart of accounts for property financial reporting\n      hints:\n        readOnly: true\n      call: yardi-voyager.get-chart-of-accounts\n   \
  \   with:\n        YardiPropertyId: tools.property_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-service-requests\n      description: Retrieve maintenance work orders and service requests\n      hints:\n        readOnly: true\n        openWorld: true\n      call: yardi-voyager.get-service-requests\n      with:\n        YardiPropertyId: tools.property_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-service-requests\n      description: Create new maintenance service requests in Voyager\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: yardi-voyager.import-service-requests\n      with:\n        YardiPropertyId: tools.property_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-vendor-invoices\n      description: Retrieve vendor invoices and accounts payable data\n      hints:\n        readOnly: true\n        openWorld:\
  \ true\n      call: yardi-voyager.get-vendor-invoices\n      with:\n        YardiPropertyId: tools.property_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: import-vendor-invoices\n      description: Submit vendor invoices to accounts payable\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: yardi-voyager.import-vendor-invoices\n      with:\n        YardiPropertyId: tools.property_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-job-cost-data\n      description: Retrieve construction project cost tracking data\n      hints:\n        readOnly: true\n      call: yardi-voyager.get-job-cost-data\n      with:\n        YardiPropertyId: tools.property_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/yardi/refs/heads/main/capabilities/property-management.yaml
tags:
- Accounting
- Billing
- Leasing
- Maintenance
- Property Management
- Real Estate
- Yardi
tools:
- description: Retrieve resident billing and payment transactions for a property
  hints:
    openWorld: true
    readOnly: true
  name: list-resident-transactions
- description: Retrieve budget and actual financial data for a property
  hints:
    readOnly: true
  name: get-budget-data
- description: List all units in a property with occupancy and market rent
  hints:
    openWorld: true
    readOnly: true
  name: list-property-units
- description: Retrieve tenant records, lease details, and contact information
  hints:
    openWorld: true
    readOnly: true
  name: list-tenants
- description: Retrieve chart of accounts for property financial reporting
  hints:
    readOnly: true
  name: get-chart-of-accounts
- description: Retrieve maintenance work orders and service requests
  hints:
    openWorld: true
    readOnly: true
  name: list-service-requests
- description: Create new maintenance service requests in Voyager
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submit-service-requests
- description: Retrieve vendor invoices and accounts payable data
  hints:
    openWorld: true
    readOnly: true
  name: list-vendor-invoices
- description: Submit vendor invoices to accounts payable
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: import-vendor-invoices
- description: Retrieve construction project cost tracking data
  hints:
    readOnly: true
  name: get-job-cost-data
---
