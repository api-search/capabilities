---
categories:
- crm-sales
consumed_apis: []
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
- update a deal
- list crm lists for segmentation
- sales
- create task
- hubspot
- create contact
- get contact
- company management
- list note engagements
- create a note engagement
- search contacts
- list all companies
- create deal
- deal management
- search companies
- analytics
- list crm lists
- update contact
- list tasks
- get a deal by id
- list deals
- content
- create a new deal
- marketing
- call engagements
- list notes
- search crm objects
- create company
- create call
- operations
- list meetings
- create meeting
- create a task engagement
- commerce
- log an email engagement
- log a call engagement
- list meeting engagements
- individual deal
- marketing automation
- crm
- get deal
- email marketing
- list companies
- search deals
- search contacts with filters
- update a contact
- search deals with filters
- create a new contact
- list all crm contacts
- update deal
- list calls
- get a contact by id
- list email engagements
- contact management
- list all deals
- list task engagements
- create a new company
- create email engagement
- get a company by id
- log a meeting engagement
- search any crm object type
- pipeline
- task engagements
- list contacts
- customer service
- individual contact
- create note
- get company
- search companies with filters
- list call engagements
- engagements
slug: sales-pipeline
source_filename: sales-pipeline.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: HubSpot Sales Pipeline\n  description: Unified workflow for sales reps to manage contacts, companies, deals, engagement activities (calls, emails,\n    meetings, notes, tasks), lists, and CRM search. Combines core CRM and engagement APIs for end-to-end sales operations.\n  tags:\n  - HubSpot\n  - Sales\n  - CRM\n  - Pipeline\n  - Engagements\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    HUBSPOT_ACCESS_TOKEN: HUBSPOT_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: crm-contacts\n    baseUri: https://api.hubapi.com\n    description: HubSpot CRM Contacts API for managing contact records.\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: contacts\n      path: /crm/v3/objects/contacts\n      description: Contact records\n      operations:\n      - name: list-contacts\n        method: GET\n        description: List\
  \ all contacts\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results per page\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: properties\n          in: query\n          type: string\n          required: false\n          description: Comma-separated properties to return\n        - name: archived\n          in: query\n          type: boolean\n          required: false\n          description: Return archived contacts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-contact\n        method: POST\n        description: Create a contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n      \
  \    type: json\n          data:\n            properties: '{{tools.properties}}'\n    - name: contact-by-id\n      path: /crm/v3/objects/contacts/{contactId}\n      description: Individual contact\n      operations:\n      - name: get-contact\n        method: GET\n        description: Get a contact by ID\n        inputParameters:\n        - name: contactId\n          in: path\n          type: string\n          required: true\n          description: Contact ID\n        - name: properties\n          in: query\n          type: string\n          required: false\n          description: Properties to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-contact\n        method: PATCH\n        description: Update a contact\n        inputParameters:\n        - name: contactId\n          in: path\n          type: string\n          required: true\n          description: Contact ID\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            properties: '{{tools.properties}}'\n      - name: archive-contact\n        method: DELETE\n        description: Archive a contact\n        inputParameters:\n        - name: contactId\n          in: path\n          type: string\n          required: true\n          description: Contact ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /crm/v3/objects/contacts/search\n      description: Search contacts\n      operations:\n      - name: search-contacts\n        method: POST\n        description: Search contacts with filters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n        \
  \    filterGroups: '{{tools.filterGroups}}'\n            query: '{{tools.query}}'\n            limit: '{{tools.limit}}'\n            properties: '{{tools.properties}}'\n    - name: batch-read\n      path: /crm/v3/objects/contacts/batch/read\n      description: Batch read contacts\n      operations:\n      - name: batch-read-contacts\n        method: POST\n        description: Read multiple contacts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n            properties: '{{tools.properties}}'\n    - name: batch-create\n      path: /crm/v3/objects/contacts/batch/create\n      description: Batch create contacts\n      operations:\n      - name: batch-create-contacts\n        method: POST\n        description: Create multiple contacts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n \
  \         type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n    - name: batch-archive\n      path: /crm/v3/objects/contacts/batch/archive\n      description: Batch archive contacts\n      operations:\n      - name: batch-archive-contacts\n        method: POST\n        description: Archive multiple contacts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n  - type: http\n    namespace: crm-companies\n    baseUri: https://api.hubapi.com\n    description: HubSpot CRM Companies API for managing company records.\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: companies\n      path: /crm/v3/objects/companies\n      description: Company records\n      operations:\n      - name: list-companies\n\
  \        method: GET\n        description: List all companies\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results per page\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: properties\n          in: query\n          type: string\n          required: false\n          description: Properties to return\n        - name: archived\n          in: query\n          type: boolean\n          required: false\n          description: Return archived companies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-company\n        method: POST\n        description: Create a company\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n        body:\n          type: json\n          data:\n            properties: '{{tools.properties}}'\n    - name: company-by-id\n      path: /crm/v3/objects/companies/{companyId}\n      description: Individual company\n      operations:\n      - name: get-company\n        method: GET\n        description: Get a company by ID\n        inputParameters:\n        - name: companyId\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-company\n        method: PATCH\n        description: Update a company\n        inputParameters:\n        - name: companyId\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n   \
  \     body:\n          type: json\n          data:\n            properties: '{{tools.properties}}'\n      - name: archive-company\n        method: DELETE\n        description: Archive a company\n        inputParameters:\n        - name: companyId\n          in: path\n          type: string\n          required: true\n          description: Company ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /crm/v3/objects/companies/search\n      description: Search companies\n      operations:\n      - name: search-companies\n        method: POST\n        description: Search companies with filters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            filterGroups: '{{tools.filterGroups}}'\n            query: '{{tools.query}}'\n            limit: '{{tools.limit}}'\n\
  \            properties: '{{tools.properties}}'\n    - name: batch-read\n      path: /crm/v3/objects/companies/batch/read\n      description: Batch read companies\n      operations:\n      - name: batch-read-companies\n        method: POST\n        description: Read multiple companies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            inputs: '{{tools.inputs}}'\n            properties: '{{tools.properties}}'\n  - type: http\n    namespace: crm-deals\n    baseUri: https://api.hubapi.com\n    description: HubSpot CRM Deals API for managing sales deal records.\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: deals\n      path: /crm/v3/objects/deals\n      description: Deal records\n      operations:\n      - name: list-deals\n        method: GET\n        description: List all deals\n   \
  \     inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results per page\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: properties\n          in: query\n          type: string\n          required: false\n          description: Properties to return\n        - name: archived\n          in: query\n          type: boolean\n          required: false\n          description: Return archived deals\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-deal\n        method: POST\n        description: Create a deal\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n          \
  \  properties: '{{tools.properties}}'\n    - name: deal-by-id\n      path: /crm/v3/objects/deals/{dealId}\n      description: Individual deal\n      operations:\n      - name: get-deal\n        method: GET\n        description: Get a deal by ID\n        inputParameters:\n        - name: dealId\n          in: path\n          type: string\n          required: true\n          description: Deal ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-deal\n        method: PATCH\n        description: Update a deal\n        inputParameters:\n        - name: dealId\n          in: path\n          type: string\n          required: true\n          description: Deal ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            properties: '{{tools.properties}}'\n      -\
  \ name: archive-deal\n        method: DELETE\n        description: Archive a deal\n        inputParameters:\n        - name: dealId\n          in: path\n          type: string\n          required: true\n          description: Deal ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /crm/v3/objects/deals/search\n      description: Search deals\n      operations:\n      - name: search-deals\n        method: POST\n        description: Search deals with filters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            filterGroups: '{{tools.filterGroups}}'\n            query: '{{tools.query}}'\n            limit: '{{tools.limit}}'\n            properties: '{{tools.properties}}'\n  - type: http\n    namespace: crm-lists\n    baseUri: https://api.hubapi.com\n\
  \    description: HubSpot CRM Lists API for managing contact and object lists.\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: lists\n      path: /crm/v3/lists\n      description: CRM lists\n      operations:\n      - name: list-lists\n        method: GET\n        description: List all CRM lists\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results per page\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: listType\n          in: query\n          type: string\n          required: false\n          description: Filter by STATIC or DYNAMIC\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-list\n        method: POST\n    \
  \    description: Create a new list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            objectTypeId: '{{tools.objectTypeId}}'\n            processingType: '{{tools.processingType}}'\n    - name: list-by-id\n      path: /crm/v3/lists/{listId}\n      description: Individual list\n      operations:\n      - name: get-list\n        method: GET\n        description: Get a list by ID\n        inputParameters:\n        - name: listId\n          in: path\n          type: string\n          required: true\n          description: List ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-list\n        method: PUT\n        description: Update a list\n        inputParameters:\n        - name: listId\n          in: path\n     \
  \     type: string\n          required: true\n          description: List ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: delete-list\n        method: DELETE\n        description: Delete a list\n        inputParameters:\n        - name: listId\n          in: path\n          type: string\n          required: true\n          description: List ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: memberships\n      path: /crm/v3/lists/{listId}/memberships\n      description: List memberships\n      operations:\n      - name: get-memberships\n        method: GET\n        description: Get list memberships\n        inputParameters:\n        - name: listId\n          in: path\n          type: string\n          required: true\n\
  \          description: List ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: crm-search\n    baseUri: https://api.hubapi.com\n    description: HubSpot CRM Search API for querying CRM objects.\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: search\n      path: /crm/v3/objects/{objectType}/search\n      description: CRM object search\n      operations:\n      - name: search-objects\n        method: POST\n        description: Search CRM objects of a specified type\n        inputParameters:\n        - name: objectType\n          in: path\n          type: string\n          required: true\n          description: Object type to search (contacts, companies, deals, tickets)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n     \
  \     type: json\n          data:\n            filterGroups: '{{tools.filterGroups}}'\n            sorts: '{{tools.sorts}}'\n            query: '{{tools.query}}'\n            properties: '{{tools.properties}}'\n            limit: '{{tools.limit}}'\n            after: '{{tools.after}}'\n  - type: http\n    namespace: engagement-calls\n    baseUri: https://api.hubapi.com\n    description: HubSpot Engagement Calls API for managing call records.\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: calls\n      path: /crm/v3/objects/calls\n      description: Call engagement records\n      operations:\n      - name: list-calls\n        method: GET\n        description: List all calls\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results per page\n        - name: after\n          in: query\n          type: string\n          required:\
  \ false\n          description: Pagination cursor\n        - name: properties\n          in: query\n          type: string\n          required: false\n          description: Properties to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-call\n        method: POST\n        description: Create a call record\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            properties: '{{tools.properties}}'\n    - name: call-by-id\n      path: /crm/v3/objects/calls/{callId}\n      description: Individual call\n      operations:\n      - name: get-call\n        method: GET\n        description: Get a call by ID\n        inputParameters:\n        - name: callId\n          in: path\n          type: string\n          required: true\n          description: Call ID\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-call\n        method: PATCH\n        description: Update a call\n        inputParameters:\n        - name: callId\n          in: path\n          type: string\n          required: true\n          description: Call ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            properties: '{{tools.properties}}'\n      - name: archive-call\n        method: DELETE\n        description: Archive a call\n        inputParameters:\n        - name: callId\n          in: path\n          type: string\n          required: true\n          description: Call ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /crm/v3/objects/calls/search\n\
  \      description: Search calls\n      operations:\n      - name: search-calls\n        method: POST\n        description: Search calls with filters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            filterGroups: '{{tools.filterGroups}}'\n            query: '{{tools.query}}'\n  - type: http\n    namespace: engagement-emails\n    baseUri: https://api.hubapi.com\n    description: HubSpot Engagement Emails API for managing email activity records.\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: emails\n      path: /crm/v3/objects/emails\n      description: Email engagement records\n      operations:\n      - name: list-email-engagements\n        method: GET\n        description: List all email engagements\n        inputParameters:\n        - name: limit\n          in: query\n         \
  \ type: integer\n          required: false\n          description: Maximum results per page\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: properties\n          in: query\n          type: string\n          required: false\n          description: Properties to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-email-engagement\n        method: POST\n        description: Create an email engagement\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            properties: '{{tools.properties}}'\n    - name: email-by-id\n      path: /crm/v3/objects/emails/{emailId}\n      description: Individual email engagement\n      operations:\n      - name: get-email-engagement\n\
  \        method: GET\n        description: Get an email engagement by ID\n        inputParameters:\n        - name: emailId\n          in: path\n          type: string\n          required: true\n          description: Email engagement ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-email-engagement\n        method: PATCH\n        description: Update an email engagement\n        inputParameters:\n        - name: emailId\n          in: path\n          type: string\n          required: true\n          description: Email engagement ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            properties: '{{tools.properties}}'\n      - name: archive-email-engagement\n        method: DELETE\n        description: Archive an email engagement\n        inputParameters:\n\
  \        - name: emailId\n          in: path\n          type: string\n          required: true\n          description: Email engagement ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: engagement-meetings\n    baseUri: https://api.hubapi.com\n    description: HubSpot Engagement Meetings API for managing meeting records.\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: meetings\n      path: /crm/v3/objects/meetings\n      description: Meeting engagement records\n      operations:\n      - name: list-meetings\n        method: GET\n        description: List all meetings\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results per page\n        - name: after\n          in: query\n          type: string\n          required:\
  \ false\n          description: Pagination cursor\n        - name: properties\n          in: query\n          type: string\n          required: false\n          description: Properties to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-meeting\n        method: POST\n        description: Create a meeting\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            properties: '{{tools.properties}}'\n    - name: meeting-by-id\n      path: /crm/v3/objects/meetings/{meetingId}\n      description: Individual meeting\n      operations:\n      - name: get-meeting\n        method: GET\n        description: Get a meeting by ID\n        inputParameters:\n        - name: meetingId\n          in: path\n          type: string\n          required: true\n        \
  \  description: Meeting ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-meeting\n        method: PATCH\n        description: Update a meeting\n        inputParameters:\n        - name: meetingId\n          in: path\n          type: string\n          required: true\n          description: Meeting ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            properties: '{{tools.properties}}'\n      - name: archive-meeting\n        method: DELETE\n        description: Archive a meeting\n        inputParameters:\n        - name: meetingId\n          in: path\n          type: string\n          required: true\n          description: Meeting ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n  - type: http\n    namespace: engagement-notes\n    baseUri: https://api.hubapi.com\n    description: HubSpot Engagement Notes API.\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: notes\n      path: /crm/v3/objects/notes\n      description: Note records\n      operations:\n      - name: list-notes\n        method: GET\n        description: List all notes\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Cursor\n        - name: properties\n          in: query\n          type: string\n          required: false\n          description: Properties\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-note\n\
  \        method: POST\n        description: Create a note\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            properties: '{{tools.properties}}'\n    - name: note-by-id\n      path: /crm/v3/objects/notes/{noteId}\n      description: Individual note\n      operations:\n      - name: get-note\n        method: GET\n        description: Get a note\n        inputParameters:\n        - name: noteId\n          in: path\n          type: string\n          required: true\n          description: Note ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-note\n        method: PATCH\n        description: Update a note\n        inputParameters:\n        - name: noteId\n          in: path\n          type: string\n          required: true\n          description: Note\
  \ ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            properties: '{{tools.properties}}'\n      - name: archive-note\n        method: DELETE\n        description: Archive a note\n        inputParameters:\n        - name: noteId\n          in: path\n          type: string\n          required: true\n          description: Note ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: engagement-tasks\n    baseUri: https://api.hubapi.com\n    description: HubSpot Engagement Tasks API.\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: tasks\n      path: /crm/v3/objects/tasks\n      description: Task records\n      operations:\n      - name: list-tasks\n        method: GET\n        description:\
  \ List all tasks\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Cursor\n        - name: properties\n          in: query\n          type: string\n          required: false\n          description: Properties\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-task\n        method: POST\n        description: Create a task\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            properties: '{{tools.properties}}'\n    - name: task-by-id\n      path: /crm/v3/objects/tasks/{taskId}\n      description: Individual task\n      operations:\n\
  \      - name: get-task\n        method: GET\n        description: Get a task\n        inputParameters:\n        - name: taskId\n          in: path\n          type: string\n          required: true\n          description: Task ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-task\n        method: PATCH\n        description: Update a task\n        inputParameters:\n        - name: taskId\n          in: path\n          type: string\n          required: true\n          description: Task ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            properties: '{{tools.properties}}'\n      - name: archive-task\n        method: DELETE\n        description: Archive a task\n        inputParameters:\n        - name: taskId\n          in: path\n          type:\
  \ string\n          required: true\n          description: Task ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: sales-pipeline-api\n    description: Unified REST API for sales pipeline management, contact outreach, and deal tracking.\n    resources:\n    - path: /v1/contacts\n      name: contacts\n      description: Contact management\n      operations:\n      - method: GET\n        name: list-contacts\n        description: List contacts\n        call: crm-contacts.list-contacts\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-contact\n        description: Create contact\n        call: crm-contacts.create-contact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/contacts/{contactId}\n      name: contact-by-id\n      description: Individual\
  \ contact\n      operations:\n      - method: GET\n        name: get-contact\n        description: Get contact\n        call: crm-contacts.get-contact\n        with:\n          contactId: rest.contactId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-contact\n        description: Update contact\n        call: crm-contacts.update-contact\n        with:\n          contactId: rest.contactId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/companies\n      name: companies\n      description: Company management\n      operations:\n      - method: GET\n        name: list-companies\n        description: List companies\n        call: crm-companies.list-companies\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-company\n        description: Create company\n        call: crm-companies.create-company\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/deals\n      name: deals\n      description: Deal management\n      operations:\n      - method: GET\n        name: list-deals\n        description: List deals\n        call: crm-deals.list-deals\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-deal\n        description: Create deal\n        call: crm-deals.create-deal\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/deals/{dealId}\n      name: deal-by-id\n      description: Individual deal\n      operations:\n      - method: GET\n        name: get-deal\n        description: Get deal\n        call: crm-deals.get-deal\n        with:\n          dealId: rest.dealId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - met\n\n# --- truncated at 32 KB (40 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/hubspot/refs/heads/main/capabilities/sales-pipeline.yaml\n"
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
