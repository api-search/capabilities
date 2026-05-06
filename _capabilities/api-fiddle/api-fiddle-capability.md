---
categories: []
consumed_apis: []
description: The API Fiddle API provides programmatic access to the API Fiddle design platform, enabling management of projects, specifications, workspaces, sharing, and export capabilities. It allows developers to automate API design workflows, collaborate on OpenAPI specifications, and integrate API Fiddle into their development pipelines.
layout: capability
name: API-Fiddle API Fiddle API
operations:
- description: API-Fiddle List projects
  method: GET
  name: listprojects
  path: /projects
- description: API-Fiddle Create a project
  method: POST
  name: createproject
  path: /projects
- description: API-Fiddle Get a project
  method: GET
  name: getproject
  path: /projects/{projectId}
- description: API-Fiddle Update a project
  method: PUT
  name: updateproject
  path: /projects/{projectId}
- description: API-Fiddle Delete a project
  method: DELETE
  name: deleteproject
  path: /projects/{projectId}
- description: API-Fiddle List specifications
  method: GET
  name: listspecifications
  path: /projects/{projectId}/specifications
- description: API-Fiddle Create a specification
  method: POST
  name: createspecification
  path: /projects/{projectId}/specifications
- description: API-Fiddle Get a specification
  method: GET
  name: getspecification
  path: /projects/{projectId}/specifications/{specificationId}
- description: API-Fiddle Update a specification
  method: PUT
  name: updatespecification
  path: /projects/{projectId}/specifications/{specificationId}
- description: API-Fiddle Delete a specification
  method: DELETE
  name: deletespecification
  path: /projects/{projectId}/specifications/{specificationId}
- description: API-Fiddle List workspaces
  method: GET
  name: listworkspaces
  path: /workspaces
- description: API-Fiddle Create a workspace
  method: POST
  name: createworkspace
  path: /workspaces
- description: API-Fiddle Get a workspace
  method: GET
  name: getworkspace
  path: /workspaces/{workspaceId}
- description: API-Fiddle Update a workspace
  method: PUT
  name: updateworkspace
  path: /workspaces/{workspaceId}
- description: API-Fiddle Delete a workspace
  method: DELETE
  name: deleteworkspace
  path: /workspaces/{workspaceId}
- description: API-Fiddle List sharing settings
  method: GET
  name: listsharing
  path: /projects/{projectId}/sharing
- description: API-Fiddle Share a project
  method: POST
  name: shareproject
  path: /projects/{projectId}/sharing
- description: API-Fiddle Remove sharing
  method: DELETE
  name: removesharing
  path: /projects/{projectId}/sharing/{sharingId}
- description: API-Fiddle Export a project
  method: POST
  name: exportproject
  path: /projects/{projectId}/export
personas: []
provider_name: API-Fiddle
provider_slug: api-fiddle
search_terms:
- deletespecification
- listworkspaces
- api-fiddle create a specification
- fiddle
- getworkspace
- api-fiddle create a project
- createworkspace
- api-fiddle update a project
- deleteproject
- api-fiddle delete a workspace
- api-fiddle list projects
- api-fiddle list sharing settings
- api-fiddle update a specification
- deleteworkspace
- updatespecification
- createspecification
- api-fiddle delete a specification
- updateproject
- api-fiddle share a project
- api-fiddle get a workspace
- exportproject
- getspecification
- api-fiddle get a specification
- getproject
- api design
- documentation
- openapi
- listsharing
- api-fiddle list workspaces
- api
- api-fiddle create a workspace
- listprojects
- removesharing
- api-fiddle export a project
- api-fiddle get a project
- listspecifications
- platform
- api-fiddle list specifications
- api-fiddle remove sharing
- shareproject
- updateworkspace
- api-fiddle delete a project
- collaboration
- createproject
- api-fiddle update a workspace
slug: api-fiddle-capability
source_filename: api-fiddle-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: API-Fiddle API Fiddle API\n  description: The API Fiddle API provides programmatic access to the API Fiddle design platform, enabling management of projects,\n    specifications, workspaces, sharing, and export capabilities. It allows developers to automate API design workflows, collaborate\n    on OpenAPI specifications, and integrate API Fiddle into their development pipelines.\n  tags:\n  - Api\n  - Fiddle\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: api-fiddle\n    baseUri: https://api.api-fiddle.com/v1\n    description: API-Fiddle API Fiddle API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{API_FIDDLE_TOKEN}}'\n    resources:\n    - name: projects\n      path: /projects\n      operations:\n      - name: listprojects\n        method: GET\n        description: API-Fiddle List projects\n        inputParameters:\n        - name: limit\n    \
  \      in: query\n          type: integer\n          description: Maximum number of projects to return.\n        - name: offset\n          in: query\n          type: integer\n          description: Number of projects to skip for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createproject\n        method: POST\n        description: API-Fiddle Create a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid\n      path: /projects/{projectId}\n      operations:\n      - name: getproject\n        method: GET\n        description: API-Fiddle Get a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateproject\n        method: PUT\n        description: API-Fiddle Update a project\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteproject\n        method: DELETE\n        description: API-Fiddle Delete a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-specifications\n      path: /projects/{projectId}/specifications\n      operations:\n      - name: listspecifications\n        method: GET\n        description: API-Fiddle List specifications\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createspecification\n        method: POST\n        description: API-Fiddle Create a specification\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-specifications-specificationi\n\
  \      path: /projects/{projectId}/specifications/{specificationId}\n      operations:\n      - name: getspecification\n        method: GET\n        description: API-Fiddle Get a specification\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatespecification\n        method: PUT\n        description: API-Fiddle Update a specification\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletespecification\n        method: DELETE\n        description: API-Fiddle Delete a specification\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces\n      path: /workspaces\n      operations:\n      - name: listworkspaces\n        method: GET\n        description: API-Fiddle List workspaces\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createworkspace\n        method: POST\n        description: API-Fiddle Create a workspace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces-workspaceid\n      path: /workspaces/{workspaceId}\n      operations:\n      - name: getworkspace\n        method: GET\n        description: API-Fiddle Get a workspace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateworkspace\n        method: PUT\n        description: API-Fiddle Update a workspace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteworkspace\n        method: DELETE\n        description: API-Fiddle Delete a workspace\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-sharing\n      path: /projects/{projectId}/sharing\n      operations:\n      - name: listsharing\n        method: GET\n        description: API-Fiddle List sharing settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: shareproject\n        method: POST\n        description: API-Fiddle Share a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-sharing-sharingid\n      path: /projects/{projectId}/sharing/{sharingId}\n      operations:\n      - name: removesharing\n        method: DELETE\n        description: API-Fiddle Remove sharing\n        inputParameters:\n        - name: sharingId\n          in: path\n          type: string\n          required:\
  \ true\n          description: The unique identifier of the sharing entry.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-export\n      path: /projects/{projectId}/export\n      operations:\n      - name: exportproject\n        method: POST\n        description: API-Fiddle Export a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: api-fiddle-rest\n    description: REST adapter for API-Fiddle API Fiddle API.\n    resources:\n    - path: /projects\n      name: listprojects\n      operations:\n      - method: GET\n        name: listprojects\n        description: API-Fiddle List projects\n        call: api-fiddle.listprojects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects\n      name: createproject\n\
  \      operations:\n      - method: POST\n        name: createproject\n        description: API-Fiddle Create a project\n        call: api-fiddle.createproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}\n      name: getproject\n      operations:\n      - method: GET\n        name: getproject\n        description: API-Fiddle Get a project\n        call: api-fiddle.getproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}\n      name: updateproject\n      operations:\n      - method: PUT\n        name: updateproject\n        description: API-Fiddle Update a project\n        call: api-fiddle.updateproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}\n      name: deleteproject\n      operations:\n      - method: DELETE\n        name: deleteproject\n        description: API-Fiddle Delete a project\n  \
  \      call: api-fiddle.deleteproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/specifications\n      name: listspecifications\n      operations:\n      - method: GET\n        name: listspecifications\n        description: API-Fiddle List specifications\n        call: api-fiddle.listspecifications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/specifications\n      name: createspecification\n      operations:\n      - method: POST\n        name: createspecification\n        description: API-Fiddle Create a specification\n        call: api-fiddle.createspecification\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/specifications/{specificationId}\n      name: getspecification\n      operations:\n      - method: GET\n        name: getspecification\n        description: API-Fiddle Get a specification\n\
  \        call: api-fiddle.getspecification\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/specifications/{specificationId}\n      name: updatespecification\n      operations:\n      - method: PUT\n        name: updatespecification\n        description: API-Fiddle Update a specification\n        call: api-fiddle.updatespecification\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/specifications/{specificationId}\n      name: deletespecification\n      operations:\n      - method: DELETE\n        name: deletespecification\n        description: API-Fiddle Delete a specification\n        call: api-fiddle.deletespecification\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces\n      name: listworkspaces\n      operations:\n      - method: GET\n        name: listworkspaces\n        description: API-Fiddle List workspaces\n  \
  \      call: api-fiddle.listworkspaces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces\n      name: createworkspace\n      operations:\n      - method: POST\n        name: createworkspace\n        description: API-Fiddle Create a workspace\n        call: api-fiddle.createworkspace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceId}\n      name: getworkspace\n      operations:\n      - method: GET\n        name: getworkspace\n        description: API-Fiddle Get a workspace\n        call: api-fiddle.getworkspace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceId}\n      name: updateworkspace\n      operations:\n      - method: PUT\n        name: updateworkspace\n        description: API-Fiddle Update a workspace\n        call: api-fiddle.updateworkspace\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /workspaces/{workspaceId}\n      name: deleteworkspace\n      operations:\n      - method: DELETE\n        name: deleteworkspace\n        description: API-Fiddle Delete a workspace\n        call: api-fiddle.deleteworkspace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/sharing\n      name: listsharing\n      operations:\n      - method: GET\n        name: listsharing\n        description: API-Fiddle List sharing settings\n        call: api-fiddle.listsharing\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/sharing\n      name: shareproject\n      operations:\n      - method: POST\n        name: shareproject\n        description: API-Fiddle Share a project\n        call: api-fiddle.shareproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/sharing/{sharingId}\n      name: removesharing\n\
  \      operations:\n      - method: DELETE\n        name: removesharing\n        description: API-Fiddle Remove sharing\n        call: api-fiddle.removesharing\n        with:\n          sharingId: rest.sharingId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/export\n      name: exportproject\n      operations:\n      - method: POST\n        name: exportproject\n        description: API-Fiddle Export a project\n        call: api-fiddle.exportproject\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: api-fiddle-mcp\n    transport: http\n    description: MCP adapter for API-Fiddle API Fiddle API for AI agent use.\n    tools:\n    - name: listprojects\n      description: API-Fiddle List projects\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: api-fiddle.listprojects\n      with:\n        limit: tools.limit\n\
  \        offset: tools.offset\n      inputParameters:\n      - name: limit\n        type: integer\n        description: Maximum number of projects to return.\n      - name: offset\n        type: integer\n        description: Number of projects to skip for pagination.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createproject\n      description: API-Fiddle Create a project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: api-fiddle.createproject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproject\n      description: API-Fiddle Get a project\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: api-fiddle.getproject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateproject\n      description: API-Fiddle Update a project\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: true\n      call: api-fiddle.updateproject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteproject\n      description: API-Fiddle Delete a project\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: api-fiddle.deleteproject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listspecifications\n      description: API-Fiddle List specifications\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: api-fiddle.listspecifications\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createspecification\n      description: API-Fiddle Create a specification\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: api-fiddle.createspecification\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ getspecification\n      description: API-Fiddle Get a specification\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: api-fiddle.getspecification\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatespecification\n      description: API-Fiddle Update a specification\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: api-fiddle.updatespecification\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletespecification\n      description: API-Fiddle Delete a specification\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: api-fiddle.deletespecification\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listworkspaces\n      description: API-Fiddle List workspaces\n      hints:\n        readOnly: true\n        destructive: false\n   \
  \     idempotent: true\n      call: api-fiddle.listworkspaces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createworkspace\n      description: API-Fiddle Create a workspace\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: api-fiddle.createworkspace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getworkspace\n      description: API-Fiddle Get a workspace\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: api-fiddle.getworkspace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateworkspace\n      description: API-Fiddle Update a workspace\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: api-fiddle.updateworkspace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteworkspace\n      description:\
  \ API-Fiddle Delete a workspace\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: api-fiddle.deleteworkspace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsharing\n      description: API-Fiddle List sharing settings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: api-fiddle.listsharing\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: shareproject\n      description: API-Fiddle Share a project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: api-fiddle.shareproject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: removesharing\n      description: API-Fiddle Remove sharing\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: api-fiddle.removesharing\n      with:\n    \
  \    sharingId: tools.sharingId\n      inputParameters:\n      - name: sharingId\n        type: string\n        description: The unique identifier of the sharing entry.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: exportproject\n      description: API-Fiddle Export a project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: api-fiddle.exportproject\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    API_FIDDLE_TOKEN: API_FIDDLE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/api-fiddle/refs/heads/main/capabilities/api-fiddle-capability.yaml
tags:
- Api
- Fiddle
- API
tools:
- description: API-Fiddle List projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojects
- description: API-Fiddle Create a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createproject
- description: API-Fiddle Get a project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproject
- description: API-Fiddle Update a project
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateproject
- description: API-Fiddle Delete a project
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteproject
- description: API-Fiddle List specifications
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listspecifications
- description: API-Fiddle Create a specification
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createspecification
- description: API-Fiddle Get a specification
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getspecification
- description: API-Fiddle Update a specification
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatespecification
- description: API-Fiddle Delete a specification
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletespecification
- description: API-Fiddle List workspaces
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listworkspaces
- description: API-Fiddle Create a workspace
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createworkspace
- description: API-Fiddle Get a workspace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getworkspace
- description: API-Fiddle Update a workspace
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateworkspace
- description: API-Fiddle Delete a workspace
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteworkspace
- description: API-Fiddle List sharing settings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsharing
- description: API-Fiddle Share a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: shareproject
- description: API-Fiddle Remove sharing
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removesharing
- description: API-Fiddle Export a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: exportproject
---
