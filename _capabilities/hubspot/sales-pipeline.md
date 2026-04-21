---
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
- contact management
- create a task engagement
- list companies
- task engagements
- list calls
- update contact
- create a note engagement
- search crm objects
- list tasks
- crm
- log an email engagement
- create email engagement
- list all deals
- search deals
- list contacts
- create a new contact
- individual deal
- marketing automation
- get company
- search contacts with filters
- list task engagements
- list meeting engagements
- list deals
- list call engagements
- list crm lists
- list note engagements
- operations
- company management
- update a contact
- create contact
- log a meeting engagement
- customer service
- marketing
- list meetings
- create a new deal
- list crm lists for segmentation
- create task
- create call
- list all companies
- update a deal
- list email engagements
- engagements
- create meeting
- pipeline
- get a deal by id
- sales
- call engagements
- get a contact by id
- list notes
- commerce
- search any crm object type
- create deal
- search companies
- log a call engagement
- email marketing
- deal management
- content
- create note
- list all crm contacts
- get deal
- hubspot
- get contact
- create company
- update deal
- create a new company
- search deals with filters
- individual contact
- analytics
- search companies with filters
- get a company by id
- search contacts
slug: sales-pipeline
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
