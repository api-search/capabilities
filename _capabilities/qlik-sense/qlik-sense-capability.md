---
categories: []
consumed_apis: []
description: REST API for Qlik Cloud platform services including apps, spaces, and reloads. Provides programmatic access to manage analytics applications, organize resources into spaces with access control, and trigger data reloads. Authentication is performed via OAuth 2.0 bearer tokens or API keys issued from a Qlik Cloud tenant.
layout: capability
name: Qlik Cloud REST API
operations:
- description: Get app privileges
  method: GET
  name: getappsprivileges
  path: /apps
- description: Create an app
  method: POST
  name: createapp
  path: /apps
- description: Retrieve an app
  method: GET
  name: getapp
  path: /apps/{appId}
- description: Update an app
  method: PUT
  name: updateapp
  path: /apps/{appId}
- description: Delete an app
  method: DELETE
  name: deleteapp
  path: /apps/{appId}
- description: Copy an app
  method: POST
  name: copyapp
  path: /apps/{appId}/copy
- description: Export an app
  method: POST
  name: exportapp
  path: /apps/{appId}/export
- description: Import an app
  method: POST
  name: importapp
  path: /apps/import
- description: Publish an app
  method: POST
  name: publishapp
  path: /apps/{appId}/publish
- description: Republish an app
  method: PUT
  name: republishapp
  path: /apps/{appId}/publish
- description: Change app owner
  method: PUT
  name: updateappowner
  path: /apps/{appId}/owner
- description: Move app to a space
  method: PUT
  name: moveapptospace
  path: /apps/{appId}/space
- description: Remove app from space
  method: DELETE
  name: removeappfromspace
  path: /apps/{appId}/space
- description: Retrieve data metadata for an app
  method: GET
  name: getappdatametadata
  path: /apps/{appId}/data/metadata
- description: Retrieve data lineage for an app
  method: GET
  name: getappdatalineage
  path: /apps/{appId}/data/lineage
- description: Retrieve script history
  method: GET
  name: getappscripts
  path: /apps/{appId}/scripts
- description: Set script for an app
  method: POST
  name: setappscript
  path: /apps/{appId}/scripts
- description: Retrieve script log metadata
  method: GET
  name: getappreloadlogs
  path: /apps/{appId}/reloads/logs
- description: Retrieve a specific reload log
  method: GET
  name: getappreloadlog
  path: /apps/{appId}/reloads/logs/{reloadId}
- description: List spaces
  method: GET
  name: listspaces
  path: /spaces
- description: Create a space
  method: POST
  name: createspace
  path: /spaces
- description: Retrieve a space
  method: GET
  name: getspace
  path: /spaces/{spaceId}
- description: Update a space
  method: PUT
  name: updatespace
  path: /spaces/{spaceId}
- description: Patch space properties
  method: PATCH
  name: patchspace
  path: /spaces/{spaceId}
- description: Delete a space
  method: DELETE
  name: deletespace
  path: /spaces/{spaceId}
- description: List space assignments
  method: GET
  name: listspaceassignments
  path: /spaces/{spaceId}/assignments
- description: Assign user or group to space
  method: POST
  name: createspaceassignment
  path: /spaces/{spaceId}/assignments
- description: Retrieve a space assignment
  method: GET
  name: getspaceassignment
  path: /spaces/{spaceId}/assignments/{assignmentId}
- description: Update a space assignment
  method: PUT
  name: updatespaceassignment
  path: /spaces/{spaceId}/assignments/{assignmentId}
- description: Delete a space assignment
  method: DELETE
  name: deletespaceassignment
  path: /spaces/{spaceId}/assignments/{assignmentId}
- description: List space types
  method: GET
  name: listspacetypes
  path: /spaces/types
- description: List reloads
  method: GET
  name: listreloads
  path: /reloads
- description: Reload an app
  method: POST
  name: reloadapp
  path: /reloads
- description: Retrieve a reload record
  method: GET
  name: getreload
  path: /reloads/{reloadId}
- description: Cancel a reload
  method: POST
  name: cancelreload
  path: /reloads/{reloadId}/actions/cancel
personas: []
provider_name: Qlik Sense
provider_slug: qlik-sense
search_terms:
- create a space
- deletespace
- api
- retrieve a space
- retrieve a specific reload log
- set script for an app
- delete a space
- createspaceassignment
- update an app
- reloadapp
- retrieve data metadata for an app
- importapp
- getapp
- republish an app
- update a space assignment
- retrieve script log metadata
- visualization
- create an app
- move app to a space
- getspaceassignment
- import an app
- assign user or group to space
- listspacetypes
- exportapp
- cancelreload
- cloud
- list reloads
- updatespace
- getappdatalineage
- retrieve a reload record
- removeappfromspace
- list space types
- retrieve an app
- patch space properties
- cancel a reload
- republishapp
- getappreloadlogs
- retrieve a space assignment
- getreload
- business intelligence
- listreloads
- patchspace
- moveapptospace
- getspace
- change app owner
- retrieve data lineage for an app
- getappsprivileges
- getappreloadlog
- get app privileges
- data integration
- updateappowner
- setappscript
- update a space
- analytics
- updatespaceassignment
- reload an app
- qlik
- copyapp
- list space assignments
- sense
- retrieve script history
- getappdatametadata
- publish an app
- delete a space assignment
- updateapp
- listspaceassignments
- deleteapp
- publishapp
- export an app
- createapp
- delete an app
- copy an app
- remove app from space
- createspace
- listspaces
- deletespaceassignment
- list spaces
- getappscripts
slug: qlik-sense-capability
source_filename: qlik-sense-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Qlik Cloud REST API\n  description: REST API for Qlik Cloud platform services including apps, spaces, and reloads. Provides programmatic access\n    to manage analytics applications, organize resources into spaces with access control, and trigger data reloads. Authentication\n    is performed via OAuth 2.0 bearer tokens or API keys issued from a Qlik Cloud tenant.\n  tags:\n  - Qlik\n  - Sense\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: qlik-sense\n    baseUri: https://your-tenant.us.qlikcloud.com/api/v1\n    description: Qlik Cloud REST API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{QLIK_SENSE_TOKEN}}'\n    resources:\n    - name: apps\n      path: /apps\n      operations:\n      - name: getappsprivileges\n        method: GET\n        description: Get app privileges\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: createapp\n        method: POST\n        description: Create an app\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-appid\n      path: /apps/{appId}\n      operations:\n      - name: getapp\n        method: GET\n        description: Retrieve an app\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateapp\n        method: PUT\n        description: Update an app\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteapp\n        method: DELETE\n        description: Delete an app\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-appid-copy\n      path:\
  \ /apps/{appId}/copy\n      operations:\n      - name: copyapp\n        method: POST\n        description: Copy an app\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-appid-export\n      path: /apps/{appId}/export\n      operations:\n      - name: exportapp\n        method: POST\n        description: Export an app\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-import\n      path: /apps/import\n      operations:\n      - name: importapp\n        method: POST\n        description: Import an app\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: The name of the target app.\n        - name: spaceId\n          in: query\n          type: string\n          description: The space identifier to import the app into. Uses personal space if\
  \ omitted.\n        - name: mode\n          in: query\n          type: string\n          description: The import mode for the app.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-appid-publish\n      path: /apps/{appId}/publish\n      operations:\n      - name: publishapp\n        method: POST\n        description: Publish an app\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: republishapp\n        method: PUT\n        description: Republish an app\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-appid-owner\n      path: /apps/{appId}/owner\n      operations:\n      - name: updateappowner\n        method: PUT\n        description: Change app owner\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: apps-appid-space\n      path: /apps/{appId}/space\n      operations:\n      - name: moveapptospace\n        method: PUT\n        description: Move app to a space\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removeappfromspace\n        method: DELETE\n        description: Remove app from space\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-appid-data-metadata\n      path: /apps/{appId}/data/metadata\n      operations:\n      - name: getappdatametadata\n        method: GET\n        description: Retrieve data metadata for an app\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-appid-data-lineage\n      path: /apps/{appId}/data/lineage\n\
  \      operations:\n      - name: getappdatalineage\n        method: GET\n        description: Retrieve data lineage for an app\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-appid-scripts\n      path: /apps/{appId}/scripts\n      operations:\n      - name: getappscripts\n        method: GET\n        description: Retrieve script history\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setappscript\n        method: POST\n        description: Set script for an app\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-appid-reloads-logs\n      path: /apps/{appId}/reloads/logs\n      operations:\n      - name: getappreloadlogs\n        method: GET\n        description: Retrieve script log metadata\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps-appid-reloads-logs-reloadid\n      path: /apps/{appId}/reloads/logs/{reloadId}\n      operations:\n      - name: getappreloadlog\n        method: GET\n        description: Retrieve a specific reload log\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spaces\n      path: /spaces\n      operations:\n      - name: listspaces\n        method: GET\n        description: List spaces\n        inputParameters:\n        - name: action\n          in: query\n          type: string\n          description: Filter by action the user has access to.\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of spaces to return.\n        - name: name\n          in: query\n          type: string\n          description: Filter by space name.\n    \
  \    - name: next\n          in: query\n          type: string\n          description: Cursor for next page of results.\n        - name: ownerId\n          in: query\n          type: string\n          description: Filter by owner identifier.\n        - name: prev\n          in: query\n          type: string\n          description: Cursor for previous page of results.\n        - name: sort\n          in: query\n          type: string\n          description: Sort field and order.\n        - name: type\n          in: query\n          type: string\n          description: Filter by space type.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createspace\n        method: POST\n        description: Create a space\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spaces-spaceid\n      path: /spaces/{spaceId}\n   \
  \   operations:\n      - name: getspace\n        method: GET\n        description: Retrieve a space\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatespace\n        method: PUT\n        description: Update a space\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchspace\n        method: PATCH\n        description: Patch space properties\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletespace\n        method: DELETE\n        description: Delete a space\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spaces-spaceid-assignments\n      path: /spaces/{spaceId}/assignments\n      operations:\n      - name: listspaceassignments\n\
  \        method: GET\n        description: List space assignments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createspaceassignment\n        method: POST\n        description: Assign user or group to space\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spaces-spaceid-assignments-assignmentid\n      path: /spaces/{spaceId}/assignments/{assignmentId}\n      operations:\n      - name: getspaceassignment\n        method: GET\n        description: Retrieve a space assignment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatespaceassignment\n        method: PUT\n        description: Update a space assignment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: deletespaceassignment\n        method: DELETE\n        description: Delete a space assignment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spaces-types\n      path: /spaces/types\n      operations:\n      - name: listspacetypes\n        method: GET\n        description: List space types\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reloads\n      path: /reloads\n      operations:\n      - name: listreloads\n        method: GET\n        description: List reloads\n        inputParameters:\n        - name: appId\n          in: query\n          type: string\n          required: true\n          description: The identifier of the app to list reloads for.\n        - name: filter\n          in: query\n          type: string\n          description: SCIM filter expression for\
  \ advanced filtering of reload records.\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of reload records to return.\n        - name: log\n          in: query\n          type: boolean\n          description: When true, includes the script log in the response.\n        - name: next\n          in: query\n          type: string\n          description: Cursor for the next page of results.\n        - name: prev\n          in: query\n          type: string\n          description: Cursor for the previous page of results.\n        - name: partial\n          in: query\n          type: boolean\n          description: When true, returns partial reload information.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: reloadapp\n        method: POST\n        description: Reload an app\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n    - name: reloads-reloadid\n      path: /reloads/{reloadId}\n      operations:\n      - name: getreload\n        method: GET\n        description: Retrieve a reload record\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reloads-reloadid-actions-cancel\n      path: /reloads/{reloadId}/actions/cancel\n      operations:\n      - name: cancelreload\n        method: POST\n        description: Cancel a reload\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: qlik-sense-rest\n    description: REST adapter for Qlik Cloud REST API.\n    resources:\n    - path: /apps\n      name: getappsprivileges\n      operations:\n      - method: GET\n        name: getappsprivileges\n        description: Get app privileges\n\
  \        call: qlik-sense.getappsprivileges\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps\n      name: createapp\n      operations:\n      - method: POST\n        name: createapp\n        description: Create an app\n        call: qlik-sense.createapp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{appId}\n      name: getapp\n      operations:\n      - method: GET\n        name: getapp\n        description: Retrieve an app\n        call: qlik-sense.getapp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{appId}\n      name: updateapp\n      operations:\n      - method: PUT\n        name: updateapp\n        description: Update an app\n        call: qlik-sense.updateapp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{appId}\n      name: deleteapp\n      operations:\n      - method: DELETE\n        name: deleteapp\n\
  \        description: Delete an app\n        call: qlik-sense.deleteapp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{appId}/copy\n      name: copyapp\n      operations:\n      - method: POST\n        name: copyapp\n        description: Copy an app\n        call: qlik-sense.copyapp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{appId}/export\n      name: exportapp\n      operations:\n      - method: POST\n        name: exportapp\n        description: Export an app\n        call: qlik-sense.exportapp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/import\n      name: importapp\n      operations:\n      - method: POST\n        name: importapp\n        description: Import an app\n        call: qlik-sense.importapp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{appId}/publish\n      name: publishapp\n    \
  \  operations:\n      - method: POST\n        name: publishapp\n        description: Publish an app\n        call: qlik-sense.publishapp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{appId}/publish\n      name: republishapp\n      operations:\n      - method: PUT\n        name: republishapp\n        description: Republish an app\n        call: qlik-sense.republishapp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{appId}/owner\n      name: updateappowner\n      operations:\n      - method: PUT\n        name: updateappowner\n        description: Change app owner\n        call: qlik-sense.updateappowner\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{appId}/space\n      name: moveapptospace\n      operations:\n      - method: PUT\n        name: moveapptospace\n        description: Move app to a space\n        call: qlik-sense.moveapptospace\n       \
  \ outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{appId}/space\n      name: removeappfromspace\n      operations:\n      - method: DELETE\n        name: removeappfromspace\n        description: Remove app from space\n        call: qlik-sense.removeappfromspace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{appId}/data/metadata\n      name: getappdatametadata\n      operations:\n      - method: GET\n        name: getappdatametadata\n        description: Retrieve data metadata for an app\n        call: qlik-sense.getappdatametadata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{appId}/data/lineage\n      name: getappdatalineage\n      operations:\n      - method: GET\n        name: getappdatalineage\n        description: Retrieve data lineage for an app\n        call: qlik-sense.getappdatalineage\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /apps/{appId}/scripts\n      name: getappscripts\n      operations:\n      - method: GET\n        name: getappscripts\n        description: Retrieve script history\n        call: qlik-sense.getappscripts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{appId}/scripts\n      name: setappscript\n      operations:\n      - method: POST\n        name: setappscript\n        description: Set script for an app\n        call: qlik-sense.setappscript\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{appId}/reloads/logs\n      name: getappreloadlogs\n      operations:\n      - method: GET\n        name: getappreloadlogs\n        description: Retrieve script log metadata\n        call: qlik-sense.getappreloadlogs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apps/{appId}/reloads/logs/{reloadId}\n      name: getappreloadlog\n      operations:\n      -\
  \ method: GET\n        name: getappreloadlog\n        description: Retrieve a specific reload log\n        call: qlik-sense.getappreloadlog\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces\n      name: listspaces\n      operations:\n      - method: GET\n        name: listspaces\n        description: List spaces\n        call: qlik-sense.listspaces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces\n      name: createspace\n      operations:\n      - method: POST\n        name: createspace\n        description: Create a space\n        call: qlik-sense.createspace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}\n      name: getspace\n      operations:\n      - method: GET\n        name: getspace\n        description: Retrieve a space\n        call: qlik-sense.getspace\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /spaces/{spaceId}\n      name: updatespace\n      operations:\n      - method: PUT\n        name: updatespace\n        description: Update a space\n        call: qlik-sense.updatespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}\n      name: patchspace\n      operations:\n      - method: PATCH\n        name: patchspace\n        description: Patch space properties\n        call: qlik-sense.patchspace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}\n      name: deletespace\n      operations:\n      - method: DELETE\n        name: deletespace\n        description: Delete a space\n        call: qlik-sense.deletespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}/assignments\n      name: listspaceassignments\n      operations:\n      - method: GET\n        name: listspaceassignments\n        description:\
  \ List space assignments\n        call: qlik-sense.listspaceassignments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}/assignments\n      name: createspaceassignment\n      operations:\n      - method: POST\n        name: createspaceassignment\n        description: Assign user or group to space\n        call: qlik-sense.createspaceassignment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}/assignments/{assignmentId}\n      name: getspaceassignment\n      operations:\n      - method: GET\n        name: getspaceassignment\n        description: Retrieve a space assignment\n        call: qlik-sense.getspaceassignment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}/assignments/{assignmentId}\n      name: updatespaceassignment\n      operations:\n      - method: PUT\n        name: updatespaceassignment\n        description:\
  \ Update a space assignment\n        call: qlik-sense.updatespaceassignment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/{spaceId}/assignments/{assignmentId}\n      name: deletespaceassignment\n      operations:\n      - method: DELETE\n        name: deletespaceassignment\n        description: Delete a space assignment\n        call: qlik-sense.deletespaceassignment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /spaces/types\n      name: listspacetypes\n      operations:\n      - method: GET\n        name: listspacetypes\n        description: List space types\n        call: qlik-sense.listspacetypes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reloads\n      name: listreloads\n      operations:\n      - method: GET\n        name: listreloads\n        description: List reloads\n        call: qlik-sense.listreloads\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /reloads\n      name: reloadapp\n      operations:\n      - method: POST\n        name: reloadapp\n        description: Reload an app\n        call: qlik-sense.reloadapp\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reloads/{reloadId}\n      name: getreload\n      operations:\n      - method: GET\n        name: getreload\n        description: Retrieve a reload record\n        call: qlik-sense.getreload\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reloads/{reloadId}/actions/cancel\n      name: cancelreload\n      operations:\n      - method: POST\n        name: cancelreload\n        description: Cancel a reload\n        call: qlik-sense.cancelreload\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: qlik-sense-mcp\n    transport: http\n    description: MCP adapter for Qlik Cloud REST API for\
  \ AI agent use.\n    tools:\n    - name: getappsprivileges\n      description: Get app privileges\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: qlik-sense.getappsprivileges\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createapp\n      description: Create an app\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: qlik-sense.createapp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapp\n      description: Retrieve an app\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: qlik-sense.getapp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateapp\n      description: Update an app\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: qlik-sense.updateapp\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: deleteapp\n      description: Delete an app\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: qlik-sense.deleteapp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: copyapp\n      description: Copy an app\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: qlik-sense.copyapp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: exportapp\n      description: Export an app\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: qlik-sense.exportapp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: importapp\n      description: Import an app\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: qlik-sense.importapp\n      with:\n      \
  \  name: tools.name\n        spaceId: tools.spaceId\n        mode: tools.mode\n      inputParameters:\n      - name: name\n        type: string\n        description: The name of the target app.\n      - name: spaceId\n        type: string\n        description: The space identifier to import the app into. Uses personal space if omitted.\n      - name: mode\n        type: string\n        description: The import mode for the app.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publishapp\n      description: Publish an app\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: qlik-sense.publishapp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: republishapp\n      description: Republish an app\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: qlik-sense.republishapp\n      outputParameters:\n      - type: object\n   \
  \     mapping: $.\n    - name: updateappowner\n      description: Change app owner\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: qlik-sense.updateappowner\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: moveapptospace\n      description: Move app to a space\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: qlik-sense.moveapptospace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: removeappfromspace\n      description: Remove app from space\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: qlik-sense.removeappfromspace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getappdatametadata\n      description: Retrieve data metadata for an app\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: qlik-sense.getappdatametadata\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getappdatalineage\n      description: Retrieve data lineage for an app\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: qlik-sense.getappdatalineage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getappscripts\n      description: Retrieve script history\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: qlik-sense.getappscripts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: setappscript\n      description: Set script for an app\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: qlik-sense.setappscript\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getappreloadlogs\n      description: Retrieve script\
  \ log metadata\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: qlik-sense.getappreloadlogs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getappreloadlog\n      description: Retrieve a specific reload log\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: qlik-sense.getappreloadlog\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listspaces\n      description: List spaces\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: qlik-sense.listspaces\n      with:\n        action: tools.action\n        limit: tools.limit\n        name: tools.name\n        next: tools.next\n        ownerId: tools.ownerId\n        prev: tools.prev\n        sort: tools.sort\n        type: tools.type\n      inputParameters:\n      - name: action\n        type: string\n        description:\
  \ Filter by action the user has access to.\n      - name: limit\n        type: integer\n        description: Maximum number of spaces to return.\n      - name: name\n        type: string\n        description: Filter by space name.\n      - name: next\n        type: string\n        description: Cursor for next page of results.\n      - name: ownerId\n        type: string\n        description: Filter by owner identifier.\n      - name: prev\n        type: string\n        description: Cursor for previous page of results.\n      - name: sort\n        type: string\n        description: Sort field and order.\n      - name: type\n        type: string\n        description: Filter by space type.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createspace\n      description: Create a space\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: qlik-sense.createspace\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: getspace\n      description: Retrieve a space\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: qlik-sense.getspace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatespace\n      description: Update a space\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: qlik-sense.updatespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchspace\n      description: Patch space properties\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: qlik-sense.patchspace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletespace\n      description: Delete a space\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: qlik-sense.deletespace\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: listspaceassignments\n      description: List space assignments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: qlik-sense.listspaceassignments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createspaceassignment\n      description: Assign user or group to space\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: qlik-sense.createspaceassignment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getspaceassignment\n      description: Retrieve a space assignment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: qlik-sense.getspaceassignment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatespaceassignment\n      description: Update a space assignment\n      hints:\n  \
  \      readOnly: false\n        destructive: false\n        idempotent: true\n      call: qlik-sense.updatespaceassignment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletespaceassignment\n      description: Delete a space assignment\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: qlik-sense.deletespaceassignment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listspacetypes\n      description: List space types\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: qlik-sense.listspacetypes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listreloads\n      description: List reloads\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: qlik-sense.listreloads\n      with:\n        appId: tools.appId\n        filter: tools.filter\n\
  \        limit: tools.limit\n        log: tools.log\n        next: tools.next\n        prev: tools.prev\n        partial: tools.partial\n      inputParameters:\n      - name: appId\n        type: string\n        description: The identifier of the app to list reloads for.\n        required: true\n      - name: filter\n        type: string\n        description: SCIM filter expression for advanced filtering of reload records.\n      - name: limit\n        type: integer\n        description: Maximum number of reload records to return.\n      - name: log\n        type: boolean\n        description: When true, includes the script log in the response.\n      - name: next\n        type: string\n        description: Cursor for the next page of results.\n      - name: prev\n        type: string\n        description: Cursor for the previous page of results.\n      - name: partial\n        type: boolean\n        descripti\n\n# --- truncated at 32 KB (32 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/qlik-sense/refs/heads/main/capabilities/qlik-sense-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/qlik-sense/refs/heads/main/capabilities/qlik-sense-capability.yaml
tags:
- Qlik
- Sense
- API
tools:
- description: Get app privileges
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getappsprivileges
- description: Create an app
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapp
- description: Retrieve an app
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapp
- description: Update an app
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateapp
- description: Delete an app
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapp
- description: Copy an app
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: copyapp
- description: Export an app
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: exportapp
- description: Import an app
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: importapp
- description: Publish an app
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: publishapp
- description: Republish an app
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: republishapp
- description: Change app owner
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateappowner
- description: Move app to a space
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: moveapptospace
- description: Remove app from space
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removeappfromspace
- description: Retrieve data metadata for an app
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getappdatametadata
- description: Retrieve data lineage for an app
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getappdatalineage
- description: Retrieve script history
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getappscripts
- description: Set script for an app
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: setappscript
- description: Retrieve script log metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getappreloadlogs
- description: Retrieve a specific reload log
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getappreloadlog
- description: List spaces
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listspaces
- description: Create a space
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createspace
- description: Retrieve a space
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getspace
- description: Update a space
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatespace
- description: Patch space properties
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchspace
- description: Delete a space
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletespace
- description: List space assignments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listspaceassignments
- description: Assign user or group to space
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createspaceassignment
- description: Retrieve a space assignment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getspaceassignment
- description: Update a space assignment
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatespaceassignment
- description: Delete a space assignment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletespaceassignment
- description: List space types
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listspacetypes
- description: List reloads
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listreloads
- description: Reload an app
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: reloadapp
- description: Retrieve a reload record
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreload
- description: Cancel a reload
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: cancelreload
---
