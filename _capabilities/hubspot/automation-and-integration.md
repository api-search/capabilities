---
categories:
- automation
consumed_apis: []
description: Workflow automation and integration management combining custom workflow actions, OAuth, feature flags, and conversations.
layout: capability
name: HubSpot Automation and Integration
operations: []
personas: []
provider_name: HubSpot
provider_slug: hubspot
search_terms:
- hubspot archive an action definition
- hubspot retrieve an inbox
- integration
- analytics
- getapplicationfeatureflag
- getinboxbyid
- content
- listactionfunctions
- setportalflagstate
- hubspot update an action definition
- hubspot retrieve a specific revision
- hubspot delete a portal flag state
- batchupsertportalflagstates
- deleteactionfunctionbyid
- deleteapplicationfeatureflag
- hubspot list portal flag states
- getactorbyid
- hubspot list action functions
- hubspot list all inboxes
- batchcompletecallbacks
- hubspot retrieve function by type
- hubspot complete multiple callbacks
- hubspot update a thread
- hubspot list action definitions
- hubspot retrieve refresh token metadata
- hubspot list thread messages
- hubspot retrieve a feature flag configuration
- automation
- archivethread
- upsertactionfunction
- hubspot delete a specific function
- hubspot revoke a refresh token
- listchannels
- listthreadmessages
- hubspot list definition revisions
- hubspot batch create or update portal flag states
- marketing automation
- hubspot retrieve access token metadata
- crm
- createactiondefinition
- hubspot archive a thread
- archiveactiondefinitionbyid
- updateactiondefinitionbyid
- hubspot send a message
- hubspot complete a single callback
- hubspot create or update a function
- listactors
- listthreads
- getportalflagstate
- listportalflagstates
- hubspot list channels
- createorrefreshaccesstoken
- hubspot
- hubspot list conversation threads
- getactiondefinitionrevisionbyid
- hubspot create or update a feature flag
- batchdeleteportalflagstates
- revokerefreshtoken
- commerce
- getrefreshtokenmetadata
- email marketing
- hubspot retrieve a specific function
- hubspot create or refresh an access token
- hubspot delete a feature flag
- deleteactionfunctionbytype
- hubspot retrieve a thread
- completecallback
- hubspot set a portal flag state
- sendmessage
- listactiondefinitionrevisions
- deleteportalflagstate
- hubspot retrieve an action definition
- hubspot retrieve an actor
- hubspot retrieve a portal flag state
- getaccesstokenmetadata
- updatethread
- sales
- hubspot retrieve a message
- hubspot list actors
- hubspot delete a function by type
- getactionfunctionbytype
- getthreadbyid
- marketing
- getmessagebyid
- oauth
- upsertapplicationfeatureflag
- operations
- hubspot create an action definition
- listactiondefinitions
- getactionfunctionbyid
- customer service
- getactiondefinitionbyid
- hubspot batch delete portal flag states
- listinboxes
slug: automation-and-integration
source_filename: automation-and-integration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: HubSpot Automation and Integration\n  description: Workflow automation and integration management combining custom workflow actions, OAuth, feature flags, and\n    conversations.\n  tags:\n  - HubSpot\n  - Automation\n  - Integration\n  - OAuth\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    HUBSPOT_ACCESS_TOKEN: HUBSPOT_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: custom-workflow-actions-api\n    baseUri: https://api.hubapi.com\n    description: \"The HubSpot Custom Workflow Actions API enables developers to create, manage, and extend workflow \\nautomation\\\n      \\ capabilities within HubSpot. This API allows you to define custom actions that can be \\nuse\"\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: complete\n      path: /complete\n      description: complete operations\n      operations:\n    \
  \  - name: completecallback\n        method: POST\n        description: HubSpot Complete a Single Callback\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: batchcompletecallbacks\n        method: POST\n        description: HubSpot Complete Multiple Callbacks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: actions\n      path: /actions\n      description: actions operations\n      operations:\n      - name: listactiondefinitions\n        method: GET\n        description: HubSpot List Action Definitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createactiondefinition\n        method: POST\n        description: HubSpot Create an Action Definition\n        outputRawFormat: json\n        outputParameters:\n   \
  \     - name: result\n          type: object\n          value: $.\n    - name: '{appId}'\n      path: /{appId}\n      description: '{appId} operations'\n      operations:\n      - name: getactiondefinitionbyid\n        method: GET\n        description: HubSpot Retrieve an Action Definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateactiondefinitionbyid\n        method: PATCH\n        description: HubSpot Update an Action Definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: archiveactiondefinitionbyid\n        method: DELETE\n        description: HubSpot Archive an Action Definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: functions\n      path: /functions\n      description: functions operations\n\
  \      operations:\n      - name: listactionfunctions\n        method: GET\n        description: HubSpot List Action Functions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getactionfunctionbytype\n        method: GET\n        description: HubSpot Retrieve Function by Type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: upsertactionfunction\n        method: PUT\n        description: HubSpot Create or Update a Function\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteactionfunctionbytype\n        method: DELETE\n        description: HubSpot Delete a Function by Type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ '{functionType}'\n      path: /{functionType}\n      description: '{functionType} operations'\n      operations:\n      - name: getactionfunctionbyid\n        method: GET\n        description: HubSpot Retrieve a Specific Function\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteactionfunctionbyid\n        method: DELETE\n        description: HubSpot Delete a Specific Function\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: revisions\n      path: /revisions\n      description: revisions operations\n      operations:\n      - name: listactiondefinitionrevisions\n        method: GET\n        description: HubSpot List Definition Revisions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getactiondefinitionrevisionbyid\n\
  \        method: GET\n        description: HubSpot Retrieve a Specific Revision\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: oauth-api\n    baseUri: https://api.hubapi.com\n    description: 'The HubSpot OAuth API enables secure authentication and authorization for accessing HubSpot resources.\n\n      Use these endpoints to manage OAuth tokens, refresh access tokens, and retrieve token metadata fo'\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: access-tokens\n      path: /access-tokens\n      description: access-tokens operations\n      operations:\n      - name: getaccesstokenmetadata\n        method: GET\n        description: HubSpot Retrieve Access Token Metadata\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: refresh-tokens\n\
  \      path: /refresh-tokens\n      description: refresh-tokens operations\n      operations:\n      - name: getrefreshtokenmetadata\n        method: GET\n        description: HubSpot Retrieve Refresh Token Metadata\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: revokerefreshtoken\n        method: DELETE\n        description: HubSpot Revoke a Refresh Token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: token\n      path: /token\n      description: token operations\n      operations:\n      - name: createorrefreshaccesstoken\n        method: POST\n        description: HubSpot Create or Refresh an Access Token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: crm-feature-flags-api\n    baseUri: https://api.hubapi.com\n\
  \    description: 'The HubSpot CRM Feature Flags API allows you to manage feature flags for your HubSpot applications.\n\n\n      ## Overview\n\n      Feature flags enable you to control feature rollouts at both the application and portal'\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: flags\n      path: /flags\n      description: flags operations\n      operations:\n      - name: getapplicationfeatureflag\n        method: GET\n        description: HubSpot Retrieve a Feature Flag Configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: upsertapplicationfeatureflag\n        method: PUT\n        description: HubSpot Create or Update a Feature Flag\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteapplicationfeatureflag\n        method:\
  \ DELETE\n        description: HubSpot Delete a Feature Flag\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: portals\n      path: /portals\n      description: portals operations\n      operations:\n      - name: listportalflagstates\n        method: GET\n        description: HubSpot List Portal Flag States\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getportalflagstate\n        method: GET\n        description: HubSpot Retrieve a Portal Flag State\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setportalflagstate\n        method: PUT\n        description: HubSpot Set a Portal Flag State\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: deleteportalflagstate\n        method: DELETE\n        description: HubSpot Delete a Portal Flag State\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: upsert\n      path: /upsert\n      description: upsert operations\n      operations:\n      - name: batchupsertportalflagstates\n        method: POST\n        description: HubSpot Batch Create or Update Portal Flag States\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: delete\n      path: /delete\n      description: delete operations\n      operations:\n      - name: batchdeleteportalflagstates\n        method: POST\n        description: HubSpot Batch Delete Portal Flag States\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: conversations-api\n\
  \    baseUri: https://api.hubapi.com\n    description: \"The HubSpot Conversations API enables you to manage conversation threads, \\nmessages, and inboxes programmatically.\\\n      \\ Use this API to query existing \\nconversations, send messages, manage thread assignmen\"\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: inboxes\n      path: /inboxes\n      description: inboxes operations\n      operations:\n      - name: listinboxes\n        method: GET\n        description: HubSpot List All Inboxes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getinboxbyid\n        method: GET\n        description: HubSpot Retrieve an Inbox\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: threads\n      path: /threads\n      description: threads operations\n\
  \      operations:\n      - name: listthreads\n        method: GET\n        description: HubSpot List Conversation Threads\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getthreadbyid\n        method: GET\n        description: HubSpot Retrieve a Thread\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatethread\n        method: PATCH\n        description: HubSpot Update a Thread\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: archivethread\n        method: DELETE\n        description: HubSpot Archive a Thread\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: messages\n      path: /messages\n      description: messages\
  \ operations\n      operations:\n      - name: listthreadmessages\n        method: GET\n        description: HubSpot List Thread Messages\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: sendmessage\n        method: POST\n        description: HubSpot Send a Message\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getmessagebyid\n        method: GET\n        description: HubSpot Retrieve a Message\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: channels\n      path: /channels\n      description: channels operations\n      operations:\n      - name: listchannels\n        method: GET\n        description: HubSpot List Channels\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n    - name: actors\n      path: /actors\n      description: actors operations\n      operations:\n      - name: listactors\n        method: GET\n        description: HubSpot List Actors\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getactorbyid\n        method: GET\n        description: HubSpot Retrieve an Actor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: mcp\n    port: 9095\n    namespace: automation-and-integration-mcp\n    transport: http\n    description: MCP server for AI-assisted HubSpot Automation and Integration.\n    tools:\n    - name: completecallback\n      description: HubSpot Complete a Single Callback\n      hints:\n        readOnly: false\n      call: custom-workflow-actions-api.completecallback\n    - name: batchcompletecallbacks\n\
  \      description: HubSpot Complete Multiple Callbacks\n      hints:\n        readOnly: false\n      call: custom-workflow-actions-api.batchcompletecallbacks\n    - name: listactiondefinitions\n      description: HubSpot List Action Definitions\n      hints:\n        readOnly: true\n      call: custom-workflow-actions-api.listactiondefinitions\n    - name: createactiondefinition\n      description: HubSpot Create an Action Definition\n      hints:\n        readOnly: false\n      call: custom-workflow-actions-api.createactiondefinition\n    - name: getactiondefinitionbyid\n      description: HubSpot Retrieve an Action Definition\n      hints:\n        readOnly: true\n      call: custom-workflow-actions-api.getactiondefinitionbyid\n    - name: updateactiondefinitionbyid\n      description: HubSpot Update an Action Definition\n      hints:\n        readOnly: false\n      call: custom-workflow-actions-api.updateactiondefinitionbyid\n    - name: archiveactiondefinitionbyid\n      description:\
  \ HubSpot Archive an Action Definition\n      hints:\n        destructive: true\n      call: custom-workflow-actions-api.archiveactiondefinitionbyid\n    - name: listactionfunctions\n      description: HubSpot List Action Functions\n      hints:\n        readOnly: true\n      call: custom-workflow-actions-api.listactionfunctions\n    - name: getactionfunctionbytype\n      description: HubSpot Retrieve Function by Type\n      hints:\n        readOnly: true\n      call: custom-workflow-actions-api.getactionfunctionbytype\n    - name: upsertactionfunction\n      description: HubSpot Create or Update a Function\n      hints:\n        readOnly: false\n      call: custom-workflow-actions-api.upsertactionfunction\n    - name: deleteactionfunctionbytype\n      description: HubSpot Delete a Function by Type\n      hints:\n        destructive: true\n      call: custom-workflow-actions-api.deleteactionfunctionbytype\n    - name: getactionfunctionbyid\n      description: HubSpot Retrieve a Specific\
  \ Function\n      hints:\n        readOnly: true\n      call: custom-workflow-actions-api.getactionfunctionbyid\n    - name: deleteactionfunctionbyid\n      description: HubSpot Delete a Specific Function\n      hints:\n        destructive: true\n      call: custom-workflow-actions-api.deleteactionfunctionbyid\n    - name: listactiondefinitionrevisions\n      description: HubSpot List Definition Revisions\n      hints:\n        readOnly: true\n      call: custom-workflow-actions-api.listactiondefinitionrevisions\n    - name: getactiondefinitionrevisionbyid\n      description: HubSpot Retrieve a Specific Revision\n      hints:\n        readOnly: true\n      call: custom-workflow-actions-api.getactiondefinitionrevisionbyid\n    - name: getaccesstokenmetadata\n      description: HubSpot Retrieve Access Token Metadata\n      hints:\n        readOnly: true\n      call: oauth-api.getaccesstokenmetadata\n    - name: getrefreshtokenmetadata\n      description: HubSpot Retrieve Refresh Token Metadata\n\
  \      hints:\n        readOnly: true\n      call: oauth-api.getrefreshtokenmetadata\n    - name: revokerefreshtoken\n      description: HubSpot Revoke a Refresh Token\n      hints:\n        destructive: true\n      call: oauth-api.revokerefreshtoken\n    - name: createorrefreshaccesstoken\n      description: HubSpot Create or Refresh an Access Token\n      hints:\n        readOnly: false\n      call: oauth-api.createorrefreshaccesstoken\n    - name: getapplicationfeatureflag\n      description: HubSpot Retrieve a Feature Flag Configuration\n      hints:\n        readOnly: true\n      call: crm-feature-flags-api.getapplicationfeatureflag\n    - name: upsertapplicationfeatureflag\n      description: HubSpot Create or Update a Feature Flag\n      hints:\n        readOnly: false\n      call: crm-feature-flags-api.upsertapplicationfeatureflag\n    - name: deleteapplicationfeatureflag\n      description: HubSpot Delete a Feature Flag\n      hints:\n        destructive: true\n      call: crm-feature-flags-api.deleteapplicationfeatureflag\n\
  \    - name: listportalflagstates\n      description: HubSpot List Portal Flag States\n      hints:\n        readOnly: true\n      call: crm-feature-flags-api.listportalflagstates\n    - name: getportalflagstate\n      description: HubSpot Retrieve a Portal Flag State\n      hints:\n        readOnly: true\n      call: crm-feature-flags-api.getportalflagstate\n    - name: setportalflagstate\n      description: HubSpot Set a Portal Flag State\n      hints:\n        readOnly: false\n      call: crm-feature-flags-api.setportalflagstate\n    - name: deleteportalflagstate\n      description: HubSpot Delete a Portal Flag State\n      hints:\n        destructive: true\n      call: crm-feature-flags-api.deleteportalflagstate\n    - name: batchupsertportalflagstates\n      description: HubSpot Batch Create or Update Portal Flag States\n      hints:\n        readOnly: false\n      call: crm-feature-flags-api.batchupsertportalflagstates\n    - name: batchdeleteportalflagstates\n      description:\
  \ HubSpot Batch Delete Portal Flag States\n      hints:\n        readOnly: false\n      call: crm-feature-flags-api.batchdeleteportalflagstates\n    - name: listinboxes\n      description: HubSpot List All Inboxes\n      hints:\n        readOnly: true\n      call: conversations-api.listinboxes\n    - name: getinboxbyid\n      description: HubSpot Retrieve an Inbox\n      hints:\n        readOnly: true\n      call: conversations-api.getinboxbyid\n    - name: listthreads\n      description: HubSpot List Conversation Threads\n      hints:\n        readOnly: true\n      call: conversations-api.listthreads\n    - name: getthreadbyid\n      description: HubSpot Retrieve a Thread\n      hints:\n        readOnly: true\n      call: conversations-api.getthreadbyid\n    - name: updatethread\n      description: HubSpot Update a Thread\n      hints:\n        readOnly: false\n      call: conversations-api.updatethread\n    - name: archivethread\n      description: HubSpot Archive a Thread\n      hints:\n\
  \        destructive: true\n      call: conversations-api.archivethread\n    - name: listthreadmessages\n      description: HubSpot List Thread Messages\n      hints:\n        readOnly: true\n      call: conversations-api.listthreadmessages\n    - name: sendmessage\n      description: HubSpot Send a Message\n      hints:\n        readOnly: false\n      call: conversations-api.sendmessage\n    - name: getmessagebyid\n      description: HubSpot Retrieve a Message\n      hints:\n        readOnly: true\n      call: conversations-api.getmessagebyid\n    - name: listchannels\n      description: HubSpot List Channels\n      hints:\n        readOnly: true\n      call: conversations-api.listchannels\n    - name: listactors\n      description: HubSpot List Actors\n      hints:\n        readOnly: true\n      call: conversations-api.listactors\n    - name: getactorbyid\n      description: HubSpot Retrieve an Actor\n      hints:\n        readOnly: true\n      call: conversations-api.getactorbyid\n"
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
