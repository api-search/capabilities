---
categories: []
consumed_apis: []
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
- list all deals/opportunities from the tenant's crm
- update an existing contact
- hubspot
- create contact
- get contact
- get details of a specific crm contact by id
- search contacts
- create deal
- create a new company/account in the crm
- unified lead management
- list all leads in the crm
- search contacts by criteria
- tenant oauth connection management
- update contact
- list all companies/accounts from the tenant's crm
- get a specific contact by id
- list deals
- list all deals/opportunities in the crm pipeline
- unified api
- revert
- list leads
- get oauth connection status for a tenant
- list all contacts from the tenant's connected crm (salesforce, hubspot, zoho, pipedrive, or close)
- get connection status
- create company
- get oauth connection status and details for a tenant
- unified contact management across all connected crms
- open source
- unified company/account management
- integrations
- list all leads from the tenant's crm
- search contacts using filter criteria
- list all companies from the tenant's crm
- crm
- list companies
- update an existing crm contact
- create lead
- individual contact operations
- create a new contact in the tenant's crm
- list all contacts from the tenant's connected crm
- create a new deal/opportunity in the crm
- unified deal/opportunity pipeline management
- create a new lead in the crm
- search crm contacts using filter criteria
- create a new deal/opportunity in the crm pipeline
- pipedrive
- list contacts
- get connection
- salesforce
slug: crm-integration
source_filename: crm-integration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Revert CRM Integration\n  description: Workflow capability for building unified CRM integrations across Salesforce, HubSpot, Zoho CRM, Pipedrive,\n    and Close CRM. Enables product teams to manage contacts, companies, deals, leads, tasks, events, and notes through a single\n    normalized API with automatic OAuth and field mapping.\n  tags:\n  - Revert\n  - CRM\n  - Integrations\n  - Salesforce\n  - HubSpot\n  - Pipedrive\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    REVERT_API_TOKEN: REVERT_API_TOKEN\n    REVERT_TENANT_ID: REVERT_TENANT_ID\ncapability:\n  consumes:\n  - type: http\n    namespace: revert\n    baseUri: https://api.revert.dev\n    description: Revert Unified API for CRM, ticketing, chat, and accounting integrations\n    authentication:\n      type: apikey\n      key: x-revert-api-token\n      value: '{{REVERT_API_TOKEN}}'\n      placement: header\n    resources:\n    - name:\
  \ connections\n      path: /connection\n      description: Manage third-party OAuth connections and webhooks\n      operations:\n      - name: get-connection\n        method: GET\n        description: Get details of a connection for a specific tenant\n        inputParameters:\n        - name: x-revert-t-id\n          in: header\n          type: string\n          required: true\n          description: The unique customer id used when the customer linked their account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-connection-webhook\n        method: POST\n        description: Create a webhook for a tenant connection\n        inputParameters:\n        - name: x-revert-t-id\n          in: header\n          type: string\n          required: true\n          description: The unique customer tenant ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n         \
  \ type: object\n          value: $.\n        body:\n          type: json\n          data:\n            webhookUrl: '{{tools.webhookUrl}}'\n    - name: crm-contacts\n      path: /crm/contacts\n      description: Unified CRM contact operations\n      operations:\n      - name: get-contacts\n        method: GET\n        description: Get all CRM contacts with pagination\n        inputParameters:\n        - name: x-revert-t-id\n          in: header\n          type: string\n          required: true\n          description: Tenant ID\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields\n        - name: pageSize\n          in: query\n          type: string\n          required: false\n          description: Number of results per page\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-contact\n        method: GET\n        description: Get details of a specific CRM contact by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Contact ID\n        - name: x-revert-t-id\n          in: header\n          type: string\n          required: true\n          description: Tenant ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-contact\n        method: POST\n        description: Create a new CRM contact\n        inputParameters:\n        - name: x-revert-t-id\n          in: header\n          type: string\n          required: true\n          description: Tenant ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n        body:\n          type: json\n          data:\n            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n            email: '{{tools.email}}'\n      - name: update-contact\n        method: PATCH\n        description: Update an existing CRM contact\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Contact ID\n        - name: x-revert-t-id\n          in: header\n          type: string\n          required: true\n          description: Tenant ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: search-contacts\n        method: POST\n        description: Search CRM contacts by criteria\n        inputParameters:\n        - name: x-revert-t-id\n          in: header\n          type: string\n          required: true\n          description: Tenant ID\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            searchCriteria: '{{tools.searchCriteria}}'\n    - name: crm-companies\n      path: /crm/companies\n      description: Unified CRM company/account operations\n      operations:\n      - name: get-companies\n        method: GET\n        description: Get all CRM companies/accounts with pagination\n        inputParameters:\n        - name: x-revert-t-id\n          in: header\n          type: string\n          required: true\n          description: Tenant ID\n        - name: pageSize\n          in: query\n          type: string\n          required: false\n          description: Number of results per page\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n \
  \         type: object\n          value: $.\n      - name: create-company\n        method: POST\n        description: Create a new CRM company/account\n        inputParameters:\n        - name: x-revert-t-id\n          in: header\n          type: string\n          required: true\n          description: Tenant ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            website: '{{tools.website}}'\n    - name: crm-deals\n      path: /crm/deals\n      description: Unified CRM deal/opportunity operations\n      operations:\n      - name: get-deals\n        method: GET\n        description: Get all CRM deals/opportunities with pagination\n        inputParameters:\n        - name: x-revert-t-id\n          in: header\n          type: string\n          required: true\n          description: Tenant ID\n        - name: pageSize\n\
  \          in: query\n          type: string\n          required: false\n          description: Number of results per page\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-deal\n        method: POST\n        description: Create a new CRM deal/opportunity\n        inputParameters:\n        - name: x-revert-t-id\n          in: header\n          type: string\n          required: true\n          description: Tenant ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            amount: '{{tools.amount}}'\n            stage: '{{tools.stage}}'\n    - name: crm-leads\n      path: /crm/leads\n\
  \      description: Unified CRM lead operations\n      operations:\n      - name: get-leads\n        method: GET\n        description: Get all CRM leads with pagination\n        inputParameters:\n        - name: x-revert-t-id\n          in: header\n          type: string\n          required: true\n          description: Tenant ID\n        - name: pageSize\n          in: query\n          type: string\n          required: false\n          description: Number of results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-lead\n        method: POST\n        description: Create a new CRM lead\n        inputParameters:\n        - name: x-revert-t-id\n          in: header\n          type: string\n          required: true\n          description: Tenant ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n       \
  \ body:\n          type: json\n          data:\n            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n            email: '{{tools.email}}'\n    - name: ticket-tasks\n      path: /ticket/tasks\n      description: Unified ticketing task operations\n      operations:\n      - name: get-ticket-tasks\n        method: GET\n        description: Get all ticketing tasks with pagination\n        inputParameters:\n        - name: x-revert-t-id\n          in: header\n          type: string\n          required: true\n          description: Tenant ID\n        - name: pageSize\n          in: query\n          type: string\n          required: false\n          description: Number of results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-ticket-task\n        method: POST\n        description: Create a new ticketing task\n        inputParameters:\n        - name:\
  \ x-revert-t-id\n          in: header\n          type: string\n          required: true\n          description: Tenant ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            description: '{{tools.description}}'\n            priority: '{{tools.priority}}'\n    - name: chat-messages\n      path: /chat/messages\n      description: Unified chat message operations\n      operations:\n      - name: get-messages\n        method: GET\n        description: Get chat messages with pagination\n        inputParameters:\n        - name: x-revert-t-id\n          in: header\n          type: string\n          required: true\n          description: Tenant ID\n        - name: pageSize\n          in: query\n          type: string\n          required: false\n          description: Number of results per page\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: send-message\n        method: POST\n        description: Send a new chat message to a channel\n        inputParameters:\n        - name: x-revert-t-id\n          in: header\n          type: string\n          required: true\n          description: Tenant ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            text: '{{tools.text}}'\n            channelId: '{{tools.channelId}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: revert-crm-api\n    description: Unified REST API for CRM integration workflows.\n    resources:\n    - path: /v1/contacts\n      name: contacts\n      description: Unified contact management across all connected CRMs\n      operations:\n      - method: GET\n        name: list-contacts\n        description:\
  \ List all contacts from the tenant's connected CRM\n        call: revert.get-contacts\n        with:\n          x-revert-t-id: rest.tenant_id\n          pageSize: rest.page_size\n          cursor: rest.cursor\n          fields: rest.fields\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-contact\n        description: Create a new contact in the tenant's CRM\n        call: revert.create-contact\n        with:\n          x-revert-t-id: rest.tenant_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/contacts/{id}\n      name: contact\n      description: Individual contact operations\n      operations:\n      - method: GET\n        name: get-contact\n        description: Get a specific contact by ID\n        call: revert.get-contact\n        with:\n          id: rest.id\n          x-revert-t-id: rest.tenant_id\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n      - method: PATCH\n        name: update-contact\n        description: Update an existing contact\n        call: revert.update-contact\n        with:\n          id: rest.id\n          x-revert-t-id: rest.tenant_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/contacts/search\n      name: contact-search\n      description: Search contacts by criteria\n      operations:\n      - method: POST\n        name: search-contacts\n        description: Search contacts using filter criteria\n        call: revert.search-contacts\n        with:\n          x-revert-t-id: rest.tenant_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/companies\n      name: companies\n      description: Unified company/account management\n      operations:\n      - method: GET\n        name: list-companies\n        description: List all companies from the tenant's CRM\n        call: revert.get-companies\n        with:\n   \
  \       x-revert-t-id: rest.tenant_id\n          pageSize: rest.page_size\n          cursor: rest.cursor\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-company\n        description: Create a new company/account in the CRM\n        call: revert.create-company\n        with:\n          x-revert-t-id: rest.tenant_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/deals\n      name: deals\n      description: Unified deal/opportunity pipeline management\n      operations:\n      - method: GET\n        name: list-deals\n        description: List all deals/opportunities from the tenant's CRM\n        call: revert.get-deals\n        with:\n          x-revert-t-id: rest.tenant_id\n          pageSize: rest.page_size\n          cursor: rest.cursor\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-deal\n        description:\
  \ Create a new deal/opportunity in the CRM\n        call: revert.create-deal\n        with:\n          x-revert-t-id: rest.tenant_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/leads\n      name: leads\n      description: Unified lead management\n      operations:\n      - method: GET\n        name: list-leads\n        description: List all leads from the tenant's CRM\n        call: revert.get-leads\n        with:\n          x-revert-t-id: rest.tenant_id\n          pageSize: rest.page_size\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-lead\n        description: Create a new lead in the CRM\n        call: revert.create-lead\n        with:\n          x-revert-t-id: rest.tenant_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/connections\n      name: connections\n      description: Tenant OAuth connection management\n      operations:\n\
  \      - method: GET\n        name: get-connection\n        description: Get OAuth connection status for a tenant\n        call: revert.get-connection\n        with:\n          x-revert-t-id: rest.tenant_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: revert-crm-mcp\n    transport: http\n    description: MCP server for AI-assisted CRM integration workflows.\n    tools:\n    - name: list-contacts\n      description: List all contacts from the tenant's connected CRM (Salesforce, HubSpot, Zoho, Pipedrive, or Close)\n      hints:\n        readOnly: true\n        openWorld: true\n      call: revert.get-contacts\n      with:\n        x-revert-t-id: tools.tenant_id\n        pageSize: tools.page_size\n        cursor: tools.cursor\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-contact\n      description: Get details of a specific CRM contact by ID\n      hints:\n        readOnly: true\n\
  \        openWorld: false\n      call: revert.get-contact\n      with:\n        id: tools.contact_id\n        x-revert-t-id: tools.tenant_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-contact\n      description: Create a new contact in the tenant's CRM\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: revert.create-contact\n      with:\n        x-revert-t-id: tools.tenant_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-contact\n      description: Update an existing CRM contact\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: revert.update-contact\n      with:\n        id: tools.contact_id\n        x-revert-t-id: tools.tenant_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-contacts\n      description: Search CRM contacts using filter criteria\n \
  \     hints:\n        readOnly: true\n        openWorld: true\n      call: revert.search-contacts\n      with:\n        x-revert-t-id: tools.tenant_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-companies\n      description: List all companies/accounts from the tenant's CRM\n      hints:\n        readOnly: true\n        openWorld: true\n      call: revert.get-companies\n      with:\n        x-revert-t-id: tools.tenant_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-company\n      description: Create a new company/account in the CRM\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: revert.create-company\n      with:\n        x-revert-t-id: tools.tenant_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-deals\n      description: List all deals/opportunities in the CRM pipeline\n      hints:\n        readOnly: true\n\
  \        openWorld: true\n      call: revert.get-deals\n      with:\n        x-revert-t-id: tools.tenant_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-deal\n      description: Create a new deal/opportunity in the CRM pipeline\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: revert.create-deal\n      with:\n        x-revert-t-id: tools.tenant_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-leads\n      description: List all leads in the CRM\n      hints:\n        readOnly: true\n        openWorld: true\n      call: revert.get-leads\n      with:\n        x-revert-t-id: tools.tenant_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-lead\n      description: Create a new lead in the CRM\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: revert.create-lead\n\
  \      with:\n        x-revert-t-id: tools.tenant_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-connection-status\n      description: Get OAuth connection status and details for a tenant\n      hints:\n        readOnly: true\n        openWorld: false\n      call: revert.get-connection\n      with:\n        x-revert-t-id: tools.tenant_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
