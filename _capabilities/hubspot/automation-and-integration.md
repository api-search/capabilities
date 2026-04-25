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
- hubspot list conversation threads
- hubspot list thread messages
- createorrefreshaccesstoken
- hubspot list actors
- hubspot retrieve an actor
- hubspot revoke a refresh token
- getrefreshtokenmetadata
- customer service
- archivethread
- upsertactionfunction
- listthreads
- hubspot retrieve a specific revision
- hubspot retrieve an inbox
- hubspot list channels
- deleteactionfunctionbytype
- deleteactionfunctionbyid
- hubspot delete a portal flag state
- hubspot delete a function by type
- hubspot complete a single callback
- marketing
- sendmessage
- hubspot create an action definition
- hubspot create or refresh an access token
- analytics
- getthreadbyid
- integration
- hubspot
- hubspot archive an action definition
- deleteapplicationfeatureflag
- hubspot list portal flag states
- getapplicationfeatureflag
- operations
- hubspot complete multiple callbacks
- updatethread
- hubspot batch create or update portal flag states
- createactiondefinition
- hubspot archive a thread
- getactionfunctionbytype
- listactors
- batchcompletecallbacks
- crm
- listinboxes
- commerce
- listthreadmessages
- getportalflagstate
- hubspot list action functions
- hubspot create or update a feature flag
- hubspot set a portal flag state
- hubspot retrieve a message
- hubspot retrieve a specific function
- marketing automation
- hubspot create or update a function
- getmessagebyid
- hubspot delete a specific function
- revokerefreshtoken
- listactionfunctions
- hubspot retrieve an action definition
- getactorbyid
- getactiondefinitionbyid
- hubspot retrieve a portal flag state
- hubspot update a thread
- getactionfunctionbyid
- updateactiondefinitionbyid
- hubspot retrieve access token metadata
- setportalflagstate
- hubspot retrieve function by type
- batchupsertportalflagstates
- batchdeleteportalflagstates
- sales
- hubspot batch delete portal flag states
- archiveactiondefinitionbyid
- listactiondefinitions
- hubspot list all inboxes
- hubspot retrieve refresh token metadata
- hubspot retrieve a thread
- hubspot list definition revisions
- email marketing
- getactiondefinitionrevisionbyid
- oauth
- listportalflagstates
- completecallback
- hubspot send a message
- content
- hubspot list action definitions
- listactiondefinitionrevisions
- getaccesstokenmetadata
- deleteportalflagstate
- automation
- hubspot retrieve a feature flag configuration
- hubspot update an action definition
- upsertapplicationfeatureflag
- hubspot delete a feature flag
- listchannels
- getinboxbyid
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
