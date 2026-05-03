---
categories: []
consumed_apis:
- truto-admin
- truto-hris
- truto-ats
- truto-crm
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
- generate a link token to initiate a customer-facing connection flow for a specific integration (e.g., bamboohr, greenhouse, salesforce).
- integration platform
- hris
- list applications from connected ats.
- create link token
- ai agents
- list candidate profiles from a connected ats provider.
- list employees from connected hris.
- list applications
- list crm contacts from a connected provider (salesforce, hubspot, pipedrive, etc.).
- list hris groups.
- hris groups and departments
- crm contacts
- saas
- integrated accounts management
- list employees from a connected hris provider (bamboohr, workday, rippling, etc.) with status and department filtering.
- crm opportunities
- list all integrated accounts connected to your truto tenant, showing which third-party apps each customer has connected.
- ats job postings
- list job postings from a connected ats (greenhouse, lever, workable, etc.) with status and department filtering.
- create a new contact in the connected crm provider.
- unified api
- list candidates
- list candidates from connected ats.
- list sales opportunities from a connected crm with account, stage, and status filtering.
- list jobs
- get a single employee record by id from a connected hris provider.
- list timeoff requests
- list opportunities
- create integrated account
- hris employees
- provision an mcp server for an integrated account so ai agents can directly access the integration's tools.
- list employees
- list time off requests from a connected hris provider with employee and status filtering.
- link token generation
- get employee
- list job applications from a connected ats with job, candidate, and status filtering.
- embedded integrations
- create contact
- mcp
- list contacts
- create mcp server
- list contacts from connected crm.
- ats
- list groups
- ats applications
- list opportunities from connected crm.
- ats candidates
- create integrated account.
- crm
- create link token for customer connection flow.
- list integrated accounts.
- list jobs from connected ats.
- create contact in connected crm.
- list integrated accounts
slug: unified-integrations
source_filename: unified-integrations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Truto Unified Integrations\"\n  description: >-\n    Unified integration platform capability combining Truto Admin API, HRIS, ATS, and CRM\n    unified APIs. Used by B2B SaaS engineering teams and AI agents to manage connected\n    third-party accounts, access normalized HR/recruiting/CRM data across 250+ integrations,\n    and provision MCP servers for AI agent access without writing integration-specific code.\n  tags:\n    - Unified API\n    - Integration Platform\n    - HRIS\n    - ATS\n    - CRM\n    - MCP\n    - AI Agents\n    - Embedded Integrations\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TRUTO_API_TOKEN: TRUTO_API_TOKEN\n\ncapability:\n  consumes:\n    - import: truto-admin\n      location: ./shared/admin.yaml\n    - import: truto-hris\n      location: ./shared/unified-hris.yaml\n    - import: truto-ats\n      location: ./shared/unified-ats.yaml\n    - import:\
  \ truto-crm\n      location: ./shared/unified-crm.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: truto-unified-api\n      description: \"Unified REST API for managing integrations and accessing normalized HRIS, ATS, and CRM data.\"\n      resources:\n        - path: /v1/integrated-accounts\n          name: integrated-accounts\n          description: \"Integrated accounts management\"\n          operations:\n            - method: GET\n              name: list-integrated-accounts\n              description: \"List integrated accounts.\"\n              call: \"truto-admin.list-integrated-accounts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-integrated-account\n              description: \"Create integrated account.\"\n              call: \"truto-admin.create-integrated-account\"\n              outputParameters:\n                - type: object\n       \
  \           mapping: \"$.\"\n        - path: /v1/link-tokens\n          name: link-tokens\n          description: \"Link token generation\"\n          operations:\n            - method: POST\n              name: create-link-token\n              description: \"Create link token for customer connection flow.\"\n              call: \"truto-admin.create-link-token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/hris/employees\n          name: hris-employees\n          description: \"HRIS employees\"\n          operations:\n            - method: GET\n              name: list-employees\n              description: \"List employees from connected HRIS.\"\n              call: \"truto-hris.list-employees\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/hris/groups\n          name: hris-groups\n          description: \"HRIS groups and departments\"\n\
  \          operations:\n            - method: GET\n              name: list-groups\n              description: \"List HRIS groups.\"\n              call: \"truto-hris.list-groups\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/ats/jobs\n          name: ats-jobs\n          description: \"ATS job postings\"\n          operations:\n            - method: GET\n              name: list-jobs\n              description: \"List jobs from connected ATS.\"\n              call: \"truto-ats.list-jobs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/ats/candidates\n          name: ats-candidates\n          description: \"ATS candidates\"\n          operations:\n            - method: GET\n              name: list-candidates\n              description: \"List candidates from connected ATS.\"\n              call: \"truto-ats.list-candidates\"\n           \
  \   outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/ats/applications\n          name: ats-applications\n          description: \"ATS applications\"\n          operations:\n            - method: GET\n              name: list-applications\n              description: \"List applications from connected ATS.\"\n              call: \"truto-ats.list-applications\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/crm/contacts\n          name: crm-contacts\n          description: \"CRM contacts\"\n          operations:\n            - method: GET\n              name: list-contacts\n              description: \"List contacts from connected CRM.\"\n              call: \"truto-crm.list-contacts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-contact\n           \
  \   description: \"Create contact in connected CRM.\"\n              call: \"truto-crm.create-contact\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/crm/opportunities\n          name: crm-opportunities\n          description: \"CRM opportunities\"\n          operations:\n            - method: GET\n              name: list-opportunities\n              description: \"List opportunities from connected CRM.\"\n              call: \"truto-crm.list-opportunities\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: truto-unified-mcp\n      transport: http\n      description: \"MCP server for AI-assisted management of integrations and access to normalized HRIS, ATS, and CRM data.\"\n      tools:\n        - name: list-integrated-accounts\n          description: \"List all integrated accounts connected to your Truto tenant,\
  \ showing which third-party apps each customer has connected.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"truto-admin.list-integrated-accounts\"\n          with:\n            integration: \"tools.integration\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-link-token\n          description: \"Generate a link token to initiate a customer-facing connection flow for a specific integration (e.g., BambooHR, Greenhouse, Salesforce).\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"truto-admin.create-link-token\"\n          with:\n            integration: \"tools.integration\"\n            externalId: \"tools.externalId\"\n            redirectUri: \"tools.redirectUri\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-mcp-server\n\
  \          description: \"Provision an MCP server for an integrated account so AI agents can directly access the integration's tools.\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"truto-admin.create-mcp-server\"\n          with:\n            id: \"tools.id\"\n            allowedMethods: \"tools.allowedMethods\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-employees\n          description: \"List employees from a connected HRIS provider (BambooHR, Workday, Rippling, etc.) with status and department filtering.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"truto-hris.list-employees\"\n          with:\n            integrated_account_id: \"tools.integrated_account_id\"\n            status: \"tools.status\"\n            department_id: \"tools.department_id\"\n            cursor: \"tools.cursor\"\n            limit: \"tools.limit\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-employee\n          description: \"Get a single employee record by ID from a connected HRIS provider.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"truto-hris.get-employee\"\n          with:\n            integrated_account_id: \"tools.integrated_account_id\"\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-timeoff-requests\n          description: \"List time off requests from a connected HRIS provider with employee and status filtering.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"truto-hris.list-timeoff-requests\"\n          with:\n            integrated_account_id: \"tools.integrated_account_id\"\n            employee_id: \"tools.employee_id\"\n            status: \"tools.status\"\n  \
  \        outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-jobs\n          description: \"List job postings from a connected ATS (Greenhouse, Lever, Workable, etc.) with status and department filtering.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"truto-ats.list-jobs\"\n          with:\n            integrated_account_id: \"tools.integrated_account_id\"\n            status: \"tools.status\"\n            department_id: \"tools.department_id\"\n            cursor: \"tools.cursor\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-candidates\n          description: \"List candidate profiles from a connected ATS provider.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"truto-ats.list-candidates\"\n          with:\n            integrated_account_id: \"tools.integrated_account_id\"\n  \
  \          cursor: \"tools.cursor\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-applications\n          description: \"List job applications from a connected ATS with job, candidate, and status filtering.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"truto-ats.list-applications\"\n          with:\n            integrated_account_id: \"tools.integrated_account_id\"\n            job_id: \"tools.job_id\"\n            candidate_id: \"tools.candidate_id\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-contacts\n          description: \"List CRM contacts from a connected provider (Salesforce, HubSpot, Pipedrive, etc.).\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"truto-crm.list-contacts\"\n \
  \         with:\n            integrated_account_id: \"tools.integrated_account_id\"\n            account_id: \"tools.account_id\"\n            cursor: \"tools.cursor\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-contact\n          description: \"Create a new contact in the connected CRM provider.\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"truto-crm.create-contact\"\n          with:\n            integrated_account_id: \"tools.integrated_account_id\"\n            firstName: \"tools.firstName\"\n            lastName: \"tools.lastName\"\n            email: \"tools.email\"\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-opportunities\n          description: \"List sales opportunities from a connected CRM with account, stage, and status\
  \ filtering.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"truto-crm.list-opportunities\"\n          with:\n            integrated_account_id: \"tools.integrated_account_id\"\n            account_id: \"tools.account_id\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
