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
- hubspot update an email engagement
- hubspot archive a batch of calls
- hubspot
- hubspot list meeting associations
- searchmeetings
- hubspot create an email engagement association
- batchupdatetasks
- createtaskassociation
- listtasks
- hubspot create a note
- hubspot batch create tasks
- createcall
- batchcreatemeetings
- hubspot batch read meetings
- commerce
- batchreadcalls
- createemailengagement
- hubspot update a task
- archivenote
- hubspot search calls
- createmeetingassociation
- listmeetingassociations
- listnotes
- gdprdeletecall
- sales
- hubspot get an email engagement
- deletemeeting
- crm
- archivecall
- operations
- hubspot update a meeting
- hubspot batch create meetings
- hubspot archive an email engagement
- hubspot list email engagement associations
- batchreademailengagements
- createemailengagementassociation
- hubspot archive a call
- hubspot create a task association
- updatenote
- email marketing
- hubspot delete a task association
- hubspot batch update email engagements
- hubspot archive a batch of notes
- createmeeting
- gettask
- activities
- gdprdeletenote
- hubspot get a note by id
- engagements
- deleteemailengagementassociation
- getcallbyid
- hubspot update a call
- hubspot update a batch of notes
- createnote
- batchupdatenotes
- hubspot create a task
- hubspot get a meeting
- hubspot permanently delete a note for gdpr compliance
- hubspot permanently delete a call for gdpr compliance
- updatecall
- deletetaskassociation
- hubspot read a batch of calls
- hubspot list meetings
- hubspot read a batch of notes
- analytics
- hubspot archive a task
- batchreadnotes
- hubspot delete an email engagement association
- hubspot list email engagements
- hubspot archive a meeting
- searchtasks
- marketing
- listmeetings
- hubspot create a meeting
- listemailengagements
- hubspot archive a note
- getemailengagement
- batchupdatemeetings
- hubspot get a call by id
- searchnotes
- content
- hubspot update a batch of calls
- hubspot list tasks
- customer service
- hubspot create an email engagement
- hubspot update a note
- hubspot batch update tasks
- hubspot batch update meetings
- hubspot list all notes
- deletemeetingassociation
- hubspot create a batch of calls
- batchcreatetasks
- listcalls
- hubspot create a call
- batchcreateemailengagements
- hubspot batch create email engagements
- batcharchivenotes
- hubspot search notes
- hubspot search meetings
- hubspot get a task
- marketing automation
- batchcreatecalls
- hubspot list task associations
- updateemailengagement
- updatemeeting
- hubspot batch read email engagements
- searchemailengagements
- listtaskassociations
- batchupdatecalls
- batchcreatenotes
- searchcalls
- createtask
- batchreadmeetings
- hubspot batch read tasks
- hubspot create a batch of notes
- listemailengagementassociations
- batchreadtasks
- hubspot search email engagements
- hubspot create a meeting association
- deleteemailengagement
- updatetask
- deletetask
- getnotebyid
- getmeeting
- batcharchivecalls
- hubspot delete a meeting association
- batchupdateemailengagements
- hubspot list all calls
- hubspot search tasks
slug: sales-engagement
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
