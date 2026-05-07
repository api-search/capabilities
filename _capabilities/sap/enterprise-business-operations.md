---
categories:
- machine-learning
consumed_apis: []
description: Unified workflow combining SAP Business One, S/4HANA Cloud Business Partner, and AI Core APIs for managing business partners, orders, financials, and AI-driven automation across SAP ERP systems.
layout: capability
name: SAP Enterprise Business Operations
operations:
- description: List business partners from SAP Business One
  method: GET
  name: list-b1-business-partners
  path: /v1/business-partners
- description: Create a business partner in SAP Business One
  method: POST
  name: create-b1-business-partner
  path: /v1/business-partners
- description: Get a specific business partner from SAP Business One
  method: GET
  name: get-b1-business-partner
  path: /v1/business-partners/{id}
- description: Update a business partner in SAP Business One
  method: PATCH
  name: update-b1-business-partner
  path: /v1/business-partners/{id}
- description: List business partners from S/4HANA Cloud
  method: GET
  name: list-s4hana-business-partners
  path: /v1/s4hana-business-partners
- description: Create a business partner in S/4HANA Cloud
  method: POST
  name: create-s4hana-business-partner
  path: /v1/s4hana-business-partners
- description: List sales orders from Business One
  method: GET
  name: list-orders
  path: /v1/orders
- description: Create a sales order in Business One
  method: POST
  name: create-order
  path: /v1/orders
- description: List items from Business One
  method: GET
  name: list-items
  path: /v1/items
- description: List invoices from Business One
  method: GET
  name: list-invoices
  path: /v1/invoices
- description: Create an invoice in Business One
  method: POST
  name: create-invoice
  path: /v1/invoices
- description: List journal entries from Business One
  method: GET
  name: list-journal-entries
  path: /v1/journal-entries
- description: Create a journal entry in Business One
  method: POST
  name: create-journal-entry
  path: /v1/journal-entries
- description: List business partner addresses from S/4HANA
  method: GET
  name: list-addresses
  path: /v1/addresses
- description: List AI scenarios from AI Core
  method: GET
  name: list-scenarios
  path: /v1/scenarios
- description: List AI executions
  method: GET
  name: list-executions
  path: /v1/executions
- description: Create an AI execution
  method: POST
  name: create-execution
  path: /v1/executions
- description: List AI deployments
  method: GET
  name: list-deployments
  path: /v1/deployments
- description: Create an AI deployment
  method: POST
  name: create-deployment
  path: /v1/deployments
personas: []
provider_name: SAP
provider_slug: sap
search_terms:
- ai delete execution
- s4hana list business partners
- ai list deployments
- get a specific business partner from s/4hana cloud
- list items
- list ai deployments
- business one business partner management
- update b1 business partner
- create an accounts receivable invoice in sap business one
- create an invoice in business one
- get details of a specific ai execution
- stop a running ai execution
- b1 create invoice
- list orders
- get a specific business partner from sap business one
- financial journal entries
- b1 list invoices
- create an ai model deployment in sap ai core
- b1 create journal entry
- create deployment
- ai list configurations
- list b1 business partners
- s/4hana business partner addresses
- ai create execution
- ai create configuration
- create execution
- ai
- list business partner tax numbers from s/4hana cloud
- list ai scenarios from sap ai core
- list financial journal entries from sap business one
- sales order management
- ai execution management
- b1 list journal entries
- create a business partner in s/4hana cloud
- data management
- list s4hana business partners
- sap
- update a business partner in sap business one
- list business partner bank accounts from s/4hana cloud
- s4hana list addresses
- create a financial journal entry in sap business one
- s4hana list bank accounts
- enterprise
- list invoices from business one
- ai deployment management
- list ai configurations from sap ai core
- cloud
- create a sales order in business one
- list sales orders from sap business one
- trigger an ai training execution in sap ai core
- list ai artifacts (models, datasets) from sap ai core
- erp
- list business partners from sap business one
- create b1 business partner
- list item master data from sap business one
- b1 create business partner
- list deployments
- list business partner roles from s/4hana cloud
- update a business partner in s/4hana cloud
- get b1 business partner
- create a business partner in sap business one
- create an ai deployment
- ai create deployment
- business one business partner detail
- list ai training executions from sap ai core
- b1 create order
- integration
- business operations
- ai scenario management
- create invoice
- list business partner addresses from s/4hana cloud
- list scenarios
- list journal entries
- create a sales order in sap business one
- s4hana create business partner
- list ai model deployments from sap ai core
- ai get execution
- list ai executions
- list invoices
- ai list executions
- create a journal entry in business one
- b1 get business partner
- create an ai execution
- s4hana get business partner
- list journal entries from business one
- invoice management
- list business partner master records from s/4hana cloud
- b1 list items
- create order
- list items from business one
- list accounts receivable invoices from sap business one
- list business partner addresses from s/4hana
- b1 update business partner
- ai list scenarios
- ai list artifacts
- business applications
- b1 list business partners
- list business partners from s/4hana cloud
- btp
- register a new ai artifact in sap ai core
- list ai scenarios from ai core
- s/4hana cloud business partner master data
- create s4hana business partner
- item master data
- s4hana update business partner
- create journal entry
- list executions
- s4hana list roles
- s4hana list tax numbers
- list sales orders from business one
- list addresses
- ai create artifact
- create an ai configuration in sap ai core
- b1 list orders
slug: enterprise-business-operations
source_filename: enterprise-business-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SAP Enterprise Business Operations\n  description: Unified workflow combining SAP Business One, S/4HANA Cloud Business Partner, and AI Core APIs for managing\n    business partners, orders, financials, and AI-driven automation across SAP ERP systems.\n  tags:\n  - SAP\n  - Enterprise\n  - ERP\n  - AI\n  - Business Operations\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SAP_AI_CORE_OAUTH_TOKEN: SAP_AI_CORE_OAUTH_TOKEN\n    SAP_B1_USERNAME: SAP_B1_USERNAME\n    SAP_B1_PASSWORD: SAP_B1_PASSWORD\n    SAP_B1_COMPANY_DB: SAP_B1_COMPANY_DB\n    SAP_S4HANA_USERNAME: SAP_S4HANA_USERNAME\n    SAP_S4HANA_PASSWORD: SAP_S4HANA_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: sap-ai-core\n    baseUri: https://api.ai.eu10.cfapps.hana.hana.ondemand.com/v2\n    description: SAP AI Core API for scenario management, execution orchestration, model serving, and artifact tracking.\n    authentication:\n\
  \      type: bearer\n      token: '{{SAP_AI_CORE_OAUTH_TOKEN}}'\n    resources:\n    - name: scenarios\n      path: /lm/scenarios\n      description: AI scenario definitions and metadata\n      operations:\n      - name: list-scenarios\n        method: GET\n        description: Retrieves all AI scenarios available in the resource group.\n        inputParameters:\n        - name: AI-Resource-Group\n          in: header\n          type: string\n          required: true\n          description: The resource group for multi-tenancy isolation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-scenario-versions\n        method: GET\n        path: /{scenarioId}/versions\n        description: Retrieves all versions for a specific AI scenario.\n        inputParameters:\n        - name: scenarioId\n          in: path\n          type: string\n          required: true\n          description: Scenario identifier\n\
  \        - name: AI-Resource-Group\n          in: header\n          type: string\n          required: true\n          description: The resource group for multi-tenancy isolation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: configurations\n      path: /lm/configurations\n      description: Execution and deployment configurations\n      operations:\n      - name: list-configurations\n        method: GET\n        description: Retrieves all configurations for executions and deployments.\n        inputParameters:\n        - name: AI-Resource-Group\n          in: header\n          type: string\n          required: true\n          description: The resource group for multi-tenancy isolation\n        - name: scenarioId\n          in: query\n          type: string\n          required: false\n          description: Filter by scenario ID\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n      - name: create-configuration\n        method: POST\n        description: Creates a new configuration for an execution or deployment.\n        inputParameters:\n        - name: AI-Resource-Group\n          in: header\n          type: string\n          required: true\n          description: The resource group for multi-tenancy isolation\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            scenarioId: '{{tools.scenarioId}}'\n            executableId: '{{tools.executableId}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: executions\n      path: /lm/executions\n      description: Training execution lifecycle management\n      operations:\n      - name: list-executions\n        method: GET\n        description: Retrieves all training executions in the resource group.\n        inputParameters:\n\
  \        - name: AI-Resource-Group\n          in: header\n          type: string\n          required: true\n          description: The resource group for multi-tenancy isolation\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by execution status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-execution\n        method: POST\n        description: Triggers a new training execution using a configuration.\n        inputParameters:\n        - name: AI-Resource-Group\n          in: header\n          type: string\n          required: true\n          description: The resource group for multi-tenancy isolation\n        body:\n          type: json\n          data:\n            configurationId: '{{tools.configurationId}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: get-execution\n        method: GET\n        path: /{executionId}\n        description: Retrieves details of a specific training execution.\n        inputParameters:\n        - name: executionId\n          in: path\n          type: string\n          required: true\n          description: Execution identifier\n        - name: AI-Resource-Group\n          in: header\n          type: string\n          required: true\n          description: The resource group for multi-tenancy isolation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-execution\n        method: DELETE\n        path: /{executionId}\n        description: Stops a running execution or marks it for deletion.\n        inputParameters:\n        - name: executionId\n          in: path\n          type: string\n          required: true\n          description: Execution identifier\n        -\
  \ name: AI-Resource-Group\n          in: header\n          type: string\n          required: true\n          description: The resource group for multi-tenancy isolation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployments\n      path: /lm/deployments\n      description: Model deployment and serving management\n      operations:\n      - name: list-deployments\n        method: GET\n        description: Retrieves all model deployments in the resource group.\n        inputParameters:\n        - name: AI-Resource-Group\n          in: header\n          type: string\n          required: true\n          description: The resource group for multi-tenancy isolation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-deployment\n        method: POST\n        description: Creates a new model deployment for\
  \ serving predictions.\n        inputParameters:\n        - name: AI-Resource-Group\n          in: header\n          type: string\n          required: true\n          description: The resource group for multi-tenancy isolation\n        body:\n          type: json\n          data:\n            configurationId: '{{tools.configurationId}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: artifacts\n      path: /lm/artifacts\n      description: Model artifacts and dataset management\n      operations:\n      - name: list-artifacts\n        method: GET\n        description: Retrieves all artifacts (models, datasets) in the resource group.\n        inputParameters:\n        - name: AI-Resource-Group\n          in: header\n          type: string\n          required: true\n          description: The resource group for multi-tenancy isolation\n        outputRawFormat: json\n        outputParameters:\n   \
  \     - name: result\n          type: object\n          value: $.\n      - name: create-artifact\n        method: POST\n        description: Registers a new artifact (model or dataset) for use in executions and deployments.\n        inputParameters:\n        - name: AI-Resource-Group\n          in: header\n          type: string\n          required: true\n          description: The resource group for multi-tenancy isolation\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            kind: '{{tools.kind}}'\n            url: '{{tools.url}}'\n            scenarioId: '{{tools.scenarioId}}'\n            description: '{{tools.description}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: sap-business-one\n    baseUri: https://localhost:50000/b1s/v1\n    description: SAP Business One Service Layer for CRUD operations on business objects.\n \
  \   authentication:\n      type: apikey\n      key: B1SESSION\n      value: '{{SAP_B1_SESSION}}'\n      placement: cookie\n    resources:\n    - name: authentication\n      path: /\n      description: Login and session management\n      operations:\n      - name: login\n        method: POST\n        path: /Login\n        description: Authenticates a user and returns a session cookie.\n        body:\n          type: json\n          data:\n            CompanyDB: '{{tools.companyDB}}'\n            UserName: '{{tools.userName}}'\n            Password: '{{tools.password}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: logout\n        method: POST\n        path: /Logout\n        description: Terminates the current authenticated session.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: business-partners\n   \
  \   path: /BusinessPartners\n      description: Manage customers, vendors, and leads\n      operations:\n      - name: list-business-partners\n        method: GET\n        description: Retrieves a list of business partners.\n        inputParameters:\n        - name: $select\n          in: query\n          type: string\n          required: false\n          description: Fields to include in the response\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter expression\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of records\n        - name: $skip\n          in: query\n          type: integer\n          required: false\n          description: Number of records to skip\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-business-partner\n\
  \        method: POST\n        description: Creates a new business partner record.\n        body:\n          type: json\n          data:\n            CardCode: '{{tools.cardCode}}'\n            CardName: '{{tools.cardName}}'\n            CardType: '{{tools.cardType}}'\n            EmailAddress: '{{tools.emailAddress}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-business-partner\n        method: GET\n        path: /('{CardCode}')\n        description: Retrieves a specific business partner by card code.\n        inputParameters:\n        - name: CardCode\n          in: path\n          type: string\n          required: true\n          description: The unique card code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-business-partner\n        method: PATCH\n        path: /('{CardCode}')\n \
  \       description: Updates an existing business partner record.\n        inputParameters:\n        - name: CardCode\n          in: path\n          type: string\n          required: true\n          description: The unique card code\n        body:\n          type: json\n          data:\n            CardName: '{{tools.cardName}}'\n            EmailAddress: '{{tools.emailAddress}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders\n      path: /Orders\n      description: Sales orders management\n      operations:\n      - name: list-orders\n        method: GET\n        description: Retrieves a list of sales orders.\n        inputParameters:\n        - name: $select\n          in: query\n          type: string\n          required: false\n          description: Fields to include\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description:\
  \ OData filter expression\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of records\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-order\n        method: POST\n        description: Creates a new sales order with line items.\n        body:\n          type: json\n          data:\n            CardCode: '{{tools.cardCode}}'\n            DocDate: '{{tools.docDate}}'\n            DocumentLines: '{{tools.documentLines}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: items\n      path: /Items\n      description: Product and item master data\n      operations:\n      - name: list-items\n        method: GET\n        description: Retrieves the item master data list.\n        inputParameters:\n        - name: $select\n\
  \          in: query\n          type: string\n          required: false\n          description: Fields to include\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter expression\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of records\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: journal-entries\n      path: /JournalEntries\n      description: Financial journal entries and postings\n      operations:\n      - name: list-journal-entries\n        method: GET\n        description: Retrieves financial journal entries.\n        inputParameters:\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter expression\n        - name: $top\n          in: query\n \
  \         type: integer\n          required: false\n          description: Maximum number of records\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-journal-entry\n        method: POST\n        description: Creates a new financial journal entry.\n        body:\n          type: json\n          data:\n            ReferenceDate: '{{tools.referenceDate}}'\n            Memo: '{{tools.memo}}'\n            JournalEntryLines: '{{tools.journalEntryLines}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invoices\n      path: /Invoices\n      description: AR and AP invoice management\n      operations:\n      - name: list-invoices\n        method: GET\n        description: Retrieves accounts receivable invoices.\n        inputParameters:\n        - name: $filter\n          in: query\n          type: string\n\
  \          required: false\n          description: OData filter expression\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of records\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-invoice\n        method: POST\n        description: Creates a new accounts receivable invoice.\n        body:\n          type: json\n          data:\n            CardCode: '{{tools.cardCode}}'\n            DocDate: '{{tools.docDate}}'\n            DocumentLines: '{{tools.documentLines}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: sap-s4hana-bp\n    baseUri: https://sandbox.api.sap.com/sap/opu/odata/sap/API_BUSINESS_PARTNER\n    description: SAP S/4HANA Cloud Business Partner OData API for master data management.\n\
  \    authentication:\n      type: basic\n      username: '{{SAP_S4HANA_USERNAME}}'\n      password: '{{SAP_S4HANA_PASSWORD}}'\n    resources:\n    - name: business-partners\n      path: /A_BusinessPartner\n      description: Business partner header data and general information\n      operations:\n      - name: list-business-partners\n        method: GET\n        description: Retrieves a collection of business partner master records.\n        inputParameters:\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of entries to return\n        - name: $skip\n          in: query\n          type: integer\n          required: false\n          description: Number of entries to skip\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter expression\n        - name: $select\n          in: query\n          type: string\n          required:\
  \ false\n          description: Properties to return\n        - name: $orderby\n          in: query\n          type: string\n          required: false\n          description: OData sort expression\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-business-partner\n        method: POST\n        description: Creates a new business partner master record.\n        body:\n          type: json\n          data:\n            BusinessPartnerFullName: '{{tools.fullName}}'\n            BusinessPartnerCategory: '{{tools.category}}'\n            FirstName: '{{tools.firstName}}'\n            LastName: '{{tools.lastName}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-business-partner\n        method: GET\n        path: /('{BusinessPartner}')\n        description: Retrieves a single business partner by its\
  \ key.\n        inputParameters:\n        - name: BusinessPartner\n          in: path\n          type: string\n          required: true\n          description: Business partner number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-business-partner\n        method: PATCH\n        path: /('{BusinessPartner}')\n        description: Updates fields of an existing business partner record.\n        inputParameters:\n        - name: BusinessPartner\n          in: path\n          type: string\n          required: true\n          description: Business partner number\n        body:\n          type: json\n          data:\n            BusinessPartnerFullName: '{{tools.fullName}}'\n            FirstName: '{{tools.firstName}}'\n            LastName: '{{tools.lastName}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n   \
  \ - name: addresses\n      path: /A_BusinessPartnerAddress\n      description: Business partner address management\n      operations:\n      - name: list-addresses\n        method: GET\n        description: Retrieves address records associated with business partners.\n        inputParameters:\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of entries\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter expression\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bank-accounts\n      path: /A_BusinessPartnerBank\n      description: Business partner bank account details\n      operations:\n      - name: list-bank-accounts\n        method: GET\n        description: Retrieves bank account records for business partners.\n        inputParameters:\n\
  \        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of entries\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter expression\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: roles\n      path: /A_BusinessPartnerRole\n      description: Business partner role assignments\n      operations:\n      - name: list-roles\n        method: GET\n        description: Retrieves role assignments for business partners.\n        inputParameters:\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of entries\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter expression\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tax-numbers\n      path: /A_BusinessPartnerTaxNumber\n      description: Business partner tax identification numbers\n      operations:\n      - name: list-tax-numbers\n        method: GET\n        description: Retrieves tax identification numbers for business partners.\n        inputParameters:\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of entries\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter expression\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sap-enterprise-ops-api\n    description: Unified REST API for SAP enterprise business operations spanning ERP,\
  \ master data, and AI workflows.\n    resources:\n    - path: /v1/business-partners\n      name: b1-business-partners\n      description: Business One business partner management\n      operations:\n      - method: GET\n        name: list-b1-business-partners\n        description: List business partners from SAP Business One\n        call: sap-business-one.list-business-partners\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-b1-business-partner\n        description: Create a business partner in SAP Business One\n        call: sap-business-one.create-business-partner\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/business-partners/{id}\n      name: b1-business-partner-detail\n      description: Business One business partner detail\n      operations:\n      - method: GET\n        name: get-b1-business-partner\n        description: Get a specific business partner from SAP Business\
  \ One\n        call: sap-business-one.get-business-partner\n        with:\n          CardCode: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-b1-business-partner\n        description: Update a business partner in SAP Business One\n        call: sap-business-one.update-business-partner\n        with:\n          CardCode: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/s4hana-business-partners\n      name: s4hana-business-partners\n      description: S/4HANA Cloud business partner master data\n      operations:\n      - method: GET\n        name: list-s4hana-business-partners\n        description: List business partners from S/4HANA Cloud\n        call: sap-s4hana-bp.list-business-partners\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-s4hana-business-partner\n        description: Create a\
  \ business partner in S/4HANA Cloud\n        call: sap-s4hana-bp.create-business-partner\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders\n      name: orders\n      description: Sales order management\n      operations:\n      - method: GET\n        name: list-orders\n        description: List sales orders from Business One\n        call: sap-business-one.list-orders\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-order\n        description: Create a sales order in Business One\n        call: sap-business-one.create-order\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/items\n      name: items\n      description: Item master data\n      operations:\n      - method: GET\n        name: list-items\n        description: List items from Business One\n        call: sap-business-one.list-items\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /v1/invoices\n      name: invoices\n      description: Invoice management\n      operations:\n      - method: GET\n        name: list-invoices\n        description: List invoices from Business One\n        call: sap-business-one.list-invoices\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-invoice\n        description: Create an invoice in Business One\n        call: sap-business-one.create-invoice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/journal-entries\n      name: journal-entries\n      description: Financial journal entries\n      operations:\n      - method: GET\n        name: list-journal-entries\n        description: List journal entries from Business One\n        call: sap-business-one.list-journal-entries\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name:\
  \ create-journal-entry\n        description: Create a journal entry in Business One\n        call: sap-business-one.create-journal-entry\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/addresses\n      name: addresses\n      description: S/4HANA business partner addresses\n      operations:\n      - method: GET\n        name: list-addresses\n        description: List business partner addresses from S/4HANA\n        call: sap-s4hana-bp.list-addresses\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/scenarios\n      name: ai-scenarios\n      description: AI scenario management\n      operations:\n      - method: GET\n        name: list-scenarios\n        description: List AI scenarios from AI Core\n        call: sap-ai-core.list-scenarios\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/executions\n      name: ai-executions\n      description: AI execution management\n\
  \      operations:\n      - method: GET\n        name: list-executions\n        description: List AI executions\n        call: sap-ai-core.list-executions\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-execution\n        description: Create an AI execution\n        call: sap-ai-core.create-execution\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/deployments\n      name: ai-deployments\n      description: AI deployment management\n      operations:\n      - method: GET\n        name: list-deployments\n        description: List AI deployments\n        call: sap-ai-core.list-deployments\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-deployment\n        description: Create an AI deployment\n        call: sap-ai-core.create-deployment\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \  - type: mcp\n    port: 9090\n    namespace: sap-enterprise-ops-mcp\n    transport: http\n    description: MCP server for AI-assisted SAP enterprise business operations across ERP, master data, and AI workflows.\n    tools:\n    - name: b1-list-business-partners\n      description: List business partners from SAP Business One\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sap-business-one.list-business-partners\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: b1-create-business-partner\n      description: Create a business partner in SAP Business One\n      hints:\n        readOnly: false\n      call: sap-business-one.create-business-partner\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: b1-get-business-partner\n      description: Get a specific business partner from SAP Business One\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sap-business-one.get-business-partner\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: b1-update-business-partner\n      description: Update a business partner in SAP Business One\n      hints:\n        readOnly: false\n        idempotent: true\n      call: sap-business-one.update-business-partner\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: b1-list-orders\n      description: List sales orders from SAP Business One\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sap-business-one.list-orders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: b1-create-order\n      description: Create a sales order in SAP Business One\n      hints:\n        readOnly: false\n      call: sap-business-one.create-order\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: b1-list-items\n      description: List item master data from SAP Business One\n      hints:\n        readOnly: true\n       \
  \ openWorld: true\n      call: sap-business-one.list-items\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: b1-list-journal-entries\n      description: List financial journal entries from SAP Business One\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sap-business-one.list-journal-entries\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: b1-create-journal-entry\n      description: Create a financial journal entry in SAP Business One\n      hints:\n        readOnly: false\n      call: sap-business-one.create-journal-entry\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: b1-list-invoices\n      description: List accounts receivable invoices from SAP Business One\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sap-business-one.list-invoices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: b1-create-invoice\n\
  \      description: Create an accounts receivable invoice in SAP Business One\n      hints:\n        readOnly: false\n      call: sap-business-one.create-invoice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: s4hana-list-business-partners\n      description: List business partner master records from S/4HANA Cloud\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sap-s4hana-bp.list-business-partners\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: s4hana-create-business-partner\n      description: Create a business partner in S/4HANA Cloud\n      hints:\n        readOnly: false\n      call: sap-s4hana-bp.create-business-partner\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: s4hana-get-business-partner\n      description: Get a specific business partner from S/4HANA Cloud\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sap-s4hana-bp.get-business-partner\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: s4hana-update-business-partner\n      description: Update a business partner in S/4HANA Cloud\n      hints:\n        readOnly: false\n        idempotent: true\n      call: sap-s4hana-bp.update-business-partner\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: s4hana-list-addresses\n      description: List business partner addresses from S/4HANA Cloud\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sap-s4hana-bp.list-addresses\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: s4hana-list-bank-accounts\n      description: List business partner bank accounts from S/4HANA Cloud\n      hints:\n        readOnl\n\n# --- truncated at 32 KB (35 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/sap/refs/heads/main/capabilities/enterprise-business-operations.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sap/refs/heads/main/capabilities/enterprise-business-operations.yaml
tags:
- SAP
- Enterprise
- ERP
- AI
- Business Operations
tools:
- description: List business partners from SAP Business One
  hints:
    openWorld: true
    readOnly: true
  name: b1-list-business-partners
- description: Create a business partner in SAP Business One
  hints:
    readOnly: false
  name: b1-create-business-partner
- description: Get a specific business partner from SAP Business One
  hints:
    openWorld: true
    readOnly: true
  name: b1-get-business-partner
- description: Update a business partner in SAP Business One
  hints:
    idempotent: true
    readOnly: false
  name: b1-update-business-partner
- description: List sales orders from SAP Business One
  hints:
    openWorld: true
    readOnly: true
  name: b1-list-orders
- description: Create a sales order in SAP Business One
  hints:
    readOnly: false
  name: b1-create-order
- description: List item master data from SAP Business One
  hints:
    openWorld: true
    readOnly: true
  name: b1-list-items
- description: List financial journal entries from SAP Business One
  hints:
    openWorld: true
    readOnly: true
  name: b1-list-journal-entries
- description: Create a financial journal entry in SAP Business One
  hints:
    readOnly: false
  name: b1-create-journal-entry
- description: List accounts receivable invoices from SAP Business One
  hints:
    openWorld: true
    readOnly: true
  name: b1-list-invoices
- description: Create an accounts receivable invoice in SAP Business One
  hints:
    readOnly: false
  name: b1-create-invoice
- description: List business partner master records from S/4HANA Cloud
  hints:
    openWorld: true
    readOnly: true
  name: s4hana-list-business-partners
- description: Create a business partner in S/4HANA Cloud
  hints:
    readOnly: false
  name: s4hana-create-business-partner
- description: Get a specific business partner from S/4HANA Cloud
  hints:
    openWorld: true
    readOnly: true
  name: s4hana-get-business-partner
- description: Update a business partner in S/4HANA Cloud
  hints:
    idempotent: true
    readOnly: false
  name: s4hana-update-business-partner
- description: List business partner addresses from S/4HANA Cloud
  hints:
    openWorld: true
    readOnly: true
  name: s4hana-list-addresses
- description: List business partner bank accounts from S/4HANA Cloud
  hints:
    openWorld: true
    readOnly: true
  name: s4hana-list-bank-accounts
- description: List business partner roles from S/4HANA Cloud
  hints:
    openWorld: true
    readOnly: true
  name: s4hana-list-roles
- description: List business partner tax numbers from S/4HANA Cloud
  hints:
    openWorld: true
    readOnly: true
  name: s4hana-list-tax-numbers
- description: List AI scenarios from SAP AI Core
  hints:
    openWorld: true
    readOnly: true
  name: ai-list-scenarios
- description: List AI configurations from SAP AI Core
  hints:
    openWorld: true
    readOnly: true
  name: ai-list-configurations
- description: Create an AI configuration in SAP AI Core
  hints:
    readOnly: false
  name: ai-create-configuration
- description: List AI training executions from SAP AI Core
  hints:
    openWorld: true
    readOnly: true
  name: ai-list-executions
- description: Trigger an AI training execution in SAP AI Core
  hints:
    readOnly: false
  name: ai-create-execution
- description: Get details of a specific AI execution
  hints:
    openWorld: true
    readOnly: true
  name: ai-get-execution
- description: Stop a running AI execution
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: ai-delete-execution
- description: List AI model deployments from SAP AI Core
  hints:
    openWorld: true
    readOnly: true
  name: ai-list-deployments
- description: Create an AI model deployment in SAP AI Core
  hints:
    readOnly: false
  name: ai-create-deployment
- description: List AI artifacts (models, datasets) from SAP AI Core
  hints:
    openWorld: true
    readOnly: true
  name: ai-list-artifacts
- description: Register a new AI artifact in SAP AI Core
  hints:
    readOnly: false
  name: ai-create-artifact
---
