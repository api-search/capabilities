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
- hubspot update an action definition
- listactors
- hubspot update a thread
- getaccesstokenmetadata
- batchcompletecallbacks
- operations
- hubspot revoke a refresh token
- hubspot delete a portal flag state
- hubspot create an action definition
- getactiondefinitionrevisionbyid
- marketing automation
- getactiondefinitionbyid
- hubspot retrieve an action definition
- hubspot list portal flag states
- marketing
- hubspot delete a specific function
- hubspot set a portal flag state
- hubspot list all inboxes
- batchupsertportalflagstates
- hubspot retrieve access token metadata
- email marketing
- getapplicationfeatureflag
- getportalflagstate
- updatethread
- hubspot complete multiple callbacks
- hubspot delete a feature flag
- hubspot retrieve a specific revision
- content
- sales
- archiveactiondefinitionbyid
- archivethread
- crm
- deleteactionfunctionbytype
- getthreadbyid
- hubspot list action definitions
- hubspot retrieve a portal flag state
- deleteactionfunctionbyid
- hubspot complete a single callback
- getactionfunctionbyid
- listthreads
- hubspot archive an action definition
- customer service
- revokerefreshtoken
- batchdeleteportalflagstates
- createactiondefinition
- hubspot list definition revisions
- upsertactionfunction
- getactorbyid
- upsertapplicationfeatureflag
- listactiondefinitions
- sendmessage
- getrefreshtokenmetadata
- completecallback
- deleteportalflagstate
- hubspot retrieve a feature flag configuration
- createorrefreshaccesstoken
- listchannels
- hubspot retrieve an inbox
- hubspot batch create or update portal flag states
- setportalflagstate
- getmessagebyid
- hubspot create or refresh an access token
- updateactiondefinitionbyid
- getinboxbyid
- hubspot create or update a feature flag
- hubspot list actors
- hubspot archive a thread
- hubspot list conversation threads
- hubspot create or update a function
- automation
- hubspot list channels
- commerce
- analytics
- hubspot list thread messages
- listthreadmessages
- hubspot retrieve a message
- hubspot delete a function by type
- hubspot list action functions
- integration
- listinboxes
- hubspot batch delete portal flag states
- listactionfunctions
- hubspot
- hubspot retrieve a thread
- deleteapplicationfeatureflag
- hubspot retrieve an actor
- getactionfunctionbytype
- hubspot send a message
- hubspot retrieve a specific function
- listactiondefinitionrevisions
- hubspot retrieve refresh token metadata
- hubspot retrieve function by type
- oauth
- listportalflagstates
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
