---
categories: []
consumed_apis: []
description: API for managing users, groups, permissions, projects, and access tokens across the JFrog Platform. JFrog Access handles identity management, role-based access control, federated identity, and scoped token creation for authentication and authorization across all JFrog services.
layout: capability
name: JFrog Access REST API
operations:
- description: JFrog System Ping
  method: GET
  name: systemping
  path: /api/v1/system/ping
- description: JFrog Get System Version
  method: GET
  name: getsystemversion
  path: /api/v1/system/version
- description: JFrog List Access Tokens
  method: GET
  name: listtokens
  path: /api/v2/tokens
- description: JFrog Create Access Token
  method: POST
  name: createtoken
  path: /api/v2/tokens
- description: JFrog Get Token Details
  method: GET
  name: gettoken
  path: /api/v2/tokens/{tokenId}
- description: JFrog Revoke Access Token
  method: DELETE
  name: revoketoken
  path: /api/v2/tokens/{tokenId}
- description: JFrog List Users
  method: GET
  name: listusers
  path: /api/v2/users
- description: JFrog Create User
  method: POST
  name: createuser
  path: /api/v2/users
- description: JFrog Get User
  method: GET
  name: getuser
  path: /api/v2/users/{username}
- description: JFrog Update User
  method: PATCH
  name: updateuser
  path: /api/v2/users/{username}
- description: JFrog Delete User
  method: DELETE
  name: deleteuser
  path: /api/v2/users/{username}
- description: JFrog List Groups
  method: GET
  name: listgroups
  path: /api/v2/groups
- description: JFrog Create Group
  method: POST
  name: creategroup
  path: /api/v2/groups
- description: JFrog Get Group
  method: GET
  name: getgroup
  path: /api/v2/groups/{groupName}
- description: JFrog Update Group
  method: PATCH
  name: updategroup
  path: /api/v2/groups/{groupName}
- description: JFrog Delete Group
  method: DELETE
  name: deletegroup
  path: /api/v2/groups/{groupName}
- description: JFrog List Permissions
  method: GET
  name: listpermissions
  path: /api/v2/permissions
- description: JFrog Create Permission
  method: POST
  name: createpermission
  path: /api/v2/permissions
- description: JFrog Get Permission
  method: GET
  name: getpermission
  path: /api/v2/permissions/{permissionName}
- description: JFrog Update Permission
  method: PUT
  name: updatepermission
  path: /api/v2/permissions/{permissionName}
- description: JFrog Delete Permission
  method: DELETE
  name: deletepermission
  path: /api/v2/permissions/{permissionName}
- description: JFrog List Projects
  method: GET
  name: listprojects
  path: /api/v1/projects
- description: JFrog Create Project
  method: POST
  name: createproject
  path: /api/v1/projects
- description: JFrog Get Project
  method: GET
  name: getproject
  path: /api/v1/projects/{projectKey}
- description: JFrog Update Project
  method: PUT
  name: updateproject
  path: /api/v1/projects/{projectKey}
- description: JFrog Delete Project
  method: DELETE
  name: deleteproject
  path: /api/v1/projects/{projectKey}
- description: JFrog Add User to Project
  method: PUT
  name: addusertoproject
  path: /api/v1/projects/{projectKey}/users/{username}
- description: JFrog Remove User from Project
  method: DELETE
  name: removeuserfromproject
  path: /api/v1/projects/{projectKey}/users/{username}
- description: JFrog Add Group to Project
  method: PUT
  name: addgrouptoproject
  path: /api/v1/projects/{projectKey}/groups/{groupName}
- description: JFrog Remove Group from Project
  method: DELETE
  name: removegroupfromproject
  path: /api/v1/projects/{projectKey}/groups/{groupName}
personas: []
provider_name: JFrog
provider_slug: jfrog
search_terms:
- jfrog list access tokens
- jfrog update user
- jfrog list projects
- devops
- getproject
- jfrog update project
- removegroupfromproject
- jfrog get project
- jfrog system ping
- jfrog create access token
- creategroup
- createpermission
- systemping
- jfrog get group
- api
- jfrog list users
- jfrog remove user from project
- ci/cd
- jfrog create permission
- createtoken
- container registry
- software supply chain
- addusertoproject
- jfrog get system version
- getuser
- getgroup
- updateproject
- jfrog create user
- deleteuser
- listgroups
- deletepermission
- jfrog delete group
- removeuserfromproject
- getsystemversion
- listtokens
- jfrog remove group from project
- jfrog update permission
- gettoken
- getpermission
- updatepermission
- updategroup
- jfrog get permission
- mlops
- jfrog create project
- revoketoken
- updateuser
- jfrog delete project
- jfrog add user to project
- deleteproject
- jfrog
- jfrog get token details
- jfrog list groups
- createuser
- listpermissions
- jfrog get user
- listusers
- jfrog list permissions
- jfrog update group
- jfrog delete permission
- listprojects
- jfrog create group
- artifactory
- addgrouptoproject
- security
- jfrog add group to project
- jfrog delete user
- deletegroup
- package management
- jfrog revoke access token
- createproject
slug: jfrog-capability
source_filename: jfrog-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: JFrog Access REST API\n  description: API for managing users, groups, permissions, projects, and access tokens across the JFrog Platform. JFrog Access\n    handles identity management, role-based access control, federated identity, and scoped token creation for authentication\n    and authorization across all JFrog services.\n  tags:\n  - Jfrog\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: jfrog\n    baseUri: https://myserver.jfrog.io/access\n    description: JFrog Access REST API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{JFROG_TOKEN}}'\n    resources:\n    - name: api-v1-system-ping\n      path: /api/v1/system/ping\n      operations:\n      - name: systemping\n        method: GET\n        description: JFrog System Ping\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: api-v1-system-version\n      path: /api/v1/system/version\n      operations:\n      - name: getsystemversion\n        method: GET\n        description: JFrog Get System Version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-tokens\n      path: /api/v2/tokens\n      operations:\n      - name: listtokens\n        method: GET\n        description: JFrog List Access Tokens\n        inputParameters:\n        - name: subject\n          in: query\n          type: string\n          description: Filter tokens by subject\n        - name: token_id\n          in: query\n          type: string\n          description: Filter by specific token ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtoken\n        method: POST\n        description: JFrog Create Access Token\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-tokens-tokenid\n      path: /api/v2/tokens/{tokenId}\n      operations:\n      - name: gettoken\n        method: GET\n        description: JFrog Get Token Details\n        inputParameters:\n        - name: tokenId\n          in: path\n          type: string\n          required: true\n          description: Token ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: revoketoken\n        method: DELETE\n        description: JFrog Revoke Access Token\n        inputParameters:\n        - name: tokenId\n          in: path\n          type: string\n          required: true\n          description: Token ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-users\n      path: /api/v2/users\n\
  \      operations:\n      - name: listusers\n        method: GET\n        description: JFrog List Users\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Filter by user status\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          description: Offset for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createuser\n        method: POST\n        description: JFrog Create User\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-users-username\n      path: /api/v2/users/{username}\n      operations:\n      - name: getuser\n        method: GET\n        description: JFrog Get User\n   \
  \     inputParameters:\n        - name: username\n          in: path\n          type: string\n          required: true\n          description: Username\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateuser\n        method: PATCH\n        description: JFrog Update User\n        inputParameters:\n        - name: username\n          in: path\n          type: string\n          required: true\n          description: Username\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteuser\n        method: DELETE\n        description: JFrog Delete User\n        inputParameters:\n        - name: username\n          in: path\n          type: string\n          required: true\n          description: Username\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: api-v2-groups\n      path: /api/v2/groups\n      operations:\n      - name: listgroups\n        method: GET\n        description: JFrog List Groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: creategroup\n        method: POST\n        description: JFrog Create Group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-groups-groupname\n      path: /api/v2/groups/{groupName}\n      operations:\n      - name: getgroup\n        method: GET\n        description: JFrog Get Group\n        inputParameters:\n        - name: groupName\n          in: path\n          type: string\n          required: true\n          description: Group name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ updategroup\n        method: PATCH\n        description: JFrog Update Group\n        inputParameters:\n        - name: groupName\n          in: path\n          type: string\n          required: true\n          description: Group name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletegroup\n        method: DELETE\n        description: JFrog Delete Group\n        inputParameters:\n        - name: groupName\n          in: path\n          type: string\n          required: true\n          description: Group name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-permissions\n      path: /api/v2/permissions\n      operations:\n      - name: listpermissions\n        method: GET\n        description: JFrog List Permissions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: createpermission\n        method: POST\n        description: JFrog Create Permission\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-permissions-permissionname\n      path: /api/v2/permissions/{permissionName}\n      operations:\n      - name: getpermission\n        method: GET\n        description: JFrog Get Permission\n        inputParameters:\n        - name: permissionName\n          in: path\n          type: string\n          required: true\n          description: Permission name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatepermission\n        method: PUT\n        description: JFrog Update Permission\n        inputParameters:\n        - name: permissionName\n          in: path\n          type: string\n          required: true\n\
  \          description: Permission name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletepermission\n        method: DELETE\n        description: JFrog Delete Permission\n        inputParameters:\n        - name: permissionName\n          in: path\n          type: string\n          required: true\n          description: Permission name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-projects\n      path: /api/v1/projects\n      operations:\n      - name: listprojects\n        method: GET\n        description: JFrog List Projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createproject\n        method: POST\n        description: JFrog Create Project\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: api-v1-projects-projectkey\n      path: /api/v1/projects/{projectKey}\n      operations:\n      - name: getproject\n        method: GET\n        description: JFrog Get Project\n        inputParameters:\n        - name: projectKey\n          in: path\n          type: string\n          required: true\n          description: Project key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateproject\n        method: PUT\n        description: JFrog Update Project\n        inputParameters:\n        - name: projectKey\n          in: path\n          type: string\n          required: true\n          description: Project key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteproject\n        method: DELETE\n        description:\
  \ JFrog Delete Project\n        inputParameters:\n        - name: projectKey\n          in: path\n          type: string\n          required: true\n          description: Project key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-projects-projectkey-users-username\n      path: /api/v1/projects/{projectKey}/users/{username}\n      operations:\n      - name: addusertoproject\n        method: PUT\n        description: JFrog Add User to Project\n        inputParameters:\n        - name: projectKey\n          in: path\n          type: string\n          required: true\n          description: Project key\n        - name: username\n          in: path\n          type: string\n          required: true\n          description: Username to add\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removeuserfromproject\n\
  \        method: DELETE\n        description: JFrog Remove User from Project\n        inputParameters:\n        - name: projectKey\n          in: path\n          type: string\n          required: true\n          description: Project key\n        - name: username\n          in: path\n          type: string\n          required: true\n          description: Username to remove\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-projects-projectkey-groups-groupname\n      path: /api/v1/projects/{projectKey}/groups/{groupName}\n      operations:\n      - name: addgrouptoproject\n        method: PUT\n        description: JFrog Add Group to Project\n        inputParameters:\n        - name: projectKey\n          in: path\n          type: string\n          required: true\n          description: Project key\n        - name: groupName\n          in: path\n          type: string\n          required: true\n\
  \          description: Group name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removegroupfromproject\n        method: DELETE\n        description: JFrog Remove Group from Project\n        inputParameters:\n        - name: projectKey\n          in: path\n          type: string\n          required: true\n          description: Project key\n        - name: groupName\n          in: path\n          type: string\n          required: true\n          description: Group name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: jfrog-rest\n    description: REST adapter for JFrog Access REST API.\n    resources:\n    - path: /api/v1/system/ping\n      name: systemping\n      operations:\n      - method: GET\n        name: systemping\n        description: JFrog System\
  \ Ping\n        call: jfrog.systemping\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/system/version\n      name: getsystemversion\n      operations:\n      - method: GET\n        name: getsystemversion\n        description: JFrog Get System Version\n        call: jfrog.getsystemversion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/tokens\n      name: listtokens\n      operations:\n      - method: GET\n        name: listtokens\n        description: JFrog List Access Tokens\n        call: jfrog.listtokens\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/tokens\n      name: createtoken\n      operations:\n      - method: POST\n        name: createtoken\n        description: JFrog Create Access Token\n        call: jfrog.createtoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/tokens/{tokenId}\n   \
  \   name: gettoken\n      operations:\n      - method: GET\n        name: gettoken\n        description: JFrog Get Token Details\n        call: jfrog.gettoken\n        with:\n          tokenId: rest.tokenId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/tokens/{tokenId}\n      name: revoketoken\n      operations:\n      - method: DELETE\n        name: revoketoken\n        description: JFrog Revoke Access Token\n        call: jfrog.revoketoken\n        with:\n          tokenId: rest.tokenId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/users\n      name: listusers\n      operations:\n      - method: GET\n        name: listusers\n        description: JFrog List Users\n        call: jfrog.listusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/users\n      name: createuser\n      operations:\n      - method: POST\n        name: createuser\n    \
  \    description: JFrog Create User\n        call: jfrog.createuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/users/{username}\n      name: getuser\n      operations:\n      - method: GET\n        name: getuser\n        description: JFrog Get User\n        call: jfrog.getuser\n        with:\n          username: rest.username\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/users/{username}\n      name: updateuser\n      operations:\n      - method: PATCH\n        name: updateuser\n        description: JFrog Update User\n        call: jfrog.updateuser\n        with:\n          username: rest.username\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/users/{username}\n      name: deleteuser\n      operations:\n      - method: DELETE\n        name: deleteuser\n        description: JFrog Delete User\n        call: jfrog.deleteuser\n        with:\n\
  \          username: rest.username\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/groups\n      name: listgroups\n      operations:\n      - method: GET\n        name: listgroups\n        description: JFrog List Groups\n        call: jfrog.listgroups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/groups\n      name: creategroup\n      operations:\n      - method: POST\n        name: creategroup\n        description: JFrog Create Group\n        call: jfrog.creategroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/groups/{groupName}\n      name: getgroup\n      operations:\n      - method: GET\n        name: getgroup\n        description: JFrog Get Group\n        call: jfrog.getgroup\n        with:\n          groupName: rest.groupName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/groups/{groupName}\n\
  \      name: updategroup\n      operations:\n      - method: PATCH\n        name: updategroup\n        description: JFrog Update Group\n        call: jfrog.updategroup\n        with:\n          groupName: rest.groupName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/groups/{groupName}\n      name: deletegroup\n      operations:\n      - method: DELETE\n        name: deletegroup\n        description: JFrog Delete Group\n        call: jfrog.deletegroup\n        with:\n          groupName: rest.groupName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/permissions\n      name: listpermissions\n      operations:\n      - method: GET\n        name: listpermissions\n        description: JFrog List Permissions\n        call: jfrog.listpermissions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/permissions\n      name: createpermission\n      operations:\n\
  \      - method: POST\n        name: createpermission\n        description: JFrog Create Permission\n        call: jfrog.createpermission\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/permissions/{permissionName}\n      name: getpermission\n      operations:\n      - method: GET\n        name: getpermission\n        description: JFrog Get Permission\n        call: jfrog.getpermission\n        with:\n          permissionName: rest.permissionName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/permissions/{permissionName}\n      name: updatepermission\n      operations:\n      - method: PUT\n        name: updatepermission\n        description: JFrog Update Permission\n        call: jfrog.updatepermission\n        with:\n          permissionName: rest.permissionName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/permissions/{permissionName}\n    \
  \  name: deletepermission\n      operations:\n      - method: DELETE\n        name: deletepermission\n        description: JFrog Delete Permission\n        call: jfrog.deletepermission\n        with:\n          permissionName: rest.permissionName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/projects\n      name: listprojects\n      operations:\n      - method: GET\n        name: listprojects\n        description: JFrog List Projects\n        call: jfrog.listprojects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/projects\n      name: createproject\n      operations:\n      - method: POST\n        name: createproject\n        description: JFrog Create Project\n        call: jfrog.createproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/projects/{projectKey}\n      name: getproject\n      operations:\n      - method: GET\n        name: getproject\n\
  \        description: JFrog Get Project\n        call: jfrog.getproject\n        with:\n          projectKey: rest.projectKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/projects/{projectKey}\n      name: updateproject\n      operations:\n      - method: PUT\n        name: updateproject\n        description: JFrog Update Project\n        call: jfrog.updateproject\n        with:\n          projectKey: rest.projectKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/projects/{projectKey}\n      name: deleteproject\n      operations:\n      - method: DELETE\n        name: deleteproject\n        description: JFrog Delete Project\n        call: jfrog.deleteproject\n        with:\n          projectKey: rest.projectKey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/projects/{projectKey}/users/{username}\n      name: addusertoproject\n      operations:\n\
  \      - method: PUT\n        name: addusertoproject\n        description: JFrog Add User to Project\n        call: jfrog.addusertoproject\n        with:\n          projectKey: rest.projectKey\n          username: rest.username\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/projects/{projectKey}/users/{username}\n      name: removeuserfromproject\n      operations:\n      - method: DELETE\n        name: removeuserfromproject\n        description: JFrog Remove User from Project\n        call: jfrog.removeuserfromproject\n        with:\n          projectKey: rest.projectKey\n          username: rest.username\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/projects/{projectKey}/groups/{groupName}\n      name: addgrouptoproject\n      operations:\n      - method: PUT\n        name: addgrouptoproject\n        description: JFrog Add Group to Project\n        call: jfrog.addgrouptoproject\n        with:\n\
  \          projectKey: rest.projectKey\n          groupName: rest.groupName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/projects/{projectKey}/groups/{groupName}\n      name: removegroupfromproject\n      operations:\n      - method: DELETE\n        name: removegroupfromproject\n        description: JFrog Remove Group from Project\n        call: jfrog.removegroupfromproject\n        with:\n          projectKey: rest.projectKey\n          groupName: rest.groupName\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: jfrog-mcp\n    transport: http\n    description: MCP adapter for JFrog Access REST API for AI agent use.\n    tools:\n    - name: systemping\n      description: JFrog System Ping\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jfrog.systemping\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: getsystemversion\n      description: JFrog Get System Version\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jfrog.getsystemversion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtokens\n      description: JFrog List Access Tokens\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jfrog.listtokens\n      with:\n        subject: tools.subject\n        token_id: tools.token_id\n      inputParameters:\n      - name: subject\n        type: string\n        description: Filter tokens by subject\n      - name: token_id\n        type: string\n        description: Filter by specific token ID\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtoken\n      description: JFrog Create Access Token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call:\
  \ jfrog.createtoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettoken\n      description: JFrog Get Token Details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jfrog.gettoken\n      with:\n        tokenId: tools.tokenId\n      inputParameters:\n      - name: tokenId\n        type: string\n        description: Token ID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: revoketoken\n      description: JFrog Revoke Access Token\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: jfrog.revoketoken\n      with:\n        tokenId: tools.tokenId\n      inputParameters:\n      - name: tokenId\n        type: string\n        description: Token ID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listusers\n      description: JFrog List Users\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jfrog.listusers\n      with:\n        status: tools.status\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: status\n        type: string\n        description: Filter by user status\n      - name: limit\n        type: integer\n        description: Maximum number of results\n      - name: offset\n        type: integer\n        description: Offset for pagination\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createuser\n      description: JFrog Create User\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jfrog.createuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getuser\n      description: JFrog Get User\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jfrog.getuser\n\
  \      with:\n        username: tools.username\n      inputParameters:\n      - name: username\n        type: string\n        description: Username\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateuser\n      description: JFrog Update User\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jfrog.updateuser\n      with:\n        username: tools.username\n      inputParameters:\n      - name: username\n        type: string\n        description: Username\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteuser\n      description: JFrog Delete User\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: jfrog.deleteuser\n      with:\n        username: tools.username\n      inputParameters:\n      - name: username\n        type: string\n        description: Username\n\
  \        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listgroups\n      description: JFrog List Groups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jfrog.listgroups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: creategroup\n      description: JFrog Create Group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jfrog.creategroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getgroup\n      description: JFrog Get Group\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jfrog.getgroup\n      with:\n        groupName: tools.groupName\n      inputParameters:\n      - name: groupName\n        type: string\n        description: Group name\n        required: true\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: updategroup\n      description: JFrog Update Group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jfrog.updategroup\n      with:\n        groupName: tools.groupName\n      inputParameters:\n      - name: groupName\n        type: string\n        description: Group name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletegroup\n      description: JFrog Delete Group\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: jfrog.deletegroup\n      with:\n        groupName: tools.groupName\n      inputParameters:\n      - name: groupName\n        type: string\n        description: Group name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpermissions\n      description: JFrog List Permissions\n      hints:\n        readOnly: true\n \
  \       destructive: false\n        idempotent: true\n      call: jfrog.listpermissions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createpermission\n      description: JFrog Create Permission\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jfrog.createpermission\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpermission\n      description: JFrog Get Permission\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jfrog.getpermission\n      with:\n        permissionName: tools.permissionName\n      inputParameters:\n      - name: permissionName\n        type: string\n        description: Permission name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatepermission\n      description: JFrog Update Permission\n      hints:\n        readOnly: false\n\
  \        destructive: false\n        idempotent: true\n      call: jfrog.updatepermission\n      with:\n        permissionName: tools.permissionName\n      inputParameters:\n      - name: permissionName\n        type: string\n        description: Permission name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletepermission\n      description: JFrog Delete Permission\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: jfrog.deletepermission\n      with:\n        permissionName: tools.permissionName\n      inputParameters:\n      - name: permissionName\n        type: string\n        description: Permission name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listprojects\n      description: JFrog List Projects\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jfrog.listprojects\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createproject\n      description: JFrog Create Project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: jfrog.createproject\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproject\n      description: JFrog Get Project\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jfrog.getproject\n      with:\n        projectKey: tools.projectKey\n      inputParameters:\n      - name: projectKey\n        type: string\n        description: Project key\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateproject\n      description: JFrog Update Project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: jfrog.updateproject\n      with:\n        projectKey: tools.projectKey\n\
  \      inputParameters:\n      - name: projectKey\n        type: string\n        description: Project key\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteproject\n      description: JFrog Delete Project\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: jfrog.deleteproject\n      with:\n        projectKey: tools.projectKey\n      inputParameters:\n      - name: projectKey\n        type: string\n        description: Project key\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: addusertoproject\n      description: JFrog Add User to Project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: jfrog.addusertoproject\n      with:\n        projectKey: tools.projectKey\n        username: tools.username\n      inputParameters:\n      - name: projectKey\n        type: string\n\
  \        description: Project key\n        required: true\n      - name: username\n        type: string\n        description: Username to add\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: removeuserfromproject\n      description: JFrog Remove User from Project\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: jfrog.removeuserfromproject\n      with:\n        projectKey: tools.projectKey\n        username: tools.username\n      inputParameters:\n      - name: projectKey\n        type: string\n        description: Project key\n        required: true\n      - name: username\n        type: string\n        description: Username to remove\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: addgrouptoproject\n      description: JFrog Add Group to Project\n      hint\n\n# --- truncated at 32 KB (33 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/jfrog/refs/heads/main/capabilities/jfrog-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/jfrog/refs/heads/main/capabilities/jfrog-capability.yaml
tags:
- Jfrog
- API
tools:
- description: JFrog System Ping
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: systemping
- description: JFrog Get System Version
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsystemversion
- description: JFrog List Access Tokens
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtokens
- description: JFrog Create Access Token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtoken
- description: JFrog Get Token Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettoken
- description: JFrog Revoke Access Token
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: revoketoken
- description: JFrog List Users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusers
- description: JFrog Create User
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createuser
- description: JFrog Get User
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: JFrog Update User
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateuser
- description: JFrog Delete User
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteuser
- description: JFrog List Groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgroups
- description: JFrog Create Group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creategroup
- description: JFrog Get Group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroup
- description: JFrog Update Group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updategroup
- description: JFrog Delete Group
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletegroup
- description: JFrog List Permissions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpermissions
- description: JFrog Create Permission
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpermission
- description: JFrog Get Permission
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpermission
- description: JFrog Update Permission
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatepermission
- description: JFrog Delete Permission
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletepermission
- description: JFrog List Projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojects
- description: JFrog Create Project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createproject
- description: JFrog Get Project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproject
- description: JFrog Update Project
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateproject
- description: JFrog Delete Project
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteproject
- description: JFrog Add User to Project
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: addusertoproject
- description: JFrog Remove User from Project
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removeuserfromproject
- description: JFrog Add Group to Project
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: addgrouptoproject
- description: JFrog Remove Group from Project
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removegroupfromproject
---
