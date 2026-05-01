---
categories:
- automation
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
- hubspot set a portal flag state
- hubspot list thread messages
- hubspot list action functions
- hubspot retrieve a feature flag configuration
- completecallback
- hubspot send a message
- getapplicationfeatureflag
- hubspot list portal flag states
- setportalflagstate
- marketing
- createactiondefinition
- hubspot list channels
- listactiondefinitionrevisions
- sendmessage
- email marketing
- getrefreshtokenmetadata
- createorrefreshaccesstoken
- sales
- listinboxes
- oauth
- hubspot revoke a refresh token
- hubspot list actors
- hubspot delete a feature flag
- listactors
- getactionfunctionbytype
- hubspot create or refresh an access token
- batchcompletecallbacks
- hubspot list conversation threads
- customer service
- hubspot
- integration
- hubspot create or update a function
- hubspot create an action definition
- deleteactionfunctionbytype
- hubspot retrieve access token metadata
- batchupsertportalflagstates
- getmessagebyid
- analytics
- listthreads
- hubspot delete a specific function
- updatethread
- hubspot create or update a feature flag
- hubspot list action definitions
- hubspot retrieve an action definition
- listactiondefinitions
- hubspot list definition revisions
- listactionfunctions
- archiveactiondefinitionbyid
- commerce
- deleteactionfunctionbyid
- hubspot retrieve a specific revision
- hubspot retrieve a thread
- marketing automation
- listchannels
- hubspot complete multiple callbacks
- operations
- getactionfunctionbyid
- listportalflagstates
- upsertapplicationfeatureflag
- getportalflagstate
- crm
- hubspot retrieve an inbox
- hubspot complete a single callback
- hubspot retrieve function by type
- hubspot delete a portal flag state
- getactiondefinitionrevisionbyid
- getaccesstokenmetadata
- getinboxbyid
- hubspot update a thread
- getactiondefinitionbyid
- hubspot delete a function by type
- deleteapplicationfeatureflag
- content
- archivethread
- hubspot retrieve refresh token metadata
- hubspot retrieve a specific function
- listthreadmessages
- hubspot update an action definition
- hubspot batch create or update portal flag states
- batchdeleteportalflagstates
- automation
- updateactiondefinitionbyid
- getthreadbyid
- hubspot batch delete portal flag states
- hubspot archive a thread
- deleteportalflagstate
- hubspot retrieve an actor
- revokerefreshtoken
- hubspot archive an action definition
- getactorbyid
- hubspot retrieve a message
- hubspot list all inboxes
- upsertactionfunction
- hubspot retrieve a portal flag state
slug: automation-and-integration
source_filename: automation-and-integration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: HubSpot Automation and Integration\n  description: Workflow automation and integration management combining custom workflow actions, OAuth, feature flags, and conversations.\n  tags:\n  - HubSpot\n  - Automation\n  - Integration\n  - OAuth\n  created: '2026-04-18'\n  modified: '2026-04-18'\nbinds:\n- namespace: env\n  keys:\n    HUBSPOT_ACCESS_TOKEN: HUBSPOT_ACCESS_TOKEN\ncapability:\n  consumes:\n  - import: custom-workflow-actions-api\n    location: ./shared/custom-workflow-actions-api.yaml\n  - import: oauth-api\n    location: ./shared/oauth-api.yaml\n  - import: crm-feature-flags-api\n    location: ./shared/crm-feature-flags-api.yaml\n  - import: conversations-api\n    location: ./shared/conversations-api.yaml\n  exposes:\n  - type: mcp\n    port: 9095\n    namespace: automation-and-integration-mcp\n    transport: http\n    description: MCP server for AI-assisted HubSpot Automation and Integration.\n    tools:\n    - name: completecallback\n\
  \      description: HubSpot Complete a Single Callback\n      hints:\n        readOnly: false\n      call: custom-workflow-actions-api.completecallback\n    - name: batchcompletecallbacks\n      description: HubSpot Complete Multiple Callbacks\n      hints:\n        readOnly: false\n      call: custom-workflow-actions-api.batchcompletecallbacks\n    - name: listactiondefinitions\n      description: HubSpot List Action Definitions\n      hints:\n        readOnly: true\n      call: custom-workflow-actions-api.listactiondefinitions\n    - name: createactiondefinition\n      description: HubSpot Create an Action Definition\n      hints:\n        readOnly: false\n      call: custom-workflow-actions-api.createactiondefinition\n    - name: getactiondefinitionbyid\n      description: HubSpot Retrieve an Action Definition\n      hints:\n        readOnly: true\n      call: custom-workflow-actions-api.getactiondefinitionbyid\n    - name: updateactiondefinitionbyid\n      description: HubSpot Update\
  \ an Action Definition\n      hints:\n        readOnly: false\n      call: custom-workflow-actions-api.updateactiondefinitionbyid\n    - name: archiveactiondefinitionbyid\n      description: HubSpot Archive an Action Definition\n      hints:\n        destructive: true\n      call: custom-workflow-actions-api.archiveactiondefinitionbyid\n    - name: listactionfunctions\n      description: HubSpot List Action Functions\n      hints:\n        readOnly: true\n      call: custom-workflow-actions-api.listactionfunctions\n    - name: getactionfunctionbytype\n      description: HubSpot Retrieve Function by Type\n      hints:\n        readOnly: true\n      call: custom-workflow-actions-api.getactionfunctionbytype\n    - name: upsertactionfunction\n      description: HubSpot Create or Update a Function\n      hints:\n        readOnly: false\n      call: custom-workflow-actions-api.upsertactionfunction\n    - name: deleteactionfunctionbytype\n      description: HubSpot Delete a Function by Type\n\
  \      hints:\n        destructive: true\n      call: custom-workflow-actions-api.deleteactionfunctionbytype\n    - name: getactionfunctionbyid\n      description: HubSpot Retrieve a Specific Function\n      hints:\n        readOnly: true\n      call: custom-workflow-actions-api.getactionfunctionbyid\n    - name: deleteactionfunctionbyid\n      description: HubSpot Delete a Specific Function\n      hints:\n        destructive: true\n      call: custom-workflow-actions-api.deleteactionfunctionbyid\n    - name: listactiondefinitionrevisions\n      description: HubSpot List Definition Revisions\n      hints:\n        readOnly: true\n      call: custom-workflow-actions-api.listactiondefinitionrevisions\n    - name: getactiondefinitionrevisionbyid\n      description: HubSpot Retrieve a Specific Revision\n      hints:\n        readOnly: true\n      call: custom-workflow-actions-api.getactiondefinitionrevisionbyid\n    - name: getaccesstokenmetadata\n      description: HubSpot Retrieve Access\
  \ Token Metadata\n      hints:\n        readOnly: true\n      call: oauth-api.getaccesstokenmetadata\n    - name: getrefreshtokenmetadata\n      description: HubSpot Retrieve Refresh Token Metadata\n      hints:\n        readOnly: true\n      call: oauth-api.getrefreshtokenmetadata\n    - name: revokerefreshtoken\n      description: HubSpot Revoke a Refresh Token\n      hints:\n        destructive: true\n      call: oauth-api.revokerefreshtoken\n    - name: createorrefreshaccesstoken\n      description: HubSpot Create or Refresh an Access Token\n      hints:\n        readOnly: false\n      call: oauth-api.createorrefreshaccesstoken\n    - name: getapplicationfeatureflag\n      description: HubSpot Retrieve a Feature Flag Configuration\n      hints:\n        readOnly: true\n      call: crm-feature-flags-api.getapplicationfeatureflag\n    - name: upsertapplicationfeatureflag\n      description: HubSpot Create or Update a Feature Flag\n      hints:\n        readOnly: false\n      call: crm-feature-flags-api.upsertapplicationfeatureflag\n\
  \    - name: deleteapplicationfeatureflag\n      description: HubSpot Delete a Feature Flag\n      hints:\n        destructive: true\n      call: crm-feature-flags-api.deleteapplicationfeatureflag\n    - name: listportalflagstates\n      description: HubSpot List Portal Flag States\n      hints:\n        readOnly: true\n      call: crm-feature-flags-api.listportalflagstates\n    - name: getportalflagstate\n      description: HubSpot Retrieve a Portal Flag State\n      hints:\n        readOnly: true\n      call: crm-feature-flags-api.getportalflagstate\n    - name: setportalflagstate\n      description: HubSpot Set a Portal Flag State\n      hints:\n        readOnly: false\n      call: crm-feature-flags-api.setportalflagstate\n    - name: deleteportalflagstate\n      description: HubSpot Delete a Portal Flag State\n      hints:\n        destructive: true\n      call: crm-feature-flags-api.deleteportalflagstate\n    - name: batchupsertportalflagstates\n      description: HubSpot Batch Create\
  \ or Update Portal Flag States\n      hints:\n        readOnly: false\n      call: crm-feature-flags-api.batchupsertportalflagstates\n    - name: batchdeleteportalflagstates\n      description: HubSpot Batch Delete Portal Flag States\n      hints:\n        readOnly: false\n      call: crm-feature-flags-api.batchdeleteportalflagstates\n    - name: listinboxes\n      description: HubSpot List All Inboxes\n      hints:\n        readOnly: true\n      call: conversations-api.listinboxes\n    - name: getinboxbyid\n      description: HubSpot Retrieve an Inbox\n      hints:\n        readOnly: true\n      call: conversations-api.getinboxbyid\n    - name: listthreads\n      description: HubSpot List Conversation Threads\n      hints:\n        readOnly: true\n      call: conversations-api.listthreads\n    - name: getthreadbyid\n      description: HubSpot Retrieve a Thread\n      hints:\n        readOnly: true\n      call: conversations-api.getthreadbyid\n    - name: updatethread\n      description:\
  \ HubSpot Update a Thread\n      hints:\n        readOnly: false\n      call: conversations-api.updatethread\n    - name: archivethread\n      description: HubSpot Archive a Thread\n      hints:\n        destructive: true\n      call: conversations-api.archivethread\n    - name: listthreadmessages\n      description: HubSpot List Thread Messages\n      hints:\n        readOnly: true\n      call: conversations-api.listthreadmessages\n    - name: sendmessage\n      description: HubSpot Send a Message\n      hints:\n        readOnly: false\n      call: conversations-api.sendmessage\n    - name: getmessagebyid\n      description: HubSpot Retrieve a Message\n      hints:\n        readOnly: true\n      call: conversations-api.getmessagebyid\n    - name: listchannels\n      description: HubSpot List Channels\n      hints:\n        readOnly: true\n      call: conversations-api.listchannels\n    - name: listactors\n      description: HubSpot List Actors\n      hints:\n        readOnly: true\n \
  \     call: conversations-api.listactors\n    - name: getactorbyid\n      description: HubSpot Retrieve an Actor\n      hints:\n        readOnly: true\n      call: conversations-api.getactorbyid\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hubspot/refs/heads/main/capabilities/automation-and-integration.yaml
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
