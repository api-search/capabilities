---
categories:
- crm-sales
consumed_apis:
- crm-contacts
- crm-companies
- crm-deals
- crm-lists
- crm-search
- engagement-calls
- engagement-emails
- engagement-meetings
- engagement-notes
- engagement-tasks
description: Unified workflow for sales reps to manage contacts, companies, deals, engagement activities (calls, emails, meetings, notes, tasks), lists, and CRM search. Combines core CRM and engagement APIs for end-to-end sales operations.
layout: capability
name: HubSpot Sales Pipeline
operations:
- description: List contacts
  method: GET
  name: list-contacts
  path: /v1/contacts
- description: Create contact
  method: POST
  name: create-contact
  path: /v1/contacts
- description: Get contact
  method: GET
  name: get-contact
  path: /v1/contacts/{contactId}
- description: Update contact
  method: PATCH
  name: update-contact
  path: /v1/contacts/{contactId}
- description: List companies
  method: GET
  name: list-companies
  path: /v1/companies
- description: Create company
  method: POST
  name: create-company
  path: /v1/companies
- description: List deals
  method: GET
  name: list-deals
  path: /v1/deals
- description: Create deal
  method: POST
  name: create-deal
  path: /v1/deals
- description: Get deal
  method: GET
  name: get-deal
  path: /v1/deals/{dealId}
- description: Update deal
  method: PATCH
  name: update-deal
  path: /v1/deals/{dealId}
- description: List calls
  method: GET
  name: list-calls
  path: /v1/calls
- description: List tasks
  method: GET
  name: list-tasks
  path: /v1/tasks
personas: []
provider_name: HubSpot
provider_slug: hubspot
search_terms:
- list all crm contacts
- get company
- operations
- list note engagements
- hubspot
- engagements
- analytics
- create company
- update a deal
- get a contact by id
- create a new deal
- list crm lists
- commerce
- list all companies
- list all deals
- list notes
- search companies
- task engagements
- create note
- individual contact
- create meeting
- list calls
- get deal
- update deal
- create a new company
- list meetings
- search any crm object type
- search crm objects
- call engagements
- list companies
- marketing
- get a company by id
- update contact
- log a meeting engagement
- search contacts
- list crm lists for segmentation
- individual deal
- list contacts
- list task engagements
- get contact
- search companies with filters
- create task
- create a new contact
- contact management
- customer service
- list call engagements
- log an email engagement
- email marketing
- list deals
- crm
- sales
- pipeline
- search contacts with filters
- create email engagement
- log a call engagement
- company management
- create a note engagement
- list email engagements
- create deal
- list tasks
- create contact
- search deals with filters
- update a contact
- content
- get a deal by id
- list meeting engagements
- create a task engagement
- search deals
- marketing automation
- create call
- deal management
slug: sales-pipeline
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"HubSpot Sales Pipeline\"\n  description: \"Unified workflow for sales reps to manage contacts, companies, deals, engagement activities (calls, emails, meetings, notes, tasks), lists, and CRM search. Combines core CRM and engagement APIs for end-to-end sales operations.\"\n  tags:\n    - HubSpot\n    - Sales\n    - CRM\n    - Pipeline\n    - Engagements\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      HUBSPOT_ACCESS_TOKEN: HUBSPOT_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: crm-contacts\n      location: ./shared/crm-contacts.yaml\n    - import: crm-companies\n      location: ./shared/crm-companies.yaml\n    - import: crm-deals\n      location: ./shared/crm-deals.yaml\n    - import: crm-lists\n      location: ./shared/crm-lists.yaml\n    - import: crm-search\n      location: ./shared/crm-search.yaml\n    - import: engagement-calls\n      location: ./shared/engagement-calls.yaml\n\
  \    - import: engagement-emails\n      location: ./shared/engagement-emails.yaml\n    - import: engagement-meetings\n      location: ./shared/engagement-meetings.yaml\n    - import: engagement-notes\n      location: ./shared/engagement-notes.yaml\n    - import: engagement-tasks\n      location: ./shared/engagement-tasks.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: sales-pipeline-api\n      description: \"Unified REST API for sales pipeline management, contact outreach, and deal tracking.\"\n      resources:\n        - path: /v1/contacts\n          name: contacts\n          description: \"Contact management\"\n          operations:\n            - { method: GET, name: list-contacts, description: \"List contacts\", call: \"crm-contacts.list-contacts\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n            - { method: POST, name: create-contact, description: \"Create contact\", call: \"crm-contacts.create-contact\", outputParameters: [{ type: object,\
  \ mapping: \"$.\" }] }\n        - path: /v1/contacts/{contactId}\n          name: contact-by-id\n          description: \"Individual contact\"\n          operations:\n            - { method: GET, name: get-contact, description: \"Get contact\", call: \"crm-contacts.get-contact\", with: { contactId: \"rest.contactId\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n            - { method: PATCH, name: update-contact, description: \"Update contact\", call: \"crm-contacts.update-contact\", with: { contactId: \"rest.contactId\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - path: /v1/companies\n          name: companies\n          description: \"Company management\"\n          operations:\n            - { method: GET, name: list-companies, description: \"List companies\", call: \"crm-companies.list-companies\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n            - { method: POST, name: create-company, description: \"Create company\", call:\
  \ \"crm-companies.create-company\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - path: /v1/deals\n          name: deals\n          description: \"Deal management\"\n          operations:\n            - { method: GET, name: list-deals, description: \"List deals\", call: \"crm-deals.list-deals\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n            - { method: POST, name: create-deal, description: \"Create deal\", call: \"crm-deals.create-deal\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - path: /v1/deals/{dealId}\n          name: deal-by-id\n          description: \"Individual deal\"\n          operations:\n            - { method: GET, name: get-deal, description: \"Get deal\", call: \"crm-deals.get-deal\", with: { dealId: \"rest.dealId\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n            - { method: PATCH, name: update-deal, description: \"Update deal\", call: \"crm-deals.update-deal\", with: { dealId: \"\
  rest.dealId\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - path: /v1/calls\n          name: calls\n          description: \"Call engagements\"\n          operations:\n            - { method: GET, name: list-calls, description: \"List calls\", call: \"engagement-calls.list-calls\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - path: /v1/tasks\n          name: tasks\n          description: \"Task engagements\"\n          operations:\n            - { method: GET, name: list-tasks, description: \"List tasks\", call: \"engagement-tasks.list-tasks\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n\n    - type: mcp\n      port: 9091\n      namespace: sales-pipeline-mcp\n      transport: http\n      description: \"MCP server for AI-assisted sales pipeline management, contact outreach, and deal tracking.\"\n      tools:\n        - { name: list-contacts, description: \"List all CRM contacts\", hints: { readOnly: true, idempotent: true }, call:\
  \ \"crm-contacts.list-contacts\", with: { limit: \"tools.limit\", after: \"tools.after\", properties: \"tools.properties\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: get-contact, description: \"Get a contact by ID\", hints: { readOnly: true, idempotent: true }, call: \"crm-contacts.get-contact\", with: { contactId: \"tools.contactId\", properties: \"tools.properties\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: create-contact, description: \"Create a new contact\", hints: { readOnly: false }, call: \"crm-contacts.create-contact\", with: { properties: \"tools.properties\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: update-contact, description: \"Update a contact\", hints: { readOnly: false, idempotent: true }, call: \"crm-contacts.update-contact\", with: { contactId: \"tools.contactId\", properties: \"tools.properties\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n     \
  \   - { name: search-contacts, description: \"Search contacts with filters\", hints: { readOnly: true, idempotent: true }, call: \"crm-contacts.search-contacts\", with: { filterGroups: \"tools.filterGroups\", query: \"tools.query\", properties: \"tools.properties\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-companies, description: \"List all companies\", hints: { readOnly: true, idempotent: true }, call: \"crm-companies.list-companies\", with: { limit: \"tools.limit\", after: \"tools.after\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: get-company, description: \"Get a company by ID\", hints: { readOnly: true, idempotent: true }, call: \"crm-companies.get-company\", with: { companyId: \"tools.companyId\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: create-company, description: \"Create a new company\", hints: { readOnly: false }, call: \"crm-companies.create-company\", with: { properties:\
  \ \"tools.properties\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: search-companies, description: \"Search companies with filters\", hints: { readOnly: true, idempotent: true }, call: \"crm-companies.search-companies\", with: { filterGroups: \"tools.filterGroups\", query: \"tools.query\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-deals, description: \"List all deals\", hints: { readOnly: true, idempotent: true }, call: \"crm-deals.list-deals\", with: { limit: \"tools.limit\", after: \"tools.after\", properties: \"tools.properties\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: get-deal, description: \"Get a deal by ID\", hints: { readOnly: true, idempotent: true }, call: \"crm-deals.get-deal\", with: { dealId: \"tools.dealId\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: create-deal, description: \"Create a new deal\", hints: { readOnly: false }, call:\
  \ \"crm-deals.create-deal\", with: { properties: \"tools.properties\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: update-deal, description: \"Update a deal\", hints: { readOnly: false, idempotent: true }, call: \"crm-deals.update-deal\", with: { dealId: \"tools.dealId\", properties: \"tools.properties\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: search-deals, description: \"Search deals with filters\", hints: { readOnly: true, idempotent: true }, call: \"crm-deals.search-deals\", with: { filterGroups: \"tools.filterGroups\", query: \"tools.query\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-calls, description: \"List call engagements\", hints: { readOnly: true, idempotent: true }, call: \"engagement-calls.list-calls\", with: { limit: \"tools.limit\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: create-call, description: \"Log a call engagement\", hints:\
  \ { readOnly: false }, call: \"engagement-calls.create-call\", with: { properties: \"tools.properties\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-email-engagements, description: \"List email engagements\", hints: { readOnly: true, idempotent: true }, call: \"engagement-emails.list-email-engagements\", with: { limit: \"tools.limit\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: create-email-engagement, description: \"Log an email engagement\", hints: { readOnly: false }, call: \"engagement-emails.create-email-engagement\", with: { properties: \"tools.properties\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-meetings, description: \"List meeting engagements\", hints: { readOnly: true, idempotent: true }, call: \"engagement-meetings.list-meetings\", with: { limit: \"tools.limit\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: create-meeting, description:\
  \ \"Log a meeting engagement\", hints: { readOnly: false }, call: \"engagement-meetings.create-meeting\", with: { properties: \"tools.properties\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-notes, description: \"List note engagements\", hints: { readOnly: true, idempotent: true }, call: \"engagement-notes.list-notes\", with: { limit: \"tools.limit\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: create-note, description: \"Create a note engagement\", hints: { readOnly: false }, call: \"engagement-notes.create-note\", with: { properties: \"tools.properties\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-tasks, description: \"List task engagements\", hints: { readOnly: true, idempotent: true }, call: \"engagement-tasks.list-tasks\", with: { limit: \"tools.limit\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: create-task, description: \"Create a task\
  \ engagement\", hints: { readOnly: false }, call: \"engagement-tasks.create-task\", with: { properties: \"tools.properties\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-crm-lists, description: \"List CRM lists for segmentation\", hints: { readOnly: true, idempotent: true }, call: \"crm-lists.list-lists\", with: { limit: \"tools.limit\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: search-crm-objects, description: \"Search any CRM object type\", hints: { readOnly: true, idempotent: true }, call: \"crm-search.search-objects\", with: { objectType: \"tools.objectType\", filterGroups: \"tools.filterGroups\", query: \"tools.query\" }, outputParameters: [{ type: object, mapping: \"$.\" }] }\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hubspot/refs/heads/main/capabilities/sales-pipeline.yaml
tags:
- HubSpot
- Sales
- CRM
- Pipeline
- Engagements
tools:
- description: List all CRM contacts
  hints:
    idempotent: true
    readOnly: true
  name: list-contacts
- description: Get a contact by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-contact
- description: Create a new contact
  hints:
    readOnly: false
  name: create-contact
- description: Update a contact
  hints:
    idempotent: true
    readOnly: false
  name: update-contact
- description: Search contacts with filters
  hints:
    idempotent: true
    readOnly: true
  name: search-contacts
- description: List all companies
  hints:
    idempotent: true
    readOnly: true
  name: list-companies
- description: Get a company by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-company
- description: Create a new company
  hints:
    readOnly: false
  name: create-company
- description: Search companies with filters
  hints:
    idempotent: true
    readOnly: true
  name: search-companies
- description: List all deals
  hints:
    idempotent: true
    readOnly: true
  name: list-deals
- description: Get a deal by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-deal
- description: Create a new deal
  hints:
    readOnly: false
  name: create-deal
- description: Update a deal
  hints:
    idempotent: true
    readOnly: false
  name: update-deal
- description: Search deals with filters
  hints:
    idempotent: true
    readOnly: true
  name: search-deals
- description: List call engagements
  hints:
    idempotent: true
    readOnly: true
  name: list-calls
- description: Log a call engagement
  hints:
    readOnly: false
  name: create-call
- description: List email engagements
  hints:
    idempotent: true
    readOnly: true
  name: list-email-engagements
- description: Log an email engagement
  hints:
    readOnly: false
  name: create-email-engagement
- description: List meeting engagements
  hints:
    idempotent: true
    readOnly: true
  name: list-meetings
- description: Log a meeting engagement
  hints:
    readOnly: false
  name: create-meeting
- description: List note engagements
  hints:
    idempotent: true
    readOnly: true
  name: list-notes
- description: Create a note engagement
  hints:
    readOnly: false
  name: create-note
- description: List task engagements
  hints:
    idempotent: true
    readOnly: true
  name: list-tasks
- description: Create a task engagement
  hints:
    readOnly: false
  name: create-task
- description: List CRM lists for segmentation
  hints:
    idempotent: true
    readOnly: true
  name: list-crm-lists
- description: Search any CRM object type
  hints:
    idempotent: true
    readOnly: true
  name: search-crm-objects
---
