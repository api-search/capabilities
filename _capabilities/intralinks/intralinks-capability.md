---
categories: []
consumed_apis: []
description: The Intralinks API provides RESTful access to the Intralinks virtual data room platform, enabling programmatic management of workspaces (exchanges), documents, folders, groups, users, permissions, splash screens, and custom fields. It supports secure document sharing, M&A due diligence workflows, and confidential business collaboration. Authentication is handled via OAuth 2.0 with authorization code and client credentials flows.
layout: capability
name: Intralinks API
operations:
- description: Intralinks Obtain OAuth Token
  method: POST
  name: getoauthtoken
  path: /oauth/token
- description: Intralinks Revoke OAuth Token
  method: POST
  name: revokeoauthtoken
  path: /oauth/revoke
- description: Intralinks List Workspaces
  method: GET
  name: listworkspaces
  path: /workspaces
- description: Intralinks Create Workspace
  method: POST
  name: createworkspace
  path: /workspaces
- description: Intralinks Get Workspace
  method: GET
  name: getworkspace
  path: /workspaces/{workspaceId}
- description: Intralinks Update Workspace
  method: PUT
  name: updateworkspace
  path: /workspaces/{workspaceId}
- description: Intralinks Delete Workspace
  method: DELETE
  name: deleteworkspace
  path: /workspaces/{workspaceId}
- description: Intralinks List Folders
  method: GET
  name: listfolders
  path: /workspaces/{workspaceId}/folders
- description: Intralinks Create Folder
  method: POST
  name: createfolder
  path: /workspaces/{workspaceId}/folders
- description: Intralinks Get Folder
  method: GET
  name: getfolder
  path: /workspaces/{workspaceId}/folders/{folderId}
- description: Intralinks Update Folder
  method: PUT
  name: updatefolder
  path: /workspaces/{workspaceId}/folders/{folderId}
- description: Intralinks Delete Folder
  method: DELETE
  name: deletefolder
  path: /workspaces/{workspaceId}/folders/{folderId}
- description: Intralinks List Documents
  method: GET
  name: listdocuments
  path: /workspaces/{workspaceId}/documents
- description: Intralinks Upload Document
  method: POST
  name: uploaddocument
  path: /workspaces/{workspaceId}/documents
- description: Intralinks Get Document
  method: GET
  name: getdocument
  path: /workspaces/{workspaceId}/documents/{documentId}
- description: Intralinks Update Document
  method: PUT
  name: updatedocument
  path: /workspaces/{workspaceId}/documents/{documentId}
- description: Intralinks Delete Document
  method: DELETE
  name: deletedocument
  path: /workspaces/{workspaceId}/documents/{documentId}
- description: Intralinks Download Document
  method: GET
  name: downloaddocument
  path: /workspaces/{workspaceId}/documents/{documentId}/download
- description: Intralinks List Groups
  method: GET
  name: listgroups
  path: /workspaces/{workspaceId}/groups
- description: Intralinks Create Group
  method: POST
  name: creategroup
  path: /workspaces/{workspaceId}/groups
- description: Intralinks Get Group
  method: GET
  name: getgroup
  path: /workspaces/{workspaceId}/groups/{groupId}
- description: Intralinks Update Group
  method: PUT
  name: updategroup
  path: /workspaces/{workspaceId}/groups/{groupId}
- description: Intralinks Delete Group
  method: DELETE
  name: deletegroup
  path: /workspaces/{workspaceId}/groups/{groupId}
- description: Intralinks List Group Members
  method: GET
  name: listgroupmembers
  path: /workspaces/{workspaceId}/groups/{groupId}/members
- description: Intralinks Add Group Member
  method: POST
  name: addgroupmember
  path: /workspaces/{workspaceId}/groups/{groupId}/members
- description: Intralinks List Permissions
  method: GET
  name: listpermissions
  path: /workspaces/{workspaceId}/permissions
- description: Intralinks Create Permission
  method: POST
  name: createpermission
  path: /workspaces/{workspaceId}/permissions
- description: Intralinks Get Splash Screen
  method: GET
  name: getsplash
  path: /workspaces/{workspaceId}/splash
- description: Intralinks Update Splash Screen
  method: PUT
  name: updatesplash
  path: /workspaces/{workspaceId}/splash
- description: Intralinks List Custom Fields
  method: GET
  name: listcustomfields
  path: /workspaces/{workspaceId}/customfields
personas: []
provider_name: Intralinks
provider_slug: intralinks
search_terms:
- intralinks get folder
- deletedocument
- intralinks update group
- uploaddocument
- intralinks update folder
- intralinks delete document
- intralinks list group members
- intralinks create permission
- intralinks update splash screen
- intralinks list documents
- document management
- creategroup
- listworkspaces
- updateworkspace
- getoauthtoken
- api
- createpermission
- addgroupmember
- listfolders
- intralinks obtain oauth token
- intralinks create group
- getsplash
- intralinks get document
- downloaddocument
- secure file sharing
- listgroupmembers
- getgroup
- listgroups
- revokeoauthtoken
- intralinks create folder
- updategroup
- intralinks update document
- virtual data room
- listcustomfields
- intralinks upload document
- intralinks list folders
- intralinks get group
- intralinks get splash screen
- intralinks list custom fields
- intralinks get workspace
- intralinks create workspace
- intralinks delete folder
- intralinks delete group
- intralinks update workspace
- intralinks list permissions
- createworkspace
- listpermissions
- listdocuments
- createfolder
- updatedocument
- getfolder
- intralinks list groups
- deletefolder
- intralinks add group member
- updatesplash
- intralinks
- intralinks list workspaces
- getworkspace
- getdocument
- intralinks revoke oauth token
- deleteworkspace
- intralinks delete workspace
- intralinks download document
- deletegroup
- updatefolder
slug: intralinks-capability
source_filename: intralinks-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Intralinks API\n  description: The Intralinks API provides RESTful access to the Intralinks virtual data room platform, enabling programmatic\n    management of workspaces (exchanges), documents, folders, groups, users, permissions, splash screens, and custom fields.\n    It supports secure document sharing, M&A due diligence workflows, and confidential business collaboration. Authentication\n    is handled via OAuth 2.0 with authorization code and client credentials flows.\n  tags:\n  - Intralinks\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: intralinks\n    baseUri: https://api.intralinks.com/v2\n    description: Intralinks API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{INTRALINKS_TOKEN}}'\n    resources:\n    - name: oauth-token\n      path: /oauth/token\n      operations:\n      - name: getoauthtoken\n        method: POST\n        description:\
  \ Intralinks Obtain OAuth Token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oauth-revoke\n      path: /oauth/revoke\n      operations:\n      - name: revokeoauthtoken\n        method: POST\n        description: Intralinks Revoke OAuth Token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces\n      path: /workspaces\n      operations:\n      - name: listworkspaces\n        method: GET\n        description: Intralinks List Workspaces\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n        - name: offset\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      -\
  \ name: createworkspace\n        method: POST\n        description: Intralinks Create Workspace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces-workspaceid\n      path: /workspaces/{workspaceId}\n      operations:\n      - name: getworkspace\n        method: GET\n        description: Intralinks Get Workspace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateworkspace\n        method: PUT\n        description: Intralinks Update Workspace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteworkspace\n        method: DELETE\n        description: Intralinks Delete Workspace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: workspaces-workspaceid-folders\n      path: /workspaces/{workspaceId}/folders\n      operations:\n      - name: listfolders\n        method: GET\n        description: Intralinks List Folders\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createfolder\n        method: POST\n        description: Intralinks Create Folder\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces-workspaceid-folders-folderid\n      path: /workspaces/{workspaceId}/folders/{folderId}\n      operations:\n      - name: getfolder\n        method: GET\n        description: Intralinks Get Folder\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatefolder\n        method: PUT\n        description: Intralinks Update Folder\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletefolder\n        method: DELETE\n        description: Intralinks Delete Folder\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces-workspaceid-documents\n      path: /workspaces/{workspaceId}/documents\n      operations:\n      - name: listdocuments\n        method: GET\n        description: Intralinks List Documents\n        inputParameters:\n        - name: folderId\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: uploaddocument\n        method: POST\n        description: Intralinks Upload Document\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n    - name: workspaces-workspaceid-documents-documentid\n      path: /workspaces/{workspaceId}/documents/{documentId}\n      operations:\n      - name: getdocument\n        method: GET\n        description: Intralinks Get Document\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatedocument\n        method: PUT\n        description: Intralinks Update Document\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedocument\n        method: DELETE\n        description: Intralinks Delete Document\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces-workspaceid-documents-documentid-down\n      path: /workspaces/{workspaceId}/documents/{documentId}/download\n      operations:\n      - name:\
  \ downloaddocument\n        method: GET\n        description: Intralinks Download Document\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces-workspaceid-groups\n      path: /workspaces/{workspaceId}/groups\n      operations:\n      - name: listgroups\n        method: GET\n        description: Intralinks List Groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: creategroup\n        method: POST\n        description: Intralinks Create Group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces-workspaceid-groups-groupid\n      path: /workspaces/{workspaceId}/groups/{groupId}\n      operations:\n      - name: getgroup\n        method: GET\n        description: Intralinks Get Group\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updategroup\n        method: PUT\n        description: Intralinks Update Group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletegroup\n        method: DELETE\n        description: Intralinks Delete Group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces-workspaceid-groups-groupid-members\n      path: /workspaces/{workspaceId}/groups/{groupId}/members\n      operations:\n      - name: listgroupmembers\n        method: GET\n        description: Intralinks List Group Members\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addgroupmember\n        method: POST\n        description: Intralinks\
  \ Add Group Member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces-workspaceid-permissions\n      path: /workspaces/{workspaceId}/permissions\n      operations:\n      - name: listpermissions\n        method: GET\n        description: Intralinks List Permissions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createpermission\n        method: POST\n        description: Intralinks Create Permission\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces-workspaceid-splash\n      path: /workspaces/{workspaceId}/splash\n      operations:\n      - name: getsplash\n        method: GET\n        description: Intralinks Get Splash Screen\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: updatesplash\n        method: PUT\n        description: Intralinks Update Splash Screen\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces-workspaceid-customfields\n      path: /workspaces/{workspaceId}/customfields\n      operations:\n      - name: listcustomfields\n        method: GET\n        description: Intralinks List Custom Fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: intralinks-rest\n    description: REST adapter for Intralinks API.\n    resources:\n    - path: /oauth/token\n      name: getoauthtoken\n      operations:\n      - method: POST\n        name: getoauthtoken\n        description: Intralinks Obtain OAuth Token\n        call: intralinks.getoauthtoken\n    \
  \    outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oauth/revoke\n      name: revokeoauthtoken\n      operations:\n      - method: POST\n        name: revokeoauthtoken\n        description: Intralinks Revoke OAuth Token\n        call: intralinks.revokeoauthtoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces\n      name: listworkspaces\n      operations:\n      - method: GET\n        name: listworkspaces\n        description: Intralinks List Workspaces\n        call: intralinks.listworkspaces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces\n      name: createworkspace\n      operations:\n      - method: POST\n        name: createworkspace\n        description: Intralinks Create Workspace\n        call: intralinks.createworkspace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceId}\n      name:\
  \ getworkspace\n      operations:\n      - method: GET\n        name: getworkspace\n        description: Intralinks Get Workspace\n        call: intralinks.getworkspace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceId}\n      name: updateworkspace\n      operations:\n      - method: PUT\n        name: updateworkspace\n        description: Intralinks Update Workspace\n        call: intralinks.updateworkspace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceId}\n      name: deleteworkspace\n      operations:\n      - method: DELETE\n        name: deleteworkspace\n        description: Intralinks Delete Workspace\n        call: intralinks.deleteworkspace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceId}/folders\n      name: listfolders\n      operations:\n      - method: GET\n        name: listfolders\n   \
  \     description: Intralinks List Folders\n        call: intralinks.listfolders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceId}/folders\n      name: createfolder\n      operations:\n      - method: POST\n        name: createfolder\n        description: Intralinks Create Folder\n        call: intralinks.createfolder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceId}/folders/{folderId}\n      name: getfolder\n      operations:\n      - method: GET\n        name: getfolder\n        description: Intralinks Get Folder\n        call: intralinks.getfolder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceId}/folders/{folderId}\n      name: updatefolder\n      operations:\n      - method: PUT\n        name: updatefolder\n        description: Intralinks Update Folder\n        call: intralinks.updatefolder\n   \
  \     outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceId}/folders/{folderId}\n      name: deletefolder\n      operations:\n      - method: DELETE\n        name: deletefolder\n        description: Intralinks Delete Folder\n        call: intralinks.deletefolder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceId}/documents\n      name: listdocuments\n      operations:\n      - method: GET\n        name: listdocuments\n        description: Intralinks List Documents\n        call: intralinks.listdocuments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceId}/documents\n      name: uploaddocument\n      operations:\n      - method: POST\n        name: uploaddocument\n        description: Intralinks Upload Document\n        call: intralinks.uploaddocument\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /workspaces/{workspaceId}/documents/{documentId}\n      name: getdocument\n      operations:\n      - method: GET\n        name: getdocument\n        description: Intralinks Get Document\n        call: intralinks.getdocument\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceId}/documents/{documentId}\n      name: updatedocument\n      operations:\n      - method: PUT\n        name: updatedocument\n        description: Intralinks Update Document\n        call: intralinks.updatedocument\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceId}/documents/{documentId}\n      name: deletedocument\n      operations:\n      - method: DELETE\n        name: deletedocument\n        description: Intralinks Delete Document\n        call: intralinks.deletedocument\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceId}/documents/{documentId}/download\n\
  \      name: downloaddocument\n      operations:\n      - method: GET\n        name: downloaddocument\n        description: Intralinks Download Document\n        call: intralinks.downloaddocument\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceId}/groups\n      name: listgroups\n      operations:\n      - method: GET\n        name: listgroups\n        description: Intralinks List Groups\n        call: intralinks.listgroups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceId}/groups\n      name: creategroup\n      operations:\n      - method: POST\n        name: creategroup\n        description: Intralinks Create Group\n        call: intralinks.creategroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceId}/groups/{groupId}\n      name: getgroup\n      operations:\n      - method: GET\n        name: getgroup\n\
  \        description: Intralinks Get Group\n        call: intralinks.getgroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceId}/groups/{groupId}\n      name: updategroup\n      operations:\n      - method: PUT\n        name: updategroup\n        description: Intralinks Update Group\n        call: intralinks.updategroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceId}/groups/{groupId}\n      name: deletegroup\n      operations:\n      - method: DELETE\n        name: deletegroup\n        description: Intralinks Delete Group\n        call: intralinks.deletegroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceId}/groups/{groupId}/members\n      name: listgroupmembers\n      operations:\n      - method: GET\n        name: listgroupmembers\n        description: Intralinks List Group Members\n        call:\
  \ intralinks.listgroupmembers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceId}/groups/{groupId}/members\n      name: addgroupmember\n      operations:\n      - method: POST\n        name: addgroupmember\n        description: Intralinks Add Group Member\n        call: intralinks.addgroupmember\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceId}/permissions\n      name: listpermissions\n      operations:\n      - method: GET\n        name: listpermissions\n        description: Intralinks List Permissions\n        call: intralinks.listpermissions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceId}/permissions\n      name: createpermission\n      operations:\n      - method: POST\n        name: createpermission\n        description: Intralinks Create Permission\n        call: intralinks.createpermission\n \
  \       outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceId}/splash\n      name: getsplash\n      operations:\n      - method: GET\n        name: getsplash\n        description: Intralinks Get Splash Screen\n        call: intralinks.getsplash\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceId}/splash\n      name: updatesplash\n      operations:\n      - method: PUT\n        name: updatesplash\n        description: Intralinks Update Splash Screen\n        call: intralinks.updatesplash\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{workspaceId}/customfields\n      name: listcustomfields\n      operations:\n      - method: GET\n        name: listcustomfields\n        description: Intralinks List Custom Fields\n        call: intralinks.listcustomfields\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \  - type: mcp\n    port: 9090\n    namespace: intralinks-mcp\n    transport: http\n    description: MCP adapter for Intralinks API for AI agent use.\n    tools:\n    - name: getoauthtoken\n      description: Intralinks Obtain OAuth Token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: intralinks.getoauthtoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: revokeoauthtoken\n      description: Intralinks Revoke OAuth Token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: intralinks.revokeoauthtoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listworkspaces\n      description: Intralinks List Workspaces\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: intralinks.listworkspaces\n      with:\n        type: tools.type\n        offset: tools.offset\n \
  \       limit: tools.limit\n      inputParameters:\n      - name: type\n        type: string\n        description: type\n      - name: offset\n        type: integer\n        description: offset\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createworkspace\n      description: Intralinks Create Workspace\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: intralinks.createworkspace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getworkspace\n      description: Intralinks Get Workspace\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: intralinks.getworkspace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateworkspace\n      description: Intralinks Update Workspace\n      hints:\n        readOnly: false\n \
  \       destructive: false\n        idempotent: true\n      call: intralinks.updateworkspace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteworkspace\n      description: Intralinks Delete Workspace\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: intralinks.deleteworkspace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfolders\n      description: Intralinks List Folders\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: intralinks.listfolders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createfolder\n      description: Intralinks Create Folder\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: intralinks.createfolder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfolder\n  \
  \    description: Intralinks Get Folder\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: intralinks.getfolder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatefolder\n      description: Intralinks Update Folder\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: intralinks.updatefolder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletefolder\n      description: Intralinks Delete Folder\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: intralinks.deletefolder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdocuments\n      description: Intralinks List Documents\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: intralinks.listdocuments\n      with:\n        folderId:\
  \ tools.folderId\n      inputParameters:\n      - name: folderId\n        type: string\n        description: folderId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: uploaddocument\n      description: Intralinks Upload Document\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: intralinks.uploaddocument\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdocument\n      description: Intralinks Get Document\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: intralinks.getdocument\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatedocument\n      description: Intralinks Update Document\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: intralinks.updatedocument\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: deletedocument\n      description: Intralinks Delete Document\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: intralinks.deletedocument\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: downloaddocument\n      description: Intralinks Download Document\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: intralinks.downloaddocument\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listgroups\n      description: Intralinks List Groups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: intralinks.listgroups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: creategroup\n      description: Intralinks Create Group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: intralinks.creategroup\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getgroup\n      description: Intralinks Get Group\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: intralinks.getgroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updategroup\n      description: Intralinks Update Group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: intralinks.updategroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletegroup\n      description: Intralinks Delete Group\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: intralinks.deletegroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listgroupmembers\n      description: Intralinks List Group Members\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: intralinks.listgroupmembers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: addgroupmember\n      description: Intralinks Add Group Member\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: intralinks.addgroupmember\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpermissions\n      description: Intralinks List Permissions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: intralinks.listpermissions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createpermission\n      description: Intralinks Create Permission\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: intralinks.createpermission\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsplash\n    \
  \  description: Intralinks Get Splash Screen\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: intralinks.getsplash\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatesplash\n      description: Intralinks Update Splash Screen\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: intralinks.updatesplash\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcustomfields\n      description: Intralinks List Custom Fields\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: intralinks.listcustomfields\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    INTRALINKS_TOKEN: INTRALINKS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/intralinks/refs/heads/main/capabilities/intralinks-capability.yaml
tags:
- Intralinks
- API
tools:
- description: Intralinks Obtain OAuth Token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getoauthtoken
- description: Intralinks Revoke OAuth Token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: revokeoauthtoken
- description: Intralinks List Workspaces
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listworkspaces
- description: Intralinks Create Workspace
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createworkspace
- description: Intralinks Get Workspace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getworkspace
- description: Intralinks Update Workspace
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateworkspace
- description: Intralinks Delete Workspace
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteworkspace
- description: Intralinks List Folders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfolders
- description: Intralinks Create Folder
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createfolder
- description: Intralinks Get Folder
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfolder
- description: Intralinks Update Folder
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatefolder
- description: Intralinks Delete Folder
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletefolder
- description: Intralinks List Documents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdocuments
- description: Intralinks Upload Document
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: uploaddocument
- description: Intralinks Get Document
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdocument
- description: Intralinks Update Document
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatedocument
- description: Intralinks Delete Document
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedocument
- description: Intralinks Download Document
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: downloaddocument
- description: Intralinks List Groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgroups
- description: Intralinks Create Group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creategroup
- description: Intralinks Get Group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroup
- description: Intralinks Update Group
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updategroup
- description: Intralinks Delete Group
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletegroup
- description: Intralinks List Group Members
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgroupmembers
- description: Intralinks Add Group Member
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addgroupmember
- description: Intralinks List Permissions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpermissions
- description: Intralinks Create Permission
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpermission
- description: Intralinks Get Splash Screen
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsplash
- description: Intralinks Update Splash Screen
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatesplash
- description: Intralinks List Custom Fields
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcustomfields
---
