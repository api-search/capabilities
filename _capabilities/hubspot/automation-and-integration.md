---
consumed_apis:
- custom-workflow-actions-api
- oauth-api
- crm-feature-flags-api
- conversations-api
description: Workflow automation and integration management combining custom workflow actions, OAuth, feature flags, and conversations.
layout: capability
name: HubSpot Automation and Integration
operations: []
personas: []
provider_name: HubSpot
provider_slug: hubspot
search_terms:
- hubspot retrieve a specific function
- hubspot create or update a function
- getaccesstokenmetadata
- customer service
- hubspot list action functions
- commerce
- hubspot delete a specific function
- listactionfunctions
- hubspot create or refresh an access token
- createorrefreshaccesstoken
- createactiondefinition
- archivethread
- email marketing
- hubspot delete a feature flag
- hubspot delete a portal flag state
- listinboxes
- listthreads
- hubspot update an action definition
- archiveactiondefinitionbyid
- hubspot retrieve refresh token metadata
- hubspot batch create or update portal flag states
- analytics
- hubspot complete a single callback
- getactionfunctionbytype
- hubspot complete multiple callbacks
- automation
- updatethread
- hubspot retrieve an inbox
- hubspot list channels
- batchdeleteportalflagstates
- hubspot send a message
- integration
- hubspot list conversation threads
- content
- listactiondefinitionrevisions
- deleteportalflagstate
- getrefreshtokenmetadata
- hubspot retrieve an action definition
- getthreadbyid
- getactionfunctionbyid
- completecallback
- hubspot create an action definition
- oauth
- hubspot retrieve an actor
- sendmessage
- hubspot list action definitions
- hubspot retrieve function by type
- marketing
- getmessagebyid
- marketing automation
- operations
- getactiondefinitionrevisionbyid
- hubspot archive a thread
- deleteapplicationfeatureflag
- hubspot list thread messages
- updateactiondefinitionbyid
- hubspot retrieve a thread
- revokerefreshtoken
- hubspot create or update a feature flag
- hubspot
- sales
- getactorbyid
- hubspot list portal flag states
- hubspot delete a function by type
- getportalflagstate
- hubspot list actors
- hubspot list all inboxes
- getactiondefinitionbyid
- hubspot retrieve a portal flag state
- hubspot batch delete portal flag states
- setportalflagstate
- hubspot archive an action definition
- upsertapplicationfeatureflag
- hubspot set a portal flag state
- batchupsertportalflagstates
- batchcompletecallbacks
- deleteactionfunctionbytype
- hubspot retrieve a message
- listactiondefinitions
- crm
- getapplicationfeatureflag
- deleteactionfunctionbyid
- listthreadmessages
- hubspot revoke a refresh token
- hubspot retrieve a specific revision
- upsertactionfunction
- hubspot update a thread
- hubspot retrieve access token metadata
- hubspot retrieve a feature flag configuration
- listportalflagstates
- getinboxbyid
- listactors
- hubspot list definition revisions
- listchannels
slug: automation-and-integration
tags:
- HubSpot
- Automation
- Integration
- OAuth
tools:
- description: HubSpot Complete a Single Callback
  hints:
    readOnly: false
  name: completecallback
- description: HubSpot Complete Multiple Callbacks
  hints:
    readOnly: false
  name: batchcompletecallbacks
- description: HubSpot List Action Definitions
  hints:
    readOnly: true
  name: listactiondefinitions
- description: HubSpot Create an Action Definition
  hints:
    readOnly: false
  name: createactiondefinition
- description: HubSpot Retrieve an Action Definition
  hints:
    readOnly: true
  name: getactiondefinitionbyid
- description: HubSpot Update an Action Definition
  hints:
    readOnly: false
  name: updateactiondefinitionbyid
- description: HubSpot Archive an Action Definition
  hints:
    destructive: true
  name: archiveactiondefinitionbyid
- description: HubSpot List Action Functions
  hints:
    readOnly: true
  name: listactionfunctions
- description: HubSpot Retrieve Function by Type
  hints:
    readOnly: true
  name: getactionfunctionbytype
- description: HubSpot Create or Update a Function
  hints:
    readOnly: false
  name: upsertactionfunction
- description: HubSpot Delete a Function by Type
  hints:
    destructive: true
  name: deleteactionfunctionbytype
- description: HubSpot Retrieve a Specific Function
  hints:
    readOnly: true
  name: getactionfunctionbyid
- description: HubSpot Delete a Specific Function
  hints:
    destructive: true
  name: deleteactionfunctionbyid
- description: HubSpot List Definition Revisions
  hints:
    readOnly: true
  name: listactiondefinitionrevisions
- description: HubSpot Retrieve a Specific Revision
  hints:
    readOnly: true
  name: getactiondefinitionrevisionbyid
- description: HubSpot Retrieve Access Token Metadata
  hints:
    readOnly: true
  name: getaccesstokenmetadata
- description: HubSpot Retrieve Refresh Token Metadata
  hints:
    readOnly: true
  name: getrefreshtokenmetadata
- description: HubSpot Revoke a Refresh Token
  hints:
    destructive: true
  name: revokerefreshtoken
- description: HubSpot Create or Refresh an Access Token
  hints:
    readOnly: false
  name: createorrefreshaccesstoken
- description: HubSpot Retrieve a Feature Flag Configuration
  hints:
    readOnly: true
  name: getapplicationfeatureflag
- description: HubSpot Create or Update a Feature Flag
  hints:
    readOnly: false
  name: upsertapplicationfeatureflag
- description: HubSpot Delete a Feature Flag
  hints:
    destructive: true
  name: deleteapplicationfeatureflag
- description: HubSpot List Portal Flag States
  hints:
    readOnly: true
  name: listportalflagstates
- description: HubSpot Retrieve a Portal Flag State
  hints:
    readOnly: true
  name: getportalflagstate
- description: HubSpot Set a Portal Flag State
  hints:
    readOnly: false
  name: setportalflagstate
- description: HubSpot Delete a Portal Flag State
  hints:
    destructive: true
  name: deleteportalflagstate
- description: HubSpot Batch Create or Update Portal Flag States
  hints:
    readOnly: false
  name: batchupsertportalflagstates
- description: HubSpot Batch Delete Portal Flag States
  hints:
    readOnly: false
  name: batchdeleteportalflagstates
- description: HubSpot List All Inboxes
  hints:
    readOnly: true
  name: listinboxes
- description: HubSpot Retrieve an Inbox
  hints:
    readOnly: true
  name: getinboxbyid
- description: HubSpot List Conversation Threads
  hints:
    readOnly: true
  name: listthreads
- description: HubSpot Retrieve a Thread
  hints:
    readOnly: true
  name: getthreadbyid
- description: HubSpot Update a Thread
  hints:
    readOnly: false
  name: updatethread
- description: HubSpot Archive a Thread
  hints:
    destructive: true
  name: archivethread
- description: HubSpot List Thread Messages
  hints:
    readOnly: true
  name: listthreadmessages
- description: HubSpot Send a Message
  hints:
    readOnly: false
  name: sendmessage
- description: HubSpot Retrieve a Message
  hints:
    readOnly: true
  name: getmessagebyid
- description: HubSpot List Channels
  hints:
    readOnly: true
  name: listchannels
- description: HubSpot List Actors
  hints:
    readOnly: true
  name: listactors
- description: HubSpot Retrieve an Actor
  hints:
    readOnly: true
  name: getactorbyid
---
