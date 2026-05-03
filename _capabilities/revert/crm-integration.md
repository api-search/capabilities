---
api_specs:
- filename: revert-unified-api-openapi.yml
  format: yaml
  label: revert
  slug: revert
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/revert/refs/heads/main/openapi/revert-unified-api-openapi.yml
categories: []
consumed_apis:
- revert
description: Workflow capability for building unified CRM integrations across Salesforce, HubSpot, Zoho CRM, Pipedrive, and Close CRM. Enables product teams to manage contacts, companies, deals, leads, tasks, events, and notes through a single normalized API with automatic OAuth and field mapping.
layout: capability
name: Revert CRM Integration
operations:
- description: List all contacts from the tenant's connected CRM
  method: GET
  name: list-contacts
  path: /v1/contacts
- description: Create a new contact in the tenant's CRM
  method: POST
  name: create-contact
  path: /v1/contacts
- description: Get a specific contact by ID
  method: GET
  name: get-contact
  path: /v1/contacts/{id}
- description: Update an existing contact
  method: PATCH
  name: update-contact
  path: /v1/contacts/{id}
- description: Search contacts using filter criteria
  method: POST
  name: search-contacts
  path: /v1/contacts/search
- description: List all companies from the tenant's CRM
  method: GET
  name: list-companies
  path: /v1/companies
- description: Create a new company/account in the CRM
  method: POST
  name: create-company
  path: /v1/companies
- description: List all deals/opportunities from the tenant's CRM
  method: GET
  name: list-deals
  path: /v1/deals
- description: Create a new deal/opportunity in the CRM
  method: POST
  name: create-deal
  path: /v1/deals
- description: List all leads from the tenant's CRM
  method: GET
  name: list-leads
  path: /v1/leads
- description: Create a new lead in the CRM
  method: POST
  name: create-lead
  path: /v1/leads
- description: Get OAuth connection status for a tenant
  method: GET
  name: get-connection
  path: /v1/connections
personas: []
provider_name: Revert
provider_slug: revert
search_terms:
- search contacts by criteria
- get details of a specific crm contact by id
- create company
- search contacts using filter criteria
- revert
- update contact
- list all companies from the tenant's crm
- open source
- list all deals/opportunities in the crm pipeline
- integrations
- individual contact operations
- unified deal/opportunity pipeline management
- create a new contact in the tenant's crm
- list all leads from the tenant's crm
- salesforce
- create deal
- unified api
- list companies
- search crm contacts using filter criteria
- get contact
- create a new company/account in the crm
- unified company/account management
- list all companies/accounts from the tenant's crm
- list all deals/opportunities from the tenant's crm
- hubspot
- unified contact management across all connected crms
- get oauth connection status and details for a tenant
- list deals
- list leads
- get connection status
- create contact
- list all leads in the crm
- list all contacts from the tenant's connected crm
- update an existing contact
- create lead
- list contacts
- list all contacts from the tenant's connected crm (salesforce, hubspot, zoho, pipedrive, or close)
- unified lead management
- update an existing crm contact
- get a specific contact by id
- create a new deal/opportunity in the crm
- create a new lead in the crm
- tenant oauth connection management
- search contacts
- get oauth connection status for a tenant
- create a new deal/opportunity in the crm pipeline
- crm
- get connection
- pipedrive
slug: crm-integration
source_filename: crm-integration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Revert CRM Integration\"\n  description: >-\n    Workflow capability for building unified CRM integrations across Salesforce,\n    HubSpot, Zoho CRM, Pipedrive, and Close CRM. Enables product teams to manage\n    contacts, companies, deals, leads, tasks, events, and notes through a single\n    normalized API with automatic OAuth and field mapping.\n  tags:\n    - Revert\n    - CRM\n    - Integrations\n    - Salesforce\n    - HubSpot\n    - Pipedrive\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      REVERT_API_TOKEN: REVERT_API_TOKEN\n      REVERT_TENANT_ID: REVERT_TENANT_ID\n\ncapability:\n  consumes:\n    - import: revert\n      location: ./shared/revert-unified-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: revert-crm-api\n      description: \"Unified REST API for CRM integration workflows.\"\n      resources:\n        - path: /v1/contacts\n  \
  \        name: contacts\n          description: \"Unified contact management across all connected CRMs\"\n          operations:\n            - method: GET\n              name: list-contacts\n              description: \"List all contacts from the tenant's connected CRM\"\n              call: \"revert.get-contacts\"\n              with:\n                x-revert-t-id: \"rest.tenant_id\"\n                pageSize: \"rest.page_size\"\n                cursor: \"rest.cursor\"\n                fields: \"rest.fields\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-contact\n              description: \"Create a new contact in the tenant's CRM\"\n              call: \"revert.create-contact\"\n              with:\n                x-revert-t-id: \"rest.tenant_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/contacts/{id}\n\
  \          name: contact\n          description: \"Individual contact operations\"\n          operations:\n            - method: GET\n              name: get-contact\n              description: \"Get a specific contact by ID\"\n              call: \"revert.get-contact\"\n              with:\n                id: \"rest.id\"\n                x-revert-t-id: \"rest.tenant_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-contact\n              description: \"Update an existing contact\"\n              call: \"revert.update-contact\"\n              with:\n                id: \"rest.id\"\n                x-revert-t-id: \"rest.tenant_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/contacts/search\n          name: contact-search\n          description: \"Search contacts by criteria\"\n          operations:\n\
  \            - method: POST\n              name: search-contacts\n              description: \"Search contacts using filter criteria\"\n              call: \"revert.search-contacts\"\n              with:\n                x-revert-t-id: \"rest.tenant_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/companies\n          name: companies\n          description: \"Unified company/account management\"\n          operations:\n            - method: GET\n              name: list-companies\n              description: \"List all companies from the tenant's CRM\"\n              call: \"revert.get-companies\"\n              with:\n                x-revert-t-id: \"rest.tenant_id\"\n                pageSize: \"rest.page_size\"\n                cursor: \"rest.cursor\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-company\n\
  \              description: \"Create a new company/account in the CRM\"\n              call: \"revert.create-company\"\n              with:\n                x-revert-t-id: \"rest.tenant_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/deals\n          name: deals\n          description: \"Unified deal/opportunity pipeline management\"\n          operations:\n            - method: GET\n              name: list-deals\n              description: \"List all deals/opportunities from the tenant's CRM\"\n              call: \"revert.get-deals\"\n              with:\n                x-revert-t-id: \"rest.tenant_id\"\n                pageSize: \"rest.page_size\"\n                cursor: \"rest.cursor\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-deal\n              description: \"Create a new deal/opportunity\
  \ in the CRM\"\n              call: \"revert.create-deal\"\n              with:\n                x-revert-t-id: \"rest.tenant_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/leads\n          name: leads\n          description: \"Unified lead management\"\n          operations:\n            - method: GET\n              name: list-leads\n              description: \"List all leads from the tenant's CRM\"\n              call: \"revert.get-leads\"\n              with:\n                x-revert-t-id: \"rest.tenant_id\"\n                pageSize: \"rest.page_size\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-lead\n              description: \"Create a new lead in the CRM\"\n              call: \"revert.create-lead\"\n              with:\n                x-revert-t-id: \"rest.tenant_id\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/connections\n          name: connections\n          description: \"Tenant OAuth connection management\"\n          operations:\n            - method: GET\n              name: get-connection\n              description: \"Get OAuth connection status for a tenant\"\n              call: \"revert.get-connection\"\n              with:\n                x-revert-t-id: \"rest.tenant_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: revert-crm-mcp\n      transport: http\n      description: \"MCP server for AI-assisted CRM integration workflows.\"\n      tools:\n        - name: list-contacts\n          description: \"List all contacts from the tenant's connected CRM (Salesforce, HubSpot, Zoho, Pipedrive, or Close)\"\n          hints:\n            readOnly: true\n            openWorld: true\n        \
  \  call: \"revert.get-contacts\"\n          with:\n            x-revert-t-id: \"tools.tenant_id\"\n            pageSize: \"tools.page_size\"\n            cursor: \"tools.cursor\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-contact\n          description: \"Get details of a specific CRM contact by ID\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"revert.get-contact\"\n          with:\n            id: \"tools.contact_id\"\n            x-revert-t-id: \"tools.tenant_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-contact\n          description: \"Create a new contact in the tenant's CRM\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"revert.create-contact\"\n          with:\n            x-revert-t-id: \"tools.tenant_id\"\n    \
  \      outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-contact\n          description: \"Update an existing CRM contact\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"revert.update-contact\"\n          with:\n            id: \"tools.contact_id\"\n            x-revert-t-id: \"tools.tenant_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-contacts\n          description: \"Search CRM contacts using filter criteria\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"revert.search-contacts\"\n          with:\n            x-revert-t-id: \"tools.tenant_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-companies\n          description: \"List all companies/accounts from the tenant's CRM\"\
  \n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"revert.get-companies\"\n          with:\n            x-revert-t-id: \"tools.tenant_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-company\n          description: \"Create a new company/account in the CRM\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"revert.create-company\"\n          with:\n            x-revert-t-id: \"tools.tenant_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-deals\n          description: \"List all deals/opportunities in the CRM pipeline\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"revert.get-deals\"\n          with:\n            x-revert-t-id: \"tools.tenant_id\"\n          outputParameters:\n         \
  \   - type: object\n              mapping: \"$.\"\n        - name: create-deal\n          description: \"Create a new deal/opportunity in the CRM pipeline\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"revert.create-deal\"\n          with:\n            x-revert-t-id: \"tools.tenant_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-leads\n          description: \"List all leads in the CRM\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"revert.get-leads\"\n          with:\n            x-revert-t-id: \"tools.tenant_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-lead\n          description: \"Create a new lead in the CRM\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n\
  \          call: \"revert.create-lead\"\n          with:\n            x-revert-t-id: \"tools.tenant_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-connection-status\n          description: \"Get OAuth connection status and details for a tenant\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"revert.get-connection\"\n          with:\n            x-revert-t-id: \"tools.tenant_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/revert/refs/heads/main/capabilities/crm-integration.yaml
tags:
- Revert
- CRM
- Integrations
- Salesforce
- HubSpot
- Pipedrive
tools:
- description: List all contacts from the tenant's connected CRM (Salesforce, HubSpot, Zoho, Pipedrive, or Close)
  hints:
    openWorld: true
    readOnly: true
  name: list-contacts
- description: Get details of a specific CRM contact by ID
  hints:
    openWorld: false
    readOnly: true
  name: get-contact
- description: Create a new contact in the tenant's CRM
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-contact
- description: Update an existing CRM contact
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-contact
- description: Search CRM contacts using filter criteria
  hints:
    openWorld: true
    readOnly: true
  name: search-contacts
- description: List all companies/accounts from the tenant's CRM
  hints:
    openWorld: true
    readOnly: true
  name: list-companies
- description: Create a new company/account in the CRM
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-company
- description: List all deals/opportunities in the CRM pipeline
  hints:
    openWorld: true
    readOnly: true
  name: list-deals
- description: Create a new deal/opportunity in the CRM pipeline
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-deal
- description: List all leads in the CRM
  hints:
    openWorld: true
    readOnly: true
  name: list-leads
- description: Create a new lead in the CRM
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-lead
- description: Get OAuth connection status and details for a tenant
  hints:
    openWorld: false
    readOnly: true
  name: get-connection-status
---
