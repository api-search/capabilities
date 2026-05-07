---
categories: []
consumed_apis: []
description: API Reference API capability.
layout: capability
name: API Reference
operations:
- description: Get the current account
  method: GET
  name: get-current
  path: /accounts/current
- description: Update the current account
  method: PATCH
  name: update-current
  path: /accounts/current
- description: Create an action
  method: POST
  name: create
  path: /actions
- description: Get all actions for the space
  method: GET
  name: get-all
  path: /actions
- description: Create several actions
  method: POST
  name: bulk-create
  path: /actions/bulk
- description: Get an action
  method: GET
  name: get
  path: /actions/{actionId}
- description: Update an action
  method: PATCH
  name: update
  path: /actions/{actionId}
- description: Delete an action
  method: DELETE
  name: delete
  path: /actions/{actionId}
- description: List agent exports
  method: GET
  name: list
  path: /agent-exports
- description: Get an agent export
  method: GET
  name: get
  path: /agent-exports/{agentExportId}
- description: Delete an agent export
  method: DELETE
  name: delete
  path: /agent-exports/{agentExportId}
- description: Download an agent export
  method: GET
  name: download
  path: /agent-exports/{agentExportId}/download
- description: List agents
  method: GET
  name: list
  path: /agents
- description: Create an agent
  method: POST
  name: create
  path: /agents
- description: Get an agent
  method: GET
  name: get
  path: /agents/{agentId}
- description: Delete an agent
  method: DELETE
  name: delete
  path: /agents/{agentId}
- description: List agent versions for an agent
  method: GET
  name: list-versions
  path: /agents/{agentId}/versions
- description: Revert to a specific agent version
  method: GET
  name: revert
  path: /agents/{agentId}/versions/{agentVersionId}/revert
- description: List Agent Roles
  method: GET
  name: list-agent-roles
  path: /agents/{agentId}/roles
- description: Assign Role to Agent
  method: POST
  name: assign-agent-role
  path: /agents/{agentId}/roles
- description: Remove Role from Agent
  method: DELETE
  name: delete-agent-role
  path: /agents/{agentId}/roles/{actorRoleId}
- description: Get logs for an agent
  method: GET
  name: get-agent-logs
  path: /agents/{agentId}/logs
- description: Get an agent log
  method: GET
  name: get-agent-log
  path: /agents/log/{eventId}
- description: Get all agent logs in your environment
  method: GET
  name: get-environment-agent-logs
  path: /agents/logs
- description: Get all executions in your environment
  method: GET
  name: get-environment-agent-executions
  path: /agents/executions
- description: List apps
  method: GET
  name: list
  path: /apps
- description: Create an app
  method: POST
  name: create
  path: /apps
- description: Get an app
  method: GET
  name: get
  path: /apps/{appId}
- description: Update an app
  method: PATCH
  name: update
  path: /apps/{appId}
- description: Delete an app
  method: DELETE
  name: delete
  path: /apps/{appId}
- description: Get constraints
  method: GET
  name: get-constraints
  path: /apps/{appId}/constraints
- description: Create constraint
  method: POST
  name: create-constraint
  path: /apps/{appId}/constraints
- description: Get constraint by ID
  method: GET
  name: get-constraint-by-id
  path: /apps/{appId}/constraints/{constraintId}
- description: Update constraint
  method: PATCH
  name: update-constraint
  path: /apps/{appId}/constraints/{constraintId}
- description: Delete constraint
  method: DELETE
  name: delete-constraint
  path: /apps/{appId}/constraints/{constraintId}
- description: Get constraint versions
  method: GET
  name: get-constraint-versions
  path: /apps/{appId}/constraints/{constraintId}/versions
- description: Get constraint version
  method: GET
  name: get-constraint-version
  path: /apps/{appId}/constraints/{constraintId}/versions/{version}
- description: List prompts
  method: GET
  name: list
  path: //prompts
- description: Create a prompt
  method: POST
  name: create
  path: //prompts
- description: Get a prompt
  method: GET
  name: get
  path: //prompts/{promptId}
- description: Update a prompt
  method: PATCH
  name: update
  path: //prompts/{promptId}
- description: Delete a prompts
  method: DELETE
  name: delete
  path: //prompts/{promptId}
- description: Obtain the publishable key for a specific environment
  method: GET
  name: get-publishable-key
  path: /auth/publishable-key
- description: Get SFTP credentials for Space
  method: GET
  name: get-sftp-credentials
  path: /auth/sftp-credentials
- description: List canvas areas
  method: GET
  name: list
  path: /canvas-areas
- description: Create a canvas area
  method: POST
  name: create
  path: /canvas-areas
- description: Get a canvas area
  method: GET
  name: get
  path: /canvas-areas/{canvasAreaId}
- description: Update a canvas area
  method: PATCH
  name: update
  path: /canvas-areas/{canvasAreaId}
- description: Delete a canvas area
  method: DELETE
  name: delete
  path: /canvas-areas/{canvasAreaId}
- description: Get a commit version
  method: GET
  name: get
  path: /commits/{commitId}
- description: Complete a commit version
  method: POST
  name: complete
  path: /commits/{commitId}/complete
- description: Replay a commit version
  method: POST
  name: replay
  path: /commits/{commitId}/replay
- description: Create
  method: POST
  name: create
  path: /data-clips
- description: List
  method: GET
  name: list
  path: /data-clips
- description: Update
  method: PATCH
  name: update
  path: /data-clips/{dataClipId}
- description: Delete
  method: DELETE
  name: delete
  path: /data-clips/{dataClipId}
- description: Get
  method: GET
  name: get
  path: /data-clips/{dataClipId}
- description: Add Records To Clip
  method: POST
  name: add-records-to-clip
  path: /data-clips/{dataClipId}/add-records
- description: Get Resolutions
  method: GET
  name: get-resolutions
  path: /data-clips/{dataClipId}/resolutions
- description: Update Resolution
  method: PATCH
  name: update-resolution
  path: /data-clips/{dataClipId}/resolutions
personas: []
provider_name: Flatfile
provider_slug: flatfile
search_terms:
- get environment agent executions
- get an action
- get publishable key
- get sftp credentials
- list apps
- api
- update a canvas area
- create an action
- get a canvas area
- get the current account
- update constraint
- get an agent log
- bulk create
- delete a prompts
- revert to a specific agent version
- update an app
- download
- get constraint by id
- get all agent logs in your environment
- delete a canvas area
- complete a commit version
- list agent exports
- get a commit version
- create an app
- get all executions in your environment
- list agent versions for an agent
- list agent roles
- get an app
- delete
- get all
- create several actions
- data exchange
- get all actions for the space
- get agent logs
- get resolutions
- update resolution
- assign role to agent
- etl
- list agents
- get sftp credentials for space
- remove role from agent
- create a prompt
- replay
- update a prompt
- add records to clip
- delete an agent
- get constraint version
- get constraint versions
- flatfile
- delete agent role
- delete constraint
- get logs for an agent
- update the current account
- delete an action
- create constraint
- get
- delete an agent export
- get constraints
- list
- update
- file import
- complete
- list canvas areas
- get an agent export
- create
- data validation
- data onboarding
- update current
- get environment agent logs
- create an agent
- replay a commit version
- list versions
- get agent log
- revert
- assign agent role
- get an agent
- get current
- data ingestion
- delete an app
- get a prompt
- download an agent export
- list prompts
- create a canvas area
- obtain the publishable key for a specific environment
- update an action
slug: flatfile-capability
source_filename: flatfile-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: API Reference\n  description: API Reference API capability.\n  tags:\n  - Flatfile\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: flatfile\n    baseUri: https://api.x.flatfile.com/v1\n    description: API Reference HTTP API.\n    authentication:\n      type: bearer\n      token: '{{FLATFILE_TOKEN}}'\n    resources:\n    - name: accounts-current\n      path: /accounts/current\n      operations:\n      - name: get-current\n        method: GET\n        description: Get the current account\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: update-current\n        method: PATCH\n        description: Update the current account\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: actions\n      path: /actions\n      operations:\n      - name: create\n        method: POST\n        description: Create an action\n        inputParameters:\n        - name: spaceId\n          in: query\n          type: string\n          required: true\n          description: The Space ID for which to create the Action.\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer\
  \ authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-all\n        method: GET\n        description: Get all actions for the space\n        inputParameters:\n        - name: spaceId\n          in: query\n          type: string\n          required: true\n          description: The Space ID for which to get the Actions.\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: actions-bulk\n      path: /actions/bulk\n      operations:\n      - name:\
  \ bulk-create\n        method: POST\n        description: Create several actions\n        inputParameters:\n        - name: spaceId\n          in: query\n          type: string\n          required: true\n          description: The Space ID for which to create the Actions.\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: actions-actionid\n      path: /actions/{actionId}\n      operations:\n      - name: get\n        method: GET\n        description: Get an action\n        inputParameters:\n        - name: actionId\n          in: path\n          type: string\n          required: true\n          description: The id of the action to return\n        -\
  \ name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update\n        method: PATCH\n        description: Update an action\n        inputParameters:\n        - name: actionId\n          in: path\n          type: string\n          required: true\n          description: The id of the action to patch\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n      - name: delete\n        method: DELETE\n        description: Delete an action\n        inputParameters:\n        - name: actionId\n          in: path\n          type: string\n          required: true\n          description: The id of the action to delete\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: agent-exports\n      path: /agent-exports\n      operations:\n      - name: list\n        method: GET\n        description: List agent exports\n        inputParameters:\n        - name: environmentId\n          in: query\n          type: string\n        - name: agentId\n          in: query\n          type: string\n        - name:\
  \ pageSize\n          in: query\n          type: string\n        - name: pageNumber\n          in: query\n          type: string\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: agent-exports-agentexportid\n      path: /agent-exports/{agentExportId}\n      operations:\n      - name: get\n        method: GET\n        description: Get an agent export\n        inputParameters:\n        - name: agentExportId\n          in: path\n          type: string\n          required: true\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n\
  \          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete\n        method: DELETE\n        description: Delete an agent export\n        inputParameters:\n        - name: agentExportId\n          in: path\n          type: string\n          required: true\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: agent-exports-agentexportid-download\n      path: /agent-exports/{agentExportId}/download\n      operations:\n      - name: download\n        method: GET\n        description: Download an agent\
  \ export\n        inputParameters:\n        - name: agentExportId\n          in: path\n          type: string\n          required: true\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: agents\n      path: /agents\n      operations:\n      - name: list\n        method: GET\n        description: List agents\n        inputParameters:\n        - name: environmentId\n          in: query\n          type: string\n          required: true\n        - name: isSystem\n          in: query\n          type: boolean\n        - name: search\n          in: query\n          type: string\n        - name: pageSize\n          in: query\n          type: string\n      \
  \  - name: pageNumber\n          in: query\n          type: string\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create\n        method: POST\n        description: Create an agent\n        inputParameters:\n        - name: environmentId\n          in: query\n          type: string\n          required: true\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n    \
  \      type: object\n          value: $.\n    - name: agents-agentid\n      path: /agents/{agentId}\n      operations:\n      - name: get\n        method: GET\n        description: Get an agent\n        inputParameters:\n        - name: agentId\n          in: path\n          type: string\n          required: true\n        - name: environmentId\n          in: query\n          type: string\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete\n        method: DELETE\n        description: Delete an agent\n        inputParameters:\n        - name: agentId\n          in: path\n          type: string\n          required: true\n        - name: environmentId\n\
  \          in: query\n          type: string\n          description: This environment variable is no longer needed or used\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: agents-agentid-versions\n      path: /agents/{agentId}/versions\n      operations:\n      - name: list-versions\n        method: GET\n        description: List agent versions for an agent\n        inputParameters:\n        - name: agentId\n          in: path\n          type: string\n          required: true\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n\
  \          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: agents-agentid-versions-agentversionid-revert\n      path: /agents/{agentId}/versions/{agentVersionId}/revert\n      operations:\n      - name: revert\n        method: GET\n        description: Revert to a specific agent version\n        inputParameters:\n        - name: agentId\n          in: path\n          type: string\n          required: true\n        - name: agentVersionId\n          in: path\n          type: string\n          required: true\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: agents-agentid-roles\n      path: /agents/{agentId}/roles\n      operations:\n      - name: list-agent-roles\n        method: GET\n        description: List Agent Roles\n        inputParameters:\n        - name: agentId\n          in: path\n          type: string\n          required: true\n          description: The agent id\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: assign-agent-role\n        method: POST\n        description: Assign Role to Agent\n        inputParameters:\n        - name: agentId\n          in: path\n          type: string\n          required: true\n          description:\
  \ The agent id\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: agents-agentid-roles-actorroleid\n      path: /agents/{agentId}/roles/{actorRoleId}\n      operations:\n      - name: delete-agent-role\n        method: DELETE\n        description: Remove Role from Agent\n        inputParameters:\n        - name: agentId\n          in: path\n          type: string\n          required: true\n          description: The agent id\n        - name: actorRoleId\n          in: path\n          type: string\n          required: true\n          description: The actor role id\n        - name: Authorization\n          in: header\n          type: string\n        \
  \  required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: agents-agentid-logs\n      path: /agents/{agentId}/logs\n      operations:\n      - name: get-agent-logs\n        method: GET\n        description: Get logs for an agent\n        inputParameters:\n        - name: agentId\n          in: path\n          type: string\n          required: true\n        - name: environmentId\n          in: query\n          type: string\n          required: true\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: agents-log-eventid\n      path: /agents/log/{eventId}\n      operations:\n      - name: get-agent-log\n        method: GET\n        description: Get an agent log\n        inputParameters:\n        - name: eventId\n          in: path\n          type: string\n          required: true\n        - name: environmentId\n          in: query\n          type: string\n          required: true\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: agents-logs\n      path: /agents/logs\n      operations:\n      - name: get-environment-agent-logs\n        method: GET\n        description:\
  \ Get all agent logs in your environment\n        inputParameters:\n        - name: environmentId\n          in: query\n          type: string\n          required: true\n        - name: spaceId\n          in: query\n          type: string\n        - name: success\n          in: query\n          type: string\n        - name: pageSize\n          in: query\n          type: string\n        - name: pageNumber\n          in: query\n          type: string\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: agents-executions\n      path: /agents/executions\n      operations:\n      - name: get-environment-agent-executions\n        method: GET\n        description:\
  \ Get all executions in your environment\n        inputParameters:\n        - name: environmentId\n          in: query\n          type: string\n          required: true\n        - name: agentId\n          in: query\n          type: string\n        - name: spaceId\n          in: query\n          type: string\n        - name: success\n          in: query\n          type: string\n        - name: pageSize\n          in: query\n          type: string\n        - name: pageNumber\n          in: query\n          type: string\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps\n      path: /apps\n      operations:\n      - name: list\n        method: GET\n\
  \        description: List apps\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create\n        method: POST\n        description: Create an app\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-appid\n      path: /apps/{appId}\n      operations:\n  \
  \    - name: get\n        method: GET\n        description: Get an app\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: ID of app\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update\n        method: PATCH\n        description: Update an app\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: ID of app\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name:\
  \ X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete\n        method: DELETE\n        description: Delete an app\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: ID of app to delete\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-appid-constraints\n      path: /apps/{appId}/constraints\n      operations:\n      - name: get-constraints\n        method: GET\n        description:\
  \ Get constraints\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: ID of the app\n        - name: includeBuiltins\n          in: query\n          type: boolean\n          description: Whether to include built-in constraints\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-constraint\n        method: POST\n        description: Create constraint\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: ID of the app\n        - name: Authorization\n          in: header\n\
  \          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-appid-constraints-constraintid\n      path: /apps/{appId}/constraints/{constraintId}\n      operations:\n      - name: get-constraint-by-id\n        method: GET\n        description: Get constraint by ID\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: ID of the app\n        - name: constraintId\n          in: path\n          type: string\n          required: true\n          description: ID of the constraint\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n\
  \        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-constraint\n        method: PATCH\n        description: Update constraint\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: ID of the app\n        - name: constraintId\n          in: path\n          type: string\n          required: true\n          description: ID of the constraint\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n        \
  \  value: $.\n      - name: delete-constraint\n        method: DELETE\n        description: Delete constraint\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: ID of the app\n        - name: constraintId\n          in: path\n          type: string\n          required: true\n          description: ID of the constraint\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-appid-constraints-constraintid-versions\n      path: /apps/{appId}/constraints/{constraintId}/versions\n      operations:\n      - name: get-constraint-versions\n        method: GET\n     \
  \   description: Get constraint versions\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n          description: ID of the app\n        - name: constraintId\n          in: path\n          type: string\n          required: true\n          description: ID of the constraint\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-appid-constraints-constraintid-versions-ver\n      path: /apps/{appId}/constraints/{constraintId}/versions/{version}\n      operations:\n      - name: get-constraint-version\n        method: GET\n        description: Get constraint version\n        inputParameters:\n\
  \        - name: appId\n          in: path\n          type: string\n          required: true\n          description: ID of the app\n        - name: constraintId\n          in: path\n          type: string\n          required: true\n          description: ID of the constraint\n        - name: version\n          in: path\n          type: integer\n          required: true\n          description: Version of the constraint\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: prompts\n      path: //prompts\n      operations:\n      - name: list\n        method: GET\n        description: List prompts\n        inputParameters:\n        - name: promptType\n  \
  \        in: query\n          type: string\n          description: Type of prompt (default AI_ASSIST)\n        - name: pageSize\n          in: query\n          type: integer\n          description: Number of prompts to return in a page (default 7)\n        - name: pageNumber\n          in: query\n          type: integer\n          description: Based on pageSize, which page of prompts to return\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create\n        method: POST\n        description: Create a prompt\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n         \
  \ description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: prompts-promptid\n      path: //prompts/{promptId}\n      operations:\n      - name: get\n        method: GET\n        description: Get a prompt\n        inputParameters:\n        - name: promptId\n          in: path\n          type: string\n          required: true\n          description: ID of prompts\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update\n        method:\
  \ PATCH\n        description: Update a prompt\n        inputParameters:\n        - name: promptId\n          in: path\n          type: string\n          required: true\n          description: ID of prompts\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete\n        method: DELETE\n        description: Delete a prompts\n        inputParameters:\n        - name: promptId\n          in: path\n          type: string\n          required: true\n          description: ID of prompts\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n\
  \          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-publishable-key\n      path: /auth/publishable-key\n      operations:\n      - name: get-publishable-key\n        method: GET\n        description: Obtain the publishable key for a specific environment\n        inputParameters:\n        - name: environmentId\n          in: query\n          type: string\n          required: true\n          description: ID of environment to search\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-sftp-credentials\n\
  \      path: /auth/sftp-credentials\n      operations:\n      - name: get-sftp-credentials\n        method: GET\n        description: Get SFTP credentials for Space\n        inputParameters:\n        - name: spaceId\n          in: query\n          type: string\n          required: true\n          description: ID of space to get credentials for\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-Hooks\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: canvas-areas\n      path: /canvas-areas\n      operations:\n      - name: list\n        method: GET\n        description: List canvas areas\n        inputParameters:\n        - name: canvasId\n          in: query\n          type: string\n          description:\
  \ ID of the canvas to filter areas by\n        - name: parentId\n          in: query\n          type: string\n          description: ID of the parent canvas area to filter by\n        - name: spaceId\n          in: query\n          type: string\n          description: ID of the space to filter areas by\n        - name: environmentId\n          in: query\n          type: string\n          description: ID of the environment to filter areas by\n        - name: pageSize\n          in: query\n          type: integer\n          description: Number of areas to return in a page (default 20)\n        - name: pageNumber\n          in: query\n          type: integer\n          description: Based on pageSize, which page of areas to return\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: Bearer authentication\n        - name: X-Disable-\n\n# --- truncated at 32 KB (89 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/flatfile/refs/heads/main/capabilities/flatfile-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/flatfile/refs/heads/main/capabilities/flatfile-capability.yaml
tags:
- Flatfile
- API
tools:
- description: Get the current account
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-current
- description: Update the current account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: update-current
- description: Create an action
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create
- description: Get all actions for the space
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-all
- description: Create several actions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: bulk-create
- description: Get an action
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get
- description: Update an action
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: update
- description: Delete an action
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete
- description: List agent exports
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list
- description: Get an agent export
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get
- description: Delete an agent export
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete
- description: Download an agent export
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: download
- description: List agents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list
- description: Create an agent
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create
- description: Get an agent
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get
- description: Delete an agent
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete
- description: List agent versions for an agent
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-versions
- description: Revert to a specific agent version
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: revert
- description: List Agent Roles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-agent-roles
- description: Assign Role to Agent
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: assign-agent-role
- description: Remove Role from Agent
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-agent-role
- description: Get logs for an agent
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-agent-logs
- description: Get an agent log
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-agent-log
- description: Get all agent logs in your environment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-environment-agent-logs
- description: Get all executions in your environment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-environment-agent-executions
- description: List apps
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list
- description: Create an app
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create
- description: Get an app
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get
- description: Update an app
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: update
- description: Delete an app
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete
- description: Get constraints
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-constraints
- description: Create constraint
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-constraint
- description: Get constraint by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-constraint-by-id
- description: Update constraint
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: update-constraint
- description: Delete constraint
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-constraint
- description: Get constraint versions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-constraint-versions
- description: Get constraint version
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-constraint-version
- description: List prompts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list
- description: Create a prompt
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create
- description: Get a prompt
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get
- description: Update a prompt
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: update
- description: Delete a prompts
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete
- description: Obtain the publishable key for a specific environment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-publishable-key
- description: Get SFTP credentials for Space
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-sftp-credentials
- description: List canvas areas
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list
- description: Create a canvas area
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create
- description: Get a canvas area
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get
- description: Update a canvas area
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: update
- description: Delete a canvas area
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete
- description: Get a commit version
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get
- description: Complete a commit version
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: complete
- description: Replay a commit version
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: replay
- description: Create
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create
- description: List
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list
- description: Update
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: update
- description: Delete
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete
- description: Get
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get
- description: Add Records To Clip
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: add-records-to-clip
- description: Get Resolutions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-resolutions
- description: Update Resolution
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: update-resolution
---
