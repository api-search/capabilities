---
categories:
- crm-sales
consumed_apis: []
description: Sales activity tracking workflow for calls, emails, meetings, tasks, and notes.
layout: capability
name: HubSpot Sales Engagement
operations: []
personas: []
provider_name: HubSpot
provider_slug: hubspot
search_terms:
- batchreademailengagements
- hubspot batch read tasks
- hubspot create a note
- hubspot search email engagements
- batcharchivenotes
- searchnotes
- hubspot update a task
- listmeetingassociations
- batchreadcalls
- hubspot create a call
- hubspot batch update tasks
- archivecall
- hubspot list task associations
- createcall
- batchcreatemeetings
- hubspot archive a meeting
- hubspot batch create email engagements
- batchupdatecalls
- batcharchivecalls
- hubspot batch read email engagements
- customer service
- createtask
- batchupdatemeetings
- hubspot archive a batch of notes
- hubspot create an email engagement association
- hubspot create a meeting
- batchcreatenotes
- getcallbyid
- getemailengagement
- hubspot read a batch of calls
- searchcalls
- createemailengagementassociation
- listnotes
- gdprdeletecall
- searchemailengagements
- hubspot archive a note
- hubspot update a meeting
- hubspot create a batch of calls
- updatetask
- hubspot read a batch of notes
- hubspot list email engagement associations
- marketing
- updatenote
- hubspot search tasks
- deletemeeting
- deletemeetingassociation
- hubspot batch create tasks
- deleteemailengagement
- getmeeting
- searchtasks
- hubspot update a batch of notes
- hubspot archive a batch of calls
- deleteemailengagementassociation
- hubspot update a call
- hubspot batch update email engagements
- hubspot batch create meetings
- hubspot search notes
- hubspot archive a task
- hubspot get an email engagement
- listtaskassociations
- batchreadmeetings
- archivenote
- searchmeetings
- content
- hubspot get a note by id
- batchreadnotes
- hubspot create a batch of notes
- batchupdatenotes
- hubspot get a meeting
- hubspot create a task
- createtaskassociation
- hubspot permanently delete a note for gdpr compliance
- createmeeting
- batchreadtasks
- hubspot get a task
- hubspot archive an email engagement
- createnote
- hubspot permanently delete a call for gdpr compliance
- createemailengagement
- commerce
- deletetaskassociation
- hubspot list all calls
- listmeetings
- email marketing
- listtasks
- hubspot
- analytics
- operations
- getnotebyid
- hubspot delete a meeting association
- hubspot archive a call
- hubspot list meeting associations
- listemailengagements
- hubspot create a meeting association
- hubspot get a call by id
- hubspot delete an email engagement association
- listemailengagementassociations
- hubspot update a batch of calls
- gdprdeletenote
- hubspot update an email engagement
- gettask
- batchupdatetasks
- hubspot create a task association
- updatemeeting
- hubspot list tasks
- batchcreateemailengagements
- createmeetingassociation
- hubspot list email engagements
- batchupdateemailengagements
- crm
- hubspot search meetings
- batchcreatetasks
- engagements
- hubspot delete a task association
- activities
- hubspot create an email engagement
- hubspot list all notes
- hubspot list meetings
- updateemailengagement
- sales
- listcalls
- deletetask
- batchcreatecalls
- updatecall
- hubspot search calls
- hubspot batch read meetings
- hubspot batch update meetings
- hubspot update a note
- marketing automation
slug: sales-engagement
source_filename: sales-engagement.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: HubSpot Sales Engagement\n  description: Sales activity tracking workflow for calls, emails, meetings, tasks, and notes.\n  tags:\n  - HubSpot\n  - Sales\n  - Engagements\n  - Activities\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    HUBSPOT_ACCESS_TOKEN: HUBSPOT_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: engagement-calls-api\n    baseUri: https://api.hubapi.com\n    description: 'The HubSpot CRM Engagement Calls API enables you to manage call engagements within your HubSpot CRM.\n\n\n      Use this API to:\n\n      - Create, read, update, and delete call records\n\n      - Perform batch operations on mul'\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: calls\n      path: /calls\n      description: calls operations\n      operations:\n      - name: listcalls\n        method: GET\n        description: HubSpot\
  \ List All Calls\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcall\n        method: POST\n        description: HubSpot Create a Call\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getcallbyid\n        method: GET\n        description: HubSpot Get a Call by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecall\n        method: PATCH\n        description: HubSpot Update a Call\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: archivecall\n        method: DELETE\n        description: HubSpot Archive a Call\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: create\n      path: /create\n      description: create operations\n      operations:\n      - name: batchcreatecalls\n        method: POST\n        description: HubSpot Create a Batch of Calls\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: read\n      path: /read\n      description: read operations\n      operations:\n      - name: batchreadcalls\n        method: POST\n        description: HubSpot Read a Batch of Calls\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: update\n      path: /update\n      description: update operations\n      operations:\n      - name: batchupdatecalls\n        method: POST\n        description: HubSpot Update a Batch of Calls\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: archive\n      path: /archive\n      description: archive operations\n      operations:\n      - name: batcharchivecalls\n        method: POST\n        description: HubSpot Archive a Batch of Calls\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n      description: search operations\n      operations:\n      - name: searchcalls\n        method: POST\n        description: HubSpot Search Calls\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gdpr-delete\n      path: /gdpr-delete\n      description: gdpr-delete operations\n      operations:\n      - name: gdprdeletecall\n        method: POST\n        description: HubSpot Permanently Delete a Call for GDPR Compliance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n  - type: http\n    namespace: engagement-emails-api\n    baseUri: https://api.hubapi.com\n    description: 'The emails engagement API allows you to log and manage email activity records on CRM records in HubSpot.\n      You can create email engagement records to track sent emails, associate them with contacts and '\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: emails\n      path: /emails\n      description: emails operations\n      operations:\n      - name: listemailengagements\n        method: GET\n        description: HubSpot List Email Engagements\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createemailengagement\n        method: POST\n        description: HubSpot Create an Email Engagement\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n   \
  \       type: object\n          value: $.\n      - name: getemailengagement\n        method: GET\n        description: HubSpot Get an Email Engagement\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateemailengagement\n        method: PATCH\n        description: HubSpot Update an Email Engagement\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteemailengagement\n        method: DELETE\n        description: HubSpot Archive an Email Engagement\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: read\n      path: /read\n      description: read operations\n      operations:\n      - name: batchreademailengagements\n        method: POST\n        description: HubSpot Batch Read Email Engagements\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: create\n      path: /create\n      description: create operations\n      operations:\n      - name: batchcreateemailengagements\n        method: POST\n        description: HubSpot Batch Create Email Engagements\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: update\n      path: /update\n      description: update operations\n      operations:\n      - name: batchupdateemailengagements\n        method: POST\n        description: HubSpot Batch Update Email Engagements\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n      description: search operations\n      operations:\n      - name: searchemailengagements\n        method: POST\n        description: HubSpot Search\
  \ Email Engagements\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: associations\n      path: /associations\n      description: associations operations\n      operations:\n      - name: listemailengagementassociations\n        method: GET\n        description: HubSpot List Email Engagement Associations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: '{toObjectId}'\n      path: /{toObjectId}\n      description: '{toObjectId} operations'\n      operations:\n      - name: createemailengagementassociation\n        method: PUT\n        description: HubSpot Create an Email Engagement Association\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteemailengagementassociation\n        method: DELETE\n        description:\
  \ HubSpot Delete an Email Engagement Association\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: engagement-meetings-api\n    baseUri: https://api.hubapi.com\n    description: The meetings endpoints allow you to log and manage meeting engagement records in HubSpot CRM. You can create\n      meeting records, associate them with contacts and companies, and retrieve meeting details a\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: meetings\n      path: /meetings\n      description: meetings operations\n      operations:\n      - name: listmeetings\n        method: GET\n        description: HubSpot List Meetings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createmeeting\n        method: POST\n        description: HubSpot Create\
  \ a Meeting\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getmeeting\n        method: GET\n        description: HubSpot Get a Meeting\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatemeeting\n        method: PATCH\n        description: HubSpot Update a Meeting\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletemeeting\n        method: DELETE\n        description: HubSpot Archive a Meeting\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: read\n      path: /read\n      description: read operations\n      operations:\n      - name: batchreadmeetings\n        method: POST\n        description: HubSpot Batch Read Meetings\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: create\n      path: /create\n      description: create operations\n      operations:\n      - name: batchcreatemeetings\n        method: POST\n        description: HubSpot Batch Create Meetings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: update\n      path: /update\n      description: update operations\n      operations:\n      - name: batchupdatemeetings\n        method: POST\n        description: HubSpot Batch Update Meetings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n      description: search operations\n      operations:\n      - name: searchmeetings\n        method: POST\n        description: HubSpot Search Meetings\n       \
  \ outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: associations\n      path: /associations\n      description: associations operations\n      operations:\n      - name: listmeetingassociations\n        method: GET\n        description: HubSpot List Meeting Associations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: '{toObjectId}'\n      path: /{toObjectId}\n      description: '{toObjectId} operations'\n      operations:\n      - name: createmeetingassociation\n        method: PUT\n        description: HubSpot Create a Meeting Association\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletemeetingassociation\n        method: DELETE\n        description: HubSpot Delete a Meeting Association\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: engagement-tasks-api\n    baseUri: https://api.hubapi.com\n    description: 'The tasks endpoints allow you to create and manage task engagement records in HubSpot CRM. Tasks represent\n      to-do items that can be assigned to users and associated with contacts, companies, and deals '\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: tasks\n      path: /tasks\n      description: tasks operations\n      operations:\n      - name: listtasks\n        method: GET\n        description: HubSpot List Tasks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtask\n        method: POST\n        description: HubSpot Create a Task\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n   \
  \       type: object\n          value: $.\n      - name: gettask\n        method: GET\n        description: HubSpot Get a Task\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatetask\n        method: PATCH\n        description: HubSpot Update a Task\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetask\n        method: DELETE\n        description: HubSpot Archive a Task\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: read\n      path: /read\n      description: read operations\n      operations:\n      - name: batchreadtasks\n        method: POST\n        description: HubSpot Batch Read Tasks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n    - name: create\n      path: /create\n      description: create operations\n      operations:\n      - name: batchcreatetasks\n        method: POST\n        description: HubSpot Batch Create Tasks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: update\n      path: /update\n      description: update operations\n      operations:\n      - name: batchupdatetasks\n        method: POST\n        description: HubSpot Batch Update Tasks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n      description: search operations\n      operations:\n      - name: searchtasks\n        method: POST\n        description: HubSpot Search Tasks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ associations\n      path: /associations\n      description: associations operations\n      operations:\n      - name: listtaskassociations\n        method: GET\n        description: HubSpot List Task Associations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: '{toObjectId}'\n      path: /{toObjectId}\n      description: '{toObjectId} operations'\n      operations:\n      - name: createtaskassociation\n        method: PUT\n        description: HubSpot Create a Task Association\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetaskassociation\n        method: DELETE\n        description: HubSpot Delete a Task Association\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: engagement-notes\n  \
  \  baseUri: https://api.hubapi.com\n    description: HubSpot Engagement Notes API.\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: notes\n      path: /crm/v3/objects/notes\n      description: Note records\n      operations:\n      - name: list-notes\n        method: GET\n        description: List all notes\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results\n        - name: after\n          in: query\n          type: string\n          required: false\n          description: Cursor\n        - name: properties\n          in: query\n          type: string\n          required: false\n          description: Properties\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-note\n        method: POST\n        description: Create a note\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            properties: '{{tools.properties}}'\n    - name: note-by-id\n      path: /crm/v3/objects/notes/{noteId}\n      description: Individual note\n      operations:\n      - name: get-note\n        method: GET\n        description: Get a note\n        inputParameters:\n        - name: noteId\n          in: path\n          type: string\n          required: true\n          description: Note ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-note\n        method: PATCH\n        description: Update a note\n        inputParameters:\n        - name: noteId\n          in: path\n          type: string\n          required: true\n          description: Note ID\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            properties: '{{tools.properties}}'\n      - name: archive-note\n        method: DELETE\n        description: Archive a note\n        inputParameters:\n        - name: noteId\n          in: path\n          type: string\n          required: true\n          description: Note ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: mcp\n    port: 9093\n    namespace: sales-engagement-mcp\n    transport: http\n    description: MCP server for AI-assisted HubSpot Sales Engagement.\n    tools:\n    - name: listcalls\n      description: HubSpot List All Calls\n      hints:\n        readOnly: true\n      call: engagement-calls-api.listcalls\n    - name: createcall\n      description: HubSpot Create a Call\n      hints:\n        readOnly: false\n      call: engagement-calls-api.createcall\n\
  \    - name: getcallbyid\n      description: HubSpot Get a Call by ID\n      hints:\n        readOnly: true\n      call: engagement-calls-api.getcallbyid\n    - name: updatecall\n      description: HubSpot Update a Call\n      hints:\n        readOnly: false\n      call: engagement-calls-api.updatecall\n    - name: archivecall\n      description: HubSpot Archive a Call\n      hints:\n        destructive: true\n      call: engagement-calls-api.archivecall\n    - name: batchcreatecalls\n      description: HubSpot Create a Batch of Calls\n      hints:\n        readOnly: false\n      call: engagement-calls-api.batchcreatecalls\n    - name: batchreadcalls\n      description: HubSpot Read a Batch of Calls\n      hints:\n        readOnly: false\n      call: engagement-calls-api.batchreadcalls\n    - name: batchupdatecalls\n      description: HubSpot Update a Batch of Calls\n      hints:\n        readOnly: false\n      call: engagement-calls-api.batchupdatecalls\n    - name: batcharchivecalls\n\
  \      description: HubSpot Archive a Batch of Calls\n      hints:\n        readOnly: false\n      call: engagement-calls-api.batcharchivecalls\n    - name: searchcalls\n      description: HubSpot Search Calls\n      hints:\n        readOnly: false\n      call: engagement-calls-api.searchcalls\n    - name: gdprdeletecall\n      description: HubSpot Permanently Delete a Call for GDPR Compliance\n      hints:\n        readOnly: false\n      call: engagement-calls-api.gdprdeletecall\n    - name: listemailengagements\n      description: HubSpot List Email Engagements\n      hints:\n        readOnly: true\n      call: engagement-emails-api.listemailengagements\n    - name: createemailengagement\n      description: HubSpot Create an Email Engagement\n      hints:\n        readOnly: false\n      call: engagement-emails-api.createemailengagement\n    - name: getemailengagement\n      description: HubSpot Get an Email Engagement\n      hints:\n        readOnly: true\n      call: engagement-emails-api.getemailengagement\n\
  \    - name: updateemailengagement\n      description: HubSpot Update an Email Engagement\n      hints:\n        readOnly: false\n      call: engagement-emails-api.updateemailengagement\n    - name: deleteemailengagement\n      description: HubSpot Archive an Email Engagement\n      hints:\n        destructive: true\n      call: engagement-emails-api.deleteemailengagement\n    - name: batchreademailengagements\n      description: HubSpot Batch Read Email Engagements\n      hints:\n        readOnly: false\n      call: engagement-emails-api.batchreademailengagements\n    - name: batchcreateemailengagements\n      description: HubSpot Batch Create Email Engagements\n      hints:\n        readOnly: false\n      call: engagement-emails-api.batchcreateemailengagements\n    - name: batchupdateemailengagements\n      description: HubSpot Batch Update Email Engagements\n      hints:\n        readOnly: false\n      call: engagement-emails-api.batchupdateemailengagements\n    - name: searchemailengagements\n\
  \      description: HubSpot Search Email Engagements\n      hints:\n        readOnly: false\n      call: engagement-emails-api.searchemailengagements\n    - name: listemailengagementassociations\n      description: HubSpot List Email Engagement Associations\n      hints:\n        readOnly: true\n      call: engagement-emails-api.listemailengagementassociations\n    - name: createemailengagementassociation\n      description: HubSpot Create an Email Engagement Association\n      hints:\n        readOnly: false\n      call: engagement-emails-api.createemailengagementassociation\n    - name: deleteemailengagementassociation\n      description: HubSpot Delete an Email Engagement Association\n      hints:\n        destructive: true\n      call: engagement-emails-api.deleteemailengagementassociation\n    - name: listmeetings\n      description: HubSpot List Meetings\n      hints:\n        readOnly: true\n      call: engagement-meetings-api.listmeetings\n    - name: createmeeting\n      description:\
  \ HubSpot Create a Meeting\n      hints:\n        readOnly: false\n      call: engagement-meetings-api.createmeeting\n    - name: getmeeting\n      description: HubSpot Get a Meeting\n      hints:\n        readOnly: true\n      call: engagement-meetings-api.getmeeting\n    - name: updatemeeting\n      description: HubSpot Update a Meeting\n      hints:\n        readOnly: false\n      call: engagement-meetings-api.updatemeeting\n    - name: deletemeeting\n      description: HubSpot Archive a Meeting\n      hints:\n        destructive: true\n      call: engagement-meetings-api.deletemeeting\n    - name: batchreadmeetings\n      description: HubSpot Batch Read Meetings\n      hints:\n        readOnly: false\n      call: engagement-meetings-api.batchreadmeetings\n    - name: batchcreatemeetings\n      description: HubSpot Batch Create Meetings\n      hints:\n        readOnly: false\n      call: engagement-meetings-api.batchcreatemeetings\n    - name: batchupdatemeetings\n      description:\
  \ HubSpot Batch Update Meetings\n      hints:\n        readOnly: false\n      call: engagement-meetings-api.batchupdatemeetings\n    - name: searchmeetings\n      description: HubSpot Search Meetings\n      hints:\n        readOnly: false\n      call: engagement-meetings-api.searchmeetings\n    - name: listmeetingassociations\n      description: HubSpot List Meeting Associations\n      hints:\n        readOnly: true\n      call: engagement-meetings-api.listmeetingassociations\n    - name: createmeetingassociation\n      description: HubSpot Create a Meeting Association\n      hints:\n        readOnly: false\n      call: engagement-meetings-api.createmeetingassociation\n    - name: deletemeetingassociation\n      description: HubSpot Delete a Meeting Association\n      hints:\n        destructive: true\n      call: engagement-meetings-api.deletemeetingassociation\n    - name: listtasks\n      description: HubSpot List Tasks\n      hints:\n        readOnly: true\n      call: engagement-tasks-api.listtasks\n\
  \    - name: createtask\n      description: HubSpot Create a Task\n      hints:\n        readOnly: false\n      call: engagement-tasks-api.createtask\n    - name: gettask\n      description: HubSpot Get a Task\n      hints:\n        readOnly: true\n      call: engagement-tasks-api.gettask\n    - name: updatetask\n      description: HubSpot Update a Task\n      hints:\n        readOnly: false\n      call: engagement-tasks-api.updatetask\n    - name: deletetask\n      description: HubSpot Archive a Task\n      hints:\n        destructive: true\n      call: engagement-tasks-api.deletetask\n    - name: batchreadtasks\n      description: HubSpot Batch Read Tasks\n      hints:\n        readOnly: false\n      call: engagement-tasks-api.batchreadtasks\n    - name: batchcreatetasks\n      description: HubSpot Batch Create Tasks\n      hints:\n        readOnly: false\n      call: engagement-tasks-api.batchcreatetasks\n    - name: batchupdatetasks\n      description: HubSpot Batch Update Tasks\n\
  \      hints:\n        readOnly: false\n      call: engagement-tasks-api.batchupdatetasks\n    - name: searchtasks\n      description: HubSpot Search Tasks\n      hints:\n        readOnly: false\n      call: engagement-tasks-api.searchtasks\n    - name: listtaskassociations\n      description: HubSpot List Task Associations\n      hints:\n        readOnly: true\n      call: engagement-tasks-api.listtaskassociations\n    - name: createtaskassociation\n      description: HubSpot Create a Task Association\n      hints:\n        readOnly: false\n      call: engagement-tasks-api.createtaskassociation\n    - name: deletetaskassociation\n      description: HubSpot Delete a Task Association\n      hints:\n        destructive: true\n      call: engagement-tasks-api.deletetaskassociation\n    - name: listnotes\n      description: HubSpot List All Notes\n      hints:\n        readOnly: true\n      call: engagement-notes.listnotes\n    - name: createnote\n      description: HubSpot Create a Note\n\
  \      hints:\n        readOnly: false\n      call: engagement-notes.createnote\n    - name: getnotebyid\n      description: HubSpot Get a Note by ID\n      hints:\n        readOnly: true\n      call: engagement-notes.getnotebyid\n    - name: updatenote\n      description: HubSpot Update a Note\n      hints:\n        readOnly: false\n      call: engagement-notes.updatenote\n    - name: archivenote\n      description: HubSpot Archive a Note\n      hints:\n        destructive: true\n      call: engagement-notes.archivenote\n    - name: batchcreatenotes\n      description: HubSpot Create a Batch of Notes\n      hints:\n        readOnly: false\n      call: engagement-notes.batchcreatenotes\n    - name: batchreadnotes\n      description: HubSpot Read a Batch of Notes\n      hints:\n        readOnly: false\n      call: engagement-notes.batchreadnotes\n    - name: batchupdatenotes\n      description: HubSpot Update a Batch of Notes\n      hints:\n        readOnly: false\n      call: engagement-notes.batchupdatenotes\n\
  \    - name: batcharchivenotes\n      description: HubSpot Archive a Batch of Notes\n      hints:\n        readOnly: false\n      call: engagement-notes.batcharchivenotes\n    - name: searchnotes\n      description: HubSpot Search Notes\n      hints:\n        readOnly: false\n      call: engagement-notes.searchnotes\n    - name: gdprdeletenote\n      description: HubSpot Permanently Delete a Note for GDPR Compliance\n      hints:\n        readOnly: false\n      call: engagement-notes.gdprdeletenote\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hubspot/refs/heads/main/capabilities/sales-engagement.yaml
tags:
- HubSpot
- Sales
- Engagements
- Activities
tools:
- description: HubSpot List All Calls
  hints:
    readOnly: true
  name: listcalls
- description: HubSpot Create a Call
  hints:
    readOnly: false
  name: createcall
- description: HubSpot Get a Call by ID
  hints:
    readOnly: true
  name: getcallbyid
- description: HubSpot Update a Call
  hints:
    readOnly: false
  name: updatecall
- description: HubSpot Archive a Call
  hints:
    destructive: true
  name: archivecall
- description: HubSpot Create a Batch of Calls
  hints:
    readOnly: false
  name: batchcreatecalls
- description: HubSpot Read a Batch of Calls
  hints:
    readOnly: false
  name: batchreadcalls
- description: HubSpot Update a Batch of Calls
  hints:
    readOnly: false
  name: batchupdatecalls
- description: HubSpot Archive a Batch of Calls
  hints:
    readOnly: false
  name: batcharchivecalls
- description: HubSpot Search Calls
  hints:
    readOnly: false
  name: searchcalls
- description: HubSpot Permanently Delete a Call for GDPR Compliance
  hints:
    readOnly: false
  name: gdprdeletecall
- description: HubSpot List Email Engagements
  hints:
    readOnly: true
  name: listemailengagements
- description: HubSpot Create an Email Engagement
  hints:
    readOnly: false
  name: createemailengagement
- description: HubSpot Get an Email Engagement
  hints:
    readOnly: true
  name: getemailengagement
- description: HubSpot Update an Email Engagement
  hints:
    readOnly: false
  name: updateemailengagement
- description: HubSpot Archive an Email Engagement
  hints:
    destructive: true
  name: deleteemailengagement
- description: HubSpot Batch Read Email Engagements
  hints:
    readOnly: false
  name: batchreademailengagements
- description: HubSpot Batch Create Email Engagements
  hints:
    readOnly: false
  name: batchcreateemailengagements
- description: HubSpot Batch Update Email Engagements
  hints:
    readOnly: false
  name: batchupdateemailengagements
- description: HubSpot Search Email Engagements
  hints:
    readOnly: false
  name: searchemailengagements
- description: HubSpot List Email Engagement Associations
  hints:
    readOnly: true
  name: listemailengagementassociations
- description: HubSpot Create an Email Engagement Association
  hints:
    readOnly: false
  name: createemailengagementassociation
- description: HubSpot Delete an Email Engagement Association
  hints:
    destructive: true
  name: deleteemailengagementassociation
- description: HubSpot List Meetings
  hints:
    readOnly: true
  name: listmeetings
- description: HubSpot Create a Meeting
  hints:
    readOnly: false
  name: createmeeting
- description: HubSpot Get a Meeting
  hints:
    readOnly: true
  name: getmeeting
- description: HubSpot Update a Meeting
  hints:
    readOnly: false
  name: updatemeeting
- description: HubSpot Archive a Meeting
  hints:
    destructive: true
  name: deletemeeting
- description: HubSpot Batch Read Meetings
  hints:
    readOnly: false
  name: batchreadmeetings
- description: HubSpot Batch Create Meetings
  hints:
    readOnly: false
  name: batchcreatemeetings
- description: HubSpot Batch Update Meetings
  hints:
    readOnly: false
  name: batchupdatemeetings
- description: HubSpot Search Meetings
  hints:
    readOnly: false
  name: searchmeetings
- description: HubSpot List Meeting Associations
  hints:
    readOnly: true
  name: listmeetingassociations
- description: HubSpot Create a Meeting Association
  hints:
    readOnly: false
  name: createmeetingassociation
- description: HubSpot Delete a Meeting Association
  hints:
    destructive: true
  name: deletemeetingassociation
- description: HubSpot List Tasks
  hints:
    readOnly: true
  name: listtasks
- description: HubSpot Create a Task
  hints:
    readOnly: false
  name: createtask
- description: HubSpot Get a Task
  hints:
    readOnly: true
  name: gettask
- description: HubSpot Update a Task
  hints:
    readOnly: false
  name: updatetask
- description: HubSpot Archive a Task
  hints:
    destructive: true
  name: deletetask
- description: HubSpot Batch Read Tasks
  hints:
    readOnly: false
  name: batchreadtasks
- description: HubSpot Batch Create Tasks
  hints:
    readOnly: false
  name: batchcreatetasks
- description: HubSpot Batch Update Tasks
  hints:
    readOnly: false
  name: batchupdatetasks
- description: HubSpot Search Tasks
  hints:
    readOnly: false
  name: searchtasks
- description: HubSpot List Task Associations
  hints:
    readOnly: true
  name: listtaskassociations
- description: HubSpot Create a Task Association
  hints:
    readOnly: false
  name: createtaskassociation
- description: HubSpot Delete a Task Association
  hints:
    destructive: true
  name: deletetaskassociation
- description: HubSpot List All Notes
  hints:
    readOnly: true
  name: listnotes
- description: HubSpot Create a Note
  hints:
    readOnly: false
  name: createnote
- description: HubSpot Get a Note by ID
  hints:
    readOnly: true
  name: getnotebyid
- description: HubSpot Update a Note
  hints:
    readOnly: false
  name: updatenote
- description: HubSpot Archive a Note
  hints:
    destructive: true
  name: archivenote
- description: HubSpot Create a Batch of Notes
  hints:
    readOnly: false
  name: batchcreatenotes
- description: HubSpot Read a Batch of Notes
  hints:
    readOnly: false
  name: batchreadnotes
- description: HubSpot Update a Batch of Notes
  hints:
    readOnly: false
  name: batchupdatenotes
- description: HubSpot Archive a Batch of Notes
  hints:
    readOnly: false
  name: batcharchivenotes
- description: HubSpot Search Notes
  hints:
    readOnly: false
  name: searchnotes
- description: HubSpot Permanently Delete a Note for GDPR Compliance
  hints:
    readOnly: false
  name: gdprdeletenote
---
