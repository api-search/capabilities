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
- hubspot archive a meeting
- listtaskassociations
- batchupdateemailengagements
- hubspot create a call
- deletetask
- batchreadnotes
- batchupdatemeetings
- hubspot batch read meetings
- hubspot create an email engagement association
- getcallbyid
- batchcreatenotes
- customer service
- hubspot list email engagements
- batchreademailengagements
- updateemailengagement
- hubspot create a batch of notes
- hubspot archive a batch of notes
- hubspot create a note
- createemailengagementassociation
- archivecall
- batchcreatecalls
- hubspot search calls
- hubspot get a note by id
- hubspot get a meeting
- hubspot batch create tasks
- deletemeeting
- hubspot archive an email engagement
- createmeetingassociation
- batchcreatemeetings
- batcharchivecalls
- listemailengagementassociations
- batchupdatetasks
- searchtasks
- gdprdeletecall
- gdprdeletenote
- searchmeetings
- hubspot permanently delete a call for gdpr compliance
- getnotebyid
- hubspot search notes
- hubspot batch read tasks
- createemailengagement
- createnote
- hubspot list all notes
- hubspot search meetings
- batchreadtasks
- searchemailengagements
- content
- createtaskassociation
- hubspot create a batch of calls
- searchnotes
- hubspot update a call
- hubspot batch update meetings
- hubspot archive a task
- hubspot read a batch of calls
- hubspot read a batch of notes
- listnotes
- commerce
- updatecall
- deletetaskassociation
- hubspot update a batch of notes
- deleteemailengagement
- hubspot batch read email engagements
- email marketing
- createmeeting
- hubspot archive a batch of calls
- hubspot list task associations
- hubspot update a note
- hubspot get an email engagement
- hubspot search tasks
- batchupdatecalls
- hubspot archive a note
- batcharchivenotes
- updatetask
- activities
- listmeetings
- gettask
- deleteemailengagementassociation
- batchreadmeetings
- hubspot delete an email engagement association
- batchcreateemailengagements
- hubspot list meeting associations
- createtask
- hubspot create a task association
- hubspot
- hubspot batch create meetings
- marketing automation
- crm
- listemailengagements
- hubspot delete a meeting association
- hubspot get a task
- batchreadcalls
- hubspot permanently delete a note for gdpr compliance
- hubspot archive a call
- hubspot get a call by id
- archivenote
- hubspot create a task
- analytics
- hubspot update a meeting
- hubspot list all calls
- batchcreatetasks
- batchupdatenotes
- hubspot list email engagement associations
- updatemeeting
- hubspot batch update email engagements
- hubspot list meetings
- hubspot create a meeting association
- hubspot batch create email engagements
- getmeeting
- updatenote
- listtasks
- hubspot update a task
- hubspot update an email engagement
- hubspot delete a task association
- deletemeetingassociation
- operations
- getemailengagement
- hubspot batch update tasks
- hubspot create an email engagement
- marketing
- hubspot search email engagements
- listcalls
- sales
- searchcalls
- hubspot create a meeting
- hubspot update a batch of calls
- createcall
- hubspot list tasks
- listmeetingassociations
- engagements
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
