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
- list companies
- search companies
- content
- engagements
- operations
- create contact
- get a company by id
- create email engagement
- create a task engagement
- marketing automation
- marketing
- create meeting
- list contacts
- list email engagements
- list meetings
- list notes
- search crm objects
- search deals with filters
- call engagements
- individual deal
- create a note engagement
- update a contact
- create task
- list crm lists for segmentation
- log a call engagement
- search contacts
- list tasks
- list call engagements
- log a meeting engagement
- contact management
- create company
- update deal
- company management
- list deals
- search deals
- commerce
- create a new deal
- update a deal
- get contact
- get a deal by id
- log an email engagement
- search any crm object type
- list all deals
- create deal
- list note engagements
- list task engagements
- list all companies
- email marketing
- pipeline
- list crm lists
- customer service
- get a contact by id
- search contacts with filters
- update contact
- search companies with filters
- list calls
- create call
- task engagements
- create a new contact
- analytics
- sales
- crm
- create a new company
- get company
- create note
- deal management
- individual contact
- get deal
- hubspot
- list meeting engagements
- list all crm contacts
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
