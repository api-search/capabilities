---
categories:
- crm-sales
consumed_apis:
- engagement-calls-api
- engagement-emails-api
- engagement-meetings-api
- engagement-tasks-api
- engagement-notes
description: Sales activity tracking workflow for calls, emails, meetings, tasks, and notes.
layout: capability
name: HubSpot Sales Engagement
operations: []
personas: []
provider_name: HubSpot
provider_slug: hubspot
search_terms:
- batchupdatenotes
- searchcalls
- listtaskassociations
- hubspot search email engagements
- batchreademailengagements
- hubspot update a batch of notes
- content
- createtaskassociation
- batchcreatecalls
- hubspot update a task
- hubspot archive a note
- hubspot create a meeting association
- hubspot update a batch of calls
- crm
- createmeetingassociation
- marketing automation
- searchemailengagements
- hubspot batch read meetings
- gettask
- batchupdatetasks
- hubspot batch read email engagements
- hubspot search notes
- batchcreatemeetings
- batchreadcalls
- updatecall
- hubspot batch create meetings
- listnotes
- hubspot permanently delete a note for gdpr compliance
- hubspot archive an email engagement
- hubspot archive a meeting
- deletemeeting
- createcall
- hubspot search meetings
- operations
- batchcreatenotes
- archivenote
- listmeetingassociations
- updatemeeting
- createmeeting
- deleteemailengagementassociation
- hubspot batch read tasks
- hubspot list tasks
- batchreadmeetings
- updatetask
- hubspot create a meeting
- sales
- listcalls
- hubspot read a batch of notes
- updateemailengagement
- hubspot archive a task
- archivecall
- batchreadtasks
- hubspot batch create tasks
- hubspot permanently delete a call for gdpr compliance
- hubspot list email engagement associations
- hubspot create a batch of notes
- getmeeting
- searchnotes
- hubspot get a meeting
- hubspot get a call by id
- hubspot list meetings
- searchmeetings
- deleteemailengagement
- batchupdateemailengagements
- hubspot list all calls
- batcharchivenotes
- hubspot list all notes
- hubspot list task associations
- gdprdeletecall
- getcallbyid
- engagements
- hubspot create a task
- deletetask
- hubspot delete a task association
- listtasks
- hubspot create an email engagement association
- batchcreatetasks
- hubspot batch update email engagements
- email marketing
- activities
- hubspot archive a batch of calls
- hubspot update an email engagement
- deletetaskassociation
- getnotebyid
- batchupdatecalls
- batchreadnotes
- hubspot get a note by id
- hubspot get an email engagement
- hubspot archive a batch of notes
- listemailengagements
- analytics
- createtask
- hubspot list meeting associations
- hubspot search calls
- hubspot create a batch of calls
- hubspot delete a meeting association
- gdprdeletenote
- hubspot create an email engagement
- hubspot list email engagements
- marketing
- batcharchivecalls
- createemailengagementassociation
- listemailengagementassociations
- hubspot get a task
- searchtasks
- hubspot batch update tasks
- hubspot create a note
- hubspot batch create email engagements
- hubspot read a batch of calls
- getemailengagement
- hubspot update a call
- hubspot archive a call
- hubspot search tasks
- commerce
- hubspot delete an email engagement association
- customer service
- updatenote
- hubspot create a call
- batchcreateemailengagements
- hubspot batch update meetings
- createemailengagement
- hubspot
- hubspot create a task association
- hubspot update a note
- listmeetings
- hubspot update a meeting
- createnote
- batchupdatemeetings
- deletemeetingassociation
slug: sales-engagement
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: HubSpot Sales Engagement\n  description: Sales activity tracking workflow for calls, emails, meetings, tasks, and notes.\n  tags:\n  - HubSpot\n  - Sales\n  - Engagements\n  - Activities\n  created: '2026-04-18'\n  modified: '2026-04-18'\nbinds:\n- namespace: env\n  keys:\n    HUBSPOT_ACCESS_TOKEN: HUBSPOT_ACCESS_TOKEN\ncapability:\n  consumes:\n  - import: engagement-calls-api\n    location: ./shared/engagement-calls-api.yaml\n  - import: engagement-emails-api\n    location: ./shared/engagement-emails-api.yaml\n  - import: engagement-meetings-api\n    location: ./shared/engagement-meetings-api.yaml\n  - import: engagement-tasks-api\n    location: ./shared/engagement-tasks-api.yaml\n  - import: engagement-notes\n    location: ./shared/engagement-notes.yaml\n  exposes:\n  - type: mcp\n    port: 9093\n    namespace: sales-engagement-mcp\n    transport: http\n    description: MCP server for AI-assisted HubSpot Sales Engagement.\n    tools:\n\
  \    - name: listcalls\n      description: HubSpot List All Calls\n      hints:\n        readOnly: true\n      call: engagement-calls-api.listcalls\n    - name: createcall\n      description: HubSpot Create a Call\n      hints:\n        readOnly: false\n      call: engagement-calls-api.createcall\n    - name: getcallbyid\n      description: HubSpot Get a Call by ID\n      hints:\n        readOnly: true\n      call: engagement-calls-api.getcallbyid\n    - name: updatecall\n      description: HubSpot Update a Call\n      hints:\n        readOnly: false\n      call: engagement-calls-api.updatecall\n    - name: archivecall\n      description: HubSpot Archive a Call\n      hints:\n        destructive: true\n      call: engagement-calls-api.archivecall\n    - name: batchcreatecalls\n      description: HubSpot Create a Batch of Calls\n      hints:\n        readOnly: false\n      call: engagement-calls-api.batchcreatecalls\n    - name: batchreadcalls\n      description: HubSpot Read a Batch of\
  \ Calls\n      hints:\n        readOnly: false\n      call: engagement-calls-api.batchreadcalls\n    - name: batchupdatecalls\n      description: HubSpot Update a Batch of Calls\n      hints:\n        readOnly: false\n      call: engagement-calls-api.batchupdatecalls\n    - name: batcharchivecalls\n      description: HubSpot Archive a Batch of Calls\n      hints:\n        readOnly: false\n      call: engagement-calls-api.batcharchivecalls\n    - name: searchcalls\n      description: HubSpot Search Calls\n      hints:\n        readOnly: false\n      call: engagement-calls-api.searchcalls\n    - name: gdprdeletecall\n      description: HubSpot Permanently Delete a Call for GDPR Compliance\n      hints:\n        readOnly: false\n      call: engagement-calls-api.gdprdeletecall\n    - name: listemailengagements\n      description: HubSpot List Email Engagements\n      hints:\n        readOnly: true\n      call: engagement-emails-api.listemailengagements\n    - name: createemailengagement\n\
  \      description: HubSpot Create an Email Engagement\n      hints:\n        readOnly: false\n      call: engagement-emails-api.createemailengagement\n    - name: getemailengagement\n      description: HubSpot Get an Email Engagement\n      hints:\n        readOnly: true\n      call: engagement-emails-api.getemailengagement\n    - name: updateemailengagement\n      description: HubSpot Update an Email Engagement\n      hints:\n        readOnly: false\n      call: engagement-emails-api.updateemailengagement\n    - name: deleteemailengagement\n      description: HubSpot Archive an Email Engagement\n      hints:\n        destructive: true\n      call: engagement-emails-api.deleteemailengagement\n    - name: batchreademailengagements\n      description: HubSpot Batch Read Email Engagements\n      hints:\n        readOnly: false\n      call: engagement-emails-api.batchreademailengagements\n    - name: batchcreateemailengagements\n      description: HubSpot Batch Create Email Engagements\n\
  \      hints:\n        readOnly: false\n      call: engagement-emails-api.batchcreateemailengagements\n    - name: batchupdateemailengagements\n      description: HubSpot Batch Update Email Engagements\n      hints:\n        readOnly: false\n      call: engagement-emails-api.batchupdateemailengagements\n    - name: searchemailengagements\n      description: HubSpot Search Email Engagements\n      hints:\n        readOnly: false\n      call: engagement-emails-api.searchemailengagements\n    - name: listemailengagementassociations\n      description: HubSpot List Email Engagement Associations\n      hints:\n        readOnly: true\n      call: engagement-emails-api.listemailengagementassociations\n    - name: createemailengagementassociation\n      description: HubSpot Create an Email Engagement Association\n      hints:\n        readOnly: false\n      call: engagement-emails-api.createemailengagementassociation\n    - name: deleteemailengagementassociation\n      description: HubSpot Delete\
  \ an Email Engagement Association\n      hints:\n        destructive: true\n      call: engagement-emails-api.deleteemailengagementassociation\n    - name: listmeetings\n      description: HubSpot List Meetings\n      hints:\n        readOnly: true\n      call: engagement-meetings-api.listmeetings\n    - name: createmeeting\n      description: HubSpot Create a Meeting\n      hints:\n        readOnly: false\n      call: engagement-meetings-api.createmeeting\n    - name: getmeeting\n      description: HubSpot Get a Meeting\n      hints:\n        readOnly: true\n      call: engagement-meetings-api.getmeeting\n    - name: updatemeeting\n      description: HubSpot Update a Meeting\n      hints:\n        readOnly: false\n      call: engagement-meetings-api.updatemeeting\n    - name: deletemeeting\n      description: HubSpot Archive a Meeting\n      hints:\n        destructive: true\n      call: engagement-meetings-api.deletemeeting\n    - name: batchreadmeetings\n      description: HubSpot Batch\
  \ Read Meetings\n      hints:\n        readOnly: false\n      call: engagement-meetings-api.batchreadmeetings\n    - name: batchcreatemeetings\n      description: HubSpot Batch Create Meetings\n      hints:\n        readOnly: false\n      call: engagement-meetings-api.batchcreatemeetings\n    - name: batchupdatemeetings\n      description: HubSpot Batch Update Meetings\n      hints:\n        readOnly: false\n      call: engagement-meetings-api.batchupdatemeetings\n    - name: searchmeetings\n      description: HubSpot Search Meetings\n      hints:\n        readOnly: false\n      call: engagement-meetings-api.searchmeetings\n    - name: listmeetingassociations\n      description: HubSpot List Meeting Associations\n      hints:\n        readOnly: true\n      call: engagement-meetings-api.listmeetingassociations\n    - name: createmeetingassociation\n      description: HubSpot Create a Meeting Association\n      hints:\n        readOnly: false\n      call: engagement-meetings-api.createmeetingassociation\n\
  \    - name: deletemeetingassociation\n      description: HubSpot Delete a Meeting Association\n      hints:\n        destructive: true\n      call: engagement-meetings-api.deletemeetingassociation\n    - name: listtasks\n      description: HubSpot List Tasks\n      hints:\n        readOnly: true\n      call: engagement-tasks-api.listtasks\n    - name: createtask\n      description: HubSpot Create a Task\n      hints:\n        readOnly: false\n      call: engagement-tasks-api.createtask\n    - name: gettask\n      description: HubSpot Get a Task\n      hints:\n        readOnly: true\n      call: engagement-tasks-api.gettask\n    - name: updatetask\n      description: HubSpot Update a Task\n      hints:\n        readOnly: false\n      call: engagement-tasks-api.updatetask\n    - name: deletetask\n      description: HubSpot Archive a Task\n      hints:\n        destructive: true\n      call: engagement-tasks-api.deletetask\n    - name: batchreadtasks\n      description: HubSpot Batch Read\
  \ Tasks\n      hints:\n        readOnly: false\n      call: engagement-tasks-api.batchreadtasks\n    - name: batchcreatetasks\n      description: HubSpot Batch Create Tasks\n      hints:\n        readOnly: false\n      call: engagement-tasks-api.batchcreatetasks\n    - name: batchupdatetasks\n      description: HubSpot Batch Update Tasks\n      hints:\n        readOnly: false\n      call: engagement-tasks-api.batchupdatetasks\n    - name: searchtasks\n      description: HubSpot Search Tasks\n      hints:\n        readOnly: false\n      call: engagement-tasks-api.searchtasks\n    - name: listtaskassociations\n      description: HubSpot List Task Associations\n      hints:\n        readOnly: true\n      call: engagement-tasks-api.listtaskassociations\n    - name: createtaskassociation\n      description: HubSpot Create a Task Association\n      hints:\n        readOnly: false\n      call: engagement-tasks-api.createtaskassociation\n    - name: deletetaskassociation\n      description: HubSpot\
  \ Delete a Task Association\n      hints:\n        destructive: true\n      call: engagement-tasks-api.deletetaskassociation\n    - name: listnotes\n      description: HubSpot List All Notes\n      hints:\n        readOnly: true\n      call: engagement-notes.listnotes\n    - name: createnote\n      description: HubSpot Create a Note\n      hints:\n        readOnly: false\n      call: engagement-notes.createnote\n    - name: getnotebyid\n      description: HubSpot Get a Note by ID\n      hints:\n        readOnly: true\n      call: engagement-notes.getnotebyid\n    - name: updatenote\n      description: HubSpot Update a Note\n      hints:\n        readOnly: false\n      call: engagement-notes.updatenote\n    - name: archivenote\n      description: HubSpot Archive a Note\n      hints:\n        destructive: true\n      call: engagement-notes.archivenote\n    - name: batchcreatenotes\n      description: HubSpot Create a Batch of Notes\n      hints:\n        readOnly: false\n      call: engagement-notes.batchcreatenotes\n\
  \    - name: batchreadnotes\n      description: HubSpot Read a Batch of Notes\n      hints:\n        readOnly: false\n      call: engagement-notes.batchreadnotes\n    - name: batchupdatenotes\n      description: HubSpot Update a Batch of Notes\n      hints:\n        readOnly: false\n      call: engagement-notes.batchupdatenotes\n    - name: batcharchivenotes\n      description: HubSpot Archive a Batch of Notes\n      hints:\n        readOnly: false\n      call: engagement-notes.batcharchivenotes\n    - name: searchnotes\n      description: HubSpot Search Notes\n      hints:\n        readOnly: false\n      call: engagement-notes.searchnotes\n    - name: gdprdeletenote\n      description: HubSpot Permanently Delete a Note for GDPR Compliance\n      hints:\n        readOnly: false\n      call: engagement-notes.gdprdeletenote\n"
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
