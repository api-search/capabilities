---
categories: []
consumed_apis: []
description: Unified integration platform capability combining Truto Admin API, HRIS, ATS, and CRM unified APIs. Used by B2B SaaS engineering teams and AI agents to manage connected third-party accounts, access normalized HR/recruiting/CRM data across 250+ integrations, and provision MCP servers for AI agent access without writing integration-specific code.
layout: capability
name: Truto Unified Integrations
operations:
- description: List integrated accounts.
  method: GET
  name: list-integrated-accounts
  path: /v1/integrated-accounts
- description: Create integrated account.
  method: POST
  name: create-integrated-account
  path: /v1/integrated-accounts
- description: Create link token for customer connection flow.
  method: POST
  name: create-link-token
  path: /v1/link-tokens
- description: List employees from connected HRIS.
  method: GET
  name: list-employees
  path: /v1/hris/employees
- description: List HRIS groups.
  method: GET
  name: list-groups
  path: /v1/hris/groups
- description: List jobs from connected ATS.
  method: GET
  name: list-jobs
  path: /v1/ats/jobs
- description: List candidates from connected ATS.
  method: GET
  name: list-candidates
  path: /v1/ats/candidates
- description: List applications from connected ATS.
  method: GET
  name: list-applications
  path: /v1/ats/applications
- description: List contacts from connected CRM.
  method: GET
  name: list-contacts
  path: /v1/crm/contacts
- description: Create contact in connected CRM.
  method: POST
  name: create-contact
  path: /v1/crm/contacts
- description: List opportunities from connected CRM.
  method: GET
  name: list-opportunities
  path: /v1/crm/opportunities
personas: []
provider_name: Truto
provider_slug: truto
search_terms:
- list employees from a connected hris provider (bamboohr, workday, rippling, etc.) with status and department filtering.
- list jobs
- create contact
- embedded integrations
- create integrated account.
- list job postings from a connected ats (greenhouse, lever, workable, etc.) with status and department filtering.
- list hris groups.
- list contacts from connected crm.
- generate a link token to initiate a customer-facing connection flow for a specific integration (e.g., bamboohr, greenhouse, salesforce).
- list sales opportunities from a connected crm with account, stage, and status filtering.
- ats
- create mcp server
- unified api
- crm contacts
- list timeoff requests
- ats candidates
- create link token
- hris employees
- create link token for customer connection flow.
- mcp
- list candidates
- provision an mcp server for an integrated account so ai agents can directly access the integration's tools.
- crm
- list time off requests from a connected hris provider with employee and status filtering.
- get a single employee record by id from a connected hris provider.
- link token generation
- saas
- list opportunities from connected crm.
- ai agents
- create a new contact in the connected crm provider.
- ats applications
- hris groups and departments
- list employees from connected hris.
- hris
- list integrated accounts.
- list applications from connected ats.
- list employees
- get employee
- list candidate profiles from a connected ats provider.
- list job applications from a connected ats with job, candidate, and status filtering.
- list integrated accounts
- integrated accounts management
- list opportunities
- list jobs from connected ats.
- integration platform
- list candidates from connected ats.
- list groups
- create contact in connected crm.
- list contacts
- create integrated account
- list applications
- list all integrated accounts connected to your truto tenant, showing which third-party apps each customer has connected.
- list crm contacts from a connected provider (salesforce, hubspot, pipedrive, etc.).
- crm opportunities
- ats job postings
slug: unified-integrations
source_filename: unified-integrations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Truto Unified Integrations\n  description: Unified integration platform capability combining Truto Admin API, HRIS, ATS, and CRM unified APIs. Used by\n    B2B SaaS engineering teams and AI agents to manage connected third-party accounts, access normalized HR/recruiting/CRM\n    data across 250+ integrations, and provision MCP servers for AI agent access without writing integration-specific code.\n  tags:\n  - Unified API\n  - Integration Platform\n  - HRIS\n  - ATS\n  - CRM\n  - MCP\n  - AI Agents\n  - Embedded Integrations\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TRUTO_API_TOKEN: TRUTO_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: truto-admin\n    baseUri: https://api.truto.one\n    description: Truto Admin API for managing integrated accounts and link tokens.\n    authentication:\n      type: bearer\n      value: '{{TRUTO_API_TOKEN}}'\n    resources:\n    - name:\
  \ integrated-accounts\n      path: /integrated-accounts\n      description: Integrated account management\n      operations:\n      - name: list-integrated-accounts\n        method: GET\n        description: List all integrated accounts in the tenant.\n        inputParameters:\n        - name: integration\n          in: query\n          type: string\n          required: false\n        - name: status\n          in: query\n          type: string\n          required: false\n        - name: page\n          in: query\n          type: integer\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-integrated-account\n        method: POST\n        description: Programmatically create an integrated account.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            integration: '{{tools.integration}}'\n            name: '{{tools.name}}'\n            credentials: '{{tools.credentials}}'\n    - name: integrated-account\n      path: /integrated-accounts/{id}\n      description: Single integrated account\n      operations:\n      - name: get-integrated-account\n        method: GET\n        description: Get a single integrated account by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-integrated-account\n        method: DELETE\n        description: Delete an integrated account.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mcp-server\n      path: /integrated-accounts/{id}/mcp\n      description: MCP server provisioning\n      operations:\n      - name: create-mcp-server\n        method: POST\n        description: Provision an MCP server for an integrated account.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            allowedMethods: '{{tools.allowedMethods}}'\n    - name: link-tokens\n      path: /link-tokens\n      description: Link token generation\n      operations:\n      - name: create-link-token\n        method: POST\n        description: Generate a link token for customer-initiated account connection.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            integration: '{{tools.integration}}'\n            externalId: '{{tools.externalId}}'\n            redirectUri: '{{tools.redirectUri}}'\n  - type: http\n    namespace: truto-hris\n    baseUri: https://api.truto.one/unified/hris\n    description: Truto Unified HRIS API for normalized HR data access.\n    authentication:\n      type: bearer\n      value: '{{TRUTO_API_TOKEN}}'\n    resources:\n    - name: employees\n      path: /employees\n      description: Employee records\n      operations:\n      - name: list-employees\n        method: GET\n        description: List employees from the connected HRIS provider.\n        inputParameters:\n        - name: integrated_account_id\n          in: query\n          type: string\n          required: true\n        - name: status\n          in: query\n          type: string\n          required:\
  \ false\n        - name: department_id\n          in: query\n          type: string\n          required: false\n        - name: cursor\n          in: query\n          type: string\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: employee\n      path: /employees/{id}\n      description: Single employee record\n      operations:\n      - name: get-employee\n        method: GET\n        description: Get a single employee by ID.\n        inputParameters:\n        - name: integrated_account_id\n          in: query\n          type: string\n          required: true\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  \
  \  - name: employments\n      path: /employments\n      description: Employment records\n      operations:\n      - name: list-employments\n        method: GET\n        description: List employment records.\n        inputParameters:\n        - name: integrated_account_id\n          in: query\n          type: string\n          required: true\n        - name: employee_id\n          in: query\n          type: string\n          required: false\n        - name: cursor\n          in: query\n          type: string\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /groups\n      description: Department and group records\n      operations:\n      - name: list-groups\n        method: GET\n        description: List groups (departments, teams).\n        inputParameters:\n\
  \        - name: integrated_account_id\n          in: query\n          type: string\n          required: true\n        - name: type\n          in: query\n          type: string\n          required: false\n        - name: cursor\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: timeoff-requests\n      path: /timeoff-requests\n      description: Time off requests\n      operations:\n      - name: list-timeoff-requests\n        method: GET\n        description: List time off requests.\n        inputParameters:\n        - name: integrated_account_id\n          in: query\n          type: string\n          required: true\n        - name: employee_id\n          in: query\n          type: string\n          required: false\n        - name: status\n          in: query\n          type: string\n          required: false\n        - name: cursor\n\
  \          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: truto-ats\n    baseUri: https://api.truto.one/unified/ats\n    description: Truto Unified ATS API for normalized recruiting data access.\n    authentication:\n      type: bearer\n      value: '{{TRUTO_API_TOKEN}}'\n    resources:\n    - name: jobs\n      path: /jobs\n      description: Job postings\n      operations:\n      - name: list-jobs\n        method: GET\n        description: List job postings.\n        inputParameters:\n        - name: integrated_account_id\n          in: query\n          type: string\n          required: true\n        - name: status\n          in: query\n          type: string\n          required: false\n        - name: department_id\n          in: query\n          type: string\n          required: false\n        - name: cursor\n  \
  \        in: query\n          type: string\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidates\n      path: /candidates\n      description: Candidate profiles\n      operations:\n      - name: list-candidates\n        method: GET\n        description: List candidates.\n        inputParameters:\n        - name: integrated_account_id\n          in: query\n          type: string\n          required: true\n        - name: cursor\n          in: query\n          type: string\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidate\n      path: /candidates/{id}\n\
  \      description: Single candidate\n      operations:\n      - name: get-candidate\n        method: GET\n        description: Get a single candidate by ID.\n        inputParameters:\n        - name: integrated_account_id\n          in: query\n          type: string\n          required: true\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications\n      path: /applications\n      description: Job applications\n      operations:\n      - name: list-applications\n        method: GET\n        description: List job applications.\n        inputParameters:\n        - name: integrated_account_id\n          in: query\n          type: string\n          required: true\n        - name: job_id\n          in: query\n          type: string\n          required: false\n        - name: candidate_id\n          in: query\n\
  \          type: string\n          required: false\n        - name: status\n          in: query\n          type: string\n          required: false\n        - name: cursor\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: offers\n      path: /offers\n      description: Job offers\n      operations:\n      - name: list-offers\n        method: GET\n        description: List job offers.\n        inputParameters:\n        - name: integrated_account_id\n          in: query\n          type: string\n          required: true\n        - name: application_id\n          in: query\n          type: string\n          required: false\n        - name: status\n          in: query\n          type: string\n          required: false\n        - name: cursor\n          in: query\n          type: string\n          required: false\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: departments\n      path: /departments\n      description: ATS departments\n      operations:\n      - name: list-departments\n        method: GET\n        description: List departments.\n        inputParameters:\n        - name: integrated_account_id\n          in: query\n          type: string\n          required: true\n        - name: cursor\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: truto-crm\n    baseUri: https://api.truto.one/unified/crm\n    description: Truto Unified CRM API for normalized customer relationship data.\n    authentication:\n      type: bearer\n      value: '{{TRUTO_API_TOKEN}}'\n    resources:\n    - name: contacts\n      path: /contacts\n      description: Contact\
  \ records\n      operations:\n      - name: list-contacts\n        method: GET\n        description: List contacts from the connected CRM provider.\n        inputParameters:\n        - name: integrated_account_id\n          in: query\n          type: string\n          required: true\n        - name: account_id\n          in: query\n          type: string\n          required: false\n        - name: cursor\n          in: query\n          type: string\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-contact\n        method: POST\n        description: Create a new contact.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            firstName:\
  \ '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n            email: '{{tools.email}}'\n            phone: '{{tools.phone}}'\n            accountId: '{{tools.accountId}}'\n    - name: accounts\n      path: /accounts\n      description: Account (company) records\n      operations:\n      - name: list-accounts\n        method: GET\n        description: List accounts from the connected CRM provider.\n        inputParameters:\n        - name: integrated_account_id\n          in: query\n          type: string\n          required: true\n        - name: cursor\n          in: query\n          type: string\n          required: false\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-account\n        method: POST\n        description: Create a new account.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            domain: '{{tools.domain}}'\n            industry: '{{tools.industry}}'\n    - name: opportunities\n      path: /opportunities\n      description: Sales opportunities\n      operations:\n      - name: list-opportunities\n        method: GET\n        description: List opportunities from the connected CRM provider.\n        inputParameters:\n        - name: integrated_account_id\n          in: query\n          type: string\n          required: true\n        - name: account_id\n          in: query\n          type: string\n          required: false\n        - name: status\n          in: query\n          type: string\n          required: false\n        - name: cursor\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: create-opportunity\n        method: POST\n        description: Create a new opportunity.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            accountId: '{{tools.accountId}}'\n            amount: '{{tools.amount}}'\n            closeDate: '{{tools.closeDate}}'\n    - name: stages\n      path: /stages\n      description: Pipeline stages\n      operations:\n      - name: list-stages\n        method: GET\n        description: List pipeline stages.\n        inputParameters:\n        - name: integrated_account_id\n          in: query\n          type: string\n          required: true\n        - name: cursor\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: truto-unified-api\n    description: Unified REST API for managing integrations and accessing normalized HRIS, ATS, and CRM data.\n    resources:\n    - path: /v1/integrated-accounts\n      name: integrated-accounts\n      description: Integrated accounts management\n      operations:\n      - method: GET\n        name: list-integrated-accounts\n        description: List integrated accounts.\n        call: truto-admin.list-integrated-accounts\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-integrated-account\n        description: Create integrated account.\n        call: truto-admin.create-integrated-account\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/link-tokens\n      name: link-tokens\n      description: Link token generation\n      operations:\n\
  \      - method: POST\n        name: create-link-token\n        description: Create link token for customer connection flow.\n        call: truto-admin.create-link-token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/hris/employees\n      name: hris-employees\n      description: HRIS employees\n      operations:\n      - method: GET\n        name: list-employees\n        description: List employees from connected HRIS.\n        call: truto-hris.list-employees\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/hris/groups\n      name: hris-groups\n      description: HRIS groups and departments\n      operations:\n      - method: GET\n        name: list-groups\n        description: List HRIS groups.\n        call: truto-hris.list-groups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ats/jobs\n      name: ats-jobs\n      description: ATS job postings\n      operations:\n\
  \      - method: GET\n        name: list-jobs\n        description: List jobs from connected ATS.\n        call: truto-ats.list-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ats/candidates\n      name: ats-candidates\n      description: ATS candidates\n      operations:\n      - method: GET\n        name: list-candidates\n        description: List candidates from connected ATS.\n        call: truto-ats.list-candidates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ats/applications\n      name: ats-applications\n      description: ATS applications\n      operations:\n      - method: GET\n        name: list-applications\n        description: List applications from connected ATS.\n        call: truto-ats.list-applications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/crm/contacts\n      name: crm-contacts\n      description: CRM contacts\n      operations:\n\
  \      - method: GET\n        name: list-contacts\n        description: List contacts from connected CRM.\n        call: truto-crm.list-contacts\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-contact\n        description: Create contact in connected CRM.\n        call: truto-crm.create-contact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/crm/opportunities\n      name: crm-opportunities\n      description: CRM opportunities\n      operations:\n      - method: GET\n        name: list-opportunities\n        description: List opportunities from connected CRM.\n        call: truto-crm.list-opportunities\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: truto-unified-mcp\n    transport: http\n    description: MCP server for AI-assisted management of integrations and access to normalized HRIS, ATS, and CRM data.\n\
  \    tools:\n    - name: list-integrated-accounts\n      description: List all integrated accounts connected to your Truto tenant, showing which third-party apps each customer\n        has connected.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: truto-admin.list-integrated-accounts\n      with:\n        integration: tools.integration\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-link-token\n      description: Generate a link token to initiate a customer-facing connection flow for a specific integration (e.g., BambooHR,\n        Greenhouse, Salesforce).\n      hints:\n        readOnly: false\n        openWorld: false\n      call: truto-admin.create-link-token\n      with:\n        integration: tools.integration\n        externalId: tools.externalId\n        redirectUri: tools.redirectUri\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-mcp-server\n\
  \      description: Provision an MCP server for an integrated account so AI agents can directly access the integration's tools.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: truto-admin.create-mcp-server\n      with:\n        id: tools.id\n        allowedMethods: tools.allowedMethods\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-employees\n      description: List employees from a connected HRIS provider (BambooHR, Workday, Rippling, etc.) with status and department\n        filtering.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: truto-hris.list-employees\n      with:\n        integrated_account_id: tools.integrated_account_id\n        status: tools.status\n        department_id: tools.department_id\n        cursor: tools.cursor\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-employee\n      description: Get a single employee\
  \ record by ID from a connected HRIS provider.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: truto-hris.get-employee\n      with:\n        integrated_account_id: tools.integrated_account_id\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-timeoff-requests\n      description: List time off requests from a connected HRIS provider with employee and status filtering.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: truto-hris.list-timeoff-requests\n      with:\n        integrated_account_id: tools.integrated_account_id\n        employee_id: tools.employee_id\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-jobs\n      description: List job postings from a connected ATS (Greenhouse, Lever, Workable, etc.) with status and department filtering.\n      hints:\n        readOnly: true\n        openWorld: false\n \
  \     call: truto-ats.list-jobs\n      with:\n        integrated_account_id: tools.integrated_account_id\n        status: tools.status\n        department_id: tools.department_id\n        cursor: tools.cursor\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-candidates\n      description: List candidate profiles from a connected ATS provider.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: truto-ats.list-candidates\n      with:\n        integrated_account_id: tools.integrated_account_id\n        cursor: tools.cursor\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-applications\n      description: List job applications from a connected ATS with job, candidate, and status filtering.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: truto-ats.list-applications\n      with:\n        integrated_account_id: tools.integrated_account_id\n\
  \        job_id: tools.job_id\n        candidate_id: tools.candidate_id\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-contacts\n      description: List CRM contacts from a connected provider (Salesforce, HubSpot, Pipedrive, etc.).\n      hints:\n        readOnly: true\n        openWorld: false\n      call: truto-crm.list-contacts\n      with:\n        integrated_account_id: tools.integrated_account_id\n        account_id: tools.account_id\n        cursor: tools.cursor\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-contact\n      description: Create a new contact in the connected CRM provider.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: truto-crm.create-contact\n      with:\n        integrated_account_id: tools.integrated_account_id\n        firstName: tools.firstName\n        lastName: tools.lastName\n        email:\
  \ tools.email\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-opportunities\n      description: List sales opportunities from a connected CRM with account, stage, and status filtering.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: truto-crm.list-opportunities\n      with:\n        integrated_account_id: tools.integrated_account_id\n        account_id: tools.account_id\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/truto/refs/heads/main/capabilities/unified-integrations.yaml
tags:
- Unified API
- Integration Platform
- HRIS
- ATS
- CRM
- MCP
- AI Agents
- Embedded Integrations
tools:
- description: List all integrated accounts connected to your Truto tenant, showing which third-party apps each customer has connected.
  hints:
    openWorld: false
    readOnly: true
  name: list-integrated-accounts
- description: Generate a link token to initiate a customer-facing connection flow for a specific integration (e.g., BambooHR, Greenhouse, Salesforce).
  hints:
    openWorld: false
    readOnly: false
  name: create-link-token
- description: Provision an MCP server for an integrated account so AI agents can directly access the integration's tools.
  hints:
    openWorld: false
    readOnly: false
  name: create-mcp-server
- description: List employees from a connected HRIS provider (BambooHR, Workday, Rippling, etc.) with status and department filtering.
  hints:
    openWorld: false
    readOnly: true
  name: list-employees
- description: Get a single employee record by ID from a connected HRIS provider.
  hints:
    openWorld: false
    readOnly: true
  name: get-employee
- description: List time off requests from a connected HRIS provider with employee and status filtering.
  hints:
    openWorld: false
    readOnly: true
  name: list-timeoff-requests
- description: List job postings from a connected ATS (Greenhouse, Lever, Workable, etc.) with status and department filtering.
  hints:
    openWorld: false
    readOnly: true
  name: list-jobs
- description: List candidate profiles from a connected ATS provider.
  hints:
    openWorld: false
    readOnly: true
  name: list-candidates
- description: List job applications from a connected ATS with job, candidate, and status filtering.
  hints:
    openWorld: false
    readOnly: true
  name: list-applications
- description: List CRM contacts from a connected provider (Salesforce, HubSpot, Pipedrive, etc.).
  hints:
    openWorld: false
    readOnly: true
  name: list-contacts
- description: Create a new contact in the connected CRM provider.
  hints:
    openWorld: false
    readOnly: false
  name: create-contact
- description: List sales opportunities from a connected CRM with account, stage, and status filtering.
  hints:
    openWorld: false
    readOnly: true
  name: list-opportunities
---
