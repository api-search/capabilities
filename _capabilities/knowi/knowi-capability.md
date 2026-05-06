---
categories: []
consumed_apis: []
description: The Knowi Management API enables programmatic administration of a Knowi workspace including users, groups, and dashboards. It uses OAuth 2.0 bearer tokens for authentication and supports automation of provisioning, permission management, and embedded analytics workflows.
layout: capability
name: Knowi Management API
operations:
- description: Obtain access token
  method: POST
  name: login
  path: /login
- description: Revoke access token
  method: DELETE
  name: logout
  path: /logout
- description: List users
  method: GET
  name: listusers
  path: /users
- description: Create user
  method: POST
  name: createuser
  path: /users
- description: Search user
  method: GET
  name: searchuser
  path: /users/search
- description: Get user
  method: GET
  name: getuser
  path: /users/{userId}
- description: Update user
  method: PUT
  name: updateuser
  path: /users/{userId}
- description: Delete user
  method: DELETE
  name: deleteuser
  path: /users/{userId}
- description: Move user assets
  method: PUT
  name: moveuserassets
  path: /users/{userId}/moveAssets
- description: List shareable entities
  method: GET
  name: listshareableentities
  path: /users/shareableEntities
- description: List groups
  method: GET
  name: listgroups
  path: /groups
- description: Create group
  method: POST
  name: creategroup
  path: /groups
- description: Get group
  method: GET
  name: getgroup
  path: /groups/{groupId}
- description: Update group
  method: PUT
  name: updategroup
  path: /groups/{groupId}
- description: Delete group
  method: DELETE
  name: deletegroup
  path: /groups/{groupId}
- description: List user groups
  method: GET
  name: listusergroups
  path: /users/{userId}/groups
- description: Create group for user
  method: POST
  name: createusergroup
  path: /users/{userId}/groups
- description: Remove group from user
  method: DELETE
  name: removeusergroup
  path: /users/{userId}/groups/{groupId}
- description: List dashboards
  method: GET
  name: listdashboards
  path: /dashboards
- description: Get dashboard
  method: GET
  name: getdashboard
  path: /dashboards/{objectId}
- description: Get dashboard share info
  method: GET
  name: getdashboardshare
  path: /dashboards/{objectId}/share
- description: Generate share URL
  method: POST
  name: generateshareurl
  path: /dashboards/{objectId}/share/url
- description: Generate secure share URL
  method: POST
  name: generatesecureshareurl
  path: /dashboards/{objectId}/share/url/secure
- description: Generate secure share hash
  method: POST
  name: generatesecuresharehash
  path: /dashboards/{objectId}/share/url/secure/hash
personas: []
provider_name: Knowi
provider_slug: knowi
search_terms:
- knowi
- creategroup
- createuser
- generate secure share hash
- api analytics
- deletegroup
- getdashboardshare
- embedded analytics
- delete group
- generate share url
- getdashboard
- search user
- create user
- get group
- get dashboard share info
- create group
- listusergroups
- createusergroup
- listshareableentities
- generatesecureshareurl
- update group
- remove group from user
- data visualization
- delete user
- revoke access token
- listgroups
- ai analytics
- login
- list shareable entities
- list user groups
- api
- nosql analytics
- move user assets
- obtain access token
- get dashboard
- update user
- create group for user
- get user
- generateshareurl
- business intelligence
- getuser
- removeusergroup
- list users
- list dashboards
- logout
- list groups
- listusers
- moveuserassets
- getgroup
- generate secure share url
- updateuser
- listdashboards
- searchuser
- updategroup
- generatesecuresharehash
- deleteuser
slug: knowi-capability
source_filename: knowi-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Knowi Management API\n  description: The Knowi Management API enables programmatic administration of a Knowi workspace including users, groups,\n    and dashboards. It uses OAuth 2.0 bearer tokens for authentication and supports automation of provisioning, permission\n    management, and embedded analytics workflows.\n  tags:\n  - Knowi\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: knowi\n    baseUri: https://knowi.com/api/1.0\n    description: Knowi Management API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{KNOWI_TOKEN}}'\n    resources:\n    - name: login\n      path: /login\n      operations:\n      - name: login\n        method: POST\n        description: Obtain access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: logout\n      path: /logout\n\
  \      operations:\n      - name: logout\n        method: DELETE\n        description: Revoke access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      operations:\n      - name: listusers\n        method: GET\n        description: List users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createuser\n        method: POST\n        description: Create user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-search\n      path: /users/search\n      operations:\n      - name: searchuser\n        method: GET\n        description: Search user\n        inputParameters:\n        - name: username\n          in: query\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-userid\n      path: /users/{userId}\n      operations:\n      - name: getuser\n        method: GET\n        description: Get user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateuser\n        method: PUT\n        description: Update user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteuser\n        method: DELETE\n        description: Delete user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-userid-moveassets\n      path: /users/{userId}/moveAssets\n      operations:\n      - name: moveuserassets\n        method: PUT\n        description: Move user assets\n        inputParameters:\n\
  \        - name: userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-shareableentities\n      path: /users/shareableEntities\n      operations:\n      - name: listshareableentities\n        method: GET\n        description: List shareable entities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /groups\n      operations:\n      - name: listgroups\n        method: GET\n        description: List groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: creategroup\n        method: POST\n        description: Create group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: groups-groupid\n      path: /groups/{groupId}\n      operations:\n      - name: getgroup\n        method: GET\n        description: Get group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updategroup\n        method: PUT\n        description: Update group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletegroup\n        method: DELETE\n        description: Delete group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-userid-groups\n      path: /users/{userId}/groups\n      operations:\n      - name: listusergroups\n        method: GET\n        description: List user groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: createusergroup\n        method: POST\n        description: Create group for user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-userid-groups-groupid\n      path: /users/{userId}/groups/{groupId}\n      operations:\n      - name: removeusergroup\n        method: DELETE\n        description: Remove group from user\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        - name: groupId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dashboards\n      path: /dashboards\n      operations:\n      - name: listdashboards\n        method: GET\n        description: List dashboards\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: dashboards-objectid\n      path: /dashboards/{objectId}\n      operations:\n      - name: getdashboard\n        method: GET\n        description: Get dashboard\n        inputParameters:\n        - name: objectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dashboards-objectid-share\n      path: /dashboards/{objectId}/share\n      operations:\n      - name: getdashboardshare\n        method: GET\n        description: Get dashboard share info\n        inputParameters:\n        - name: objectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dashboards-objectid-share-url\n      path: /dashboards/{objectId}/share/url\n\
  \      operations:\n      - name: generateshareurl\n        method: POST\n        description: Generate share URL\n        inputParameters:\n        - name: objectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dashboards-objectid-share-url-secure\n      path: /dashboards/{objectId}/share/url/secure\n      operations:\n      - name: generatesecureshareurl\n        method: POST\n        description: Generate secure share URL\n        inputParameters:\n        - name: objectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dashboards-objectid-share-url-secure-hash\n      path: /dashboards/{objectId}/share/url/secure/hash\n      operations:\n      - name: generatesecuresharehash\n\
  \        method: POST\n        description: Generate secure share hash\n        inputParameters:\n        - name: objectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: knowi-rest\n    description: REST adapter for Knowi Management API.\n    resources:\n    - path: /login\n      name: login\n      operations:\n      - method: POST\n        name: login\n        description: Obtain access token\n        call: knowi.login\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /logout\n      name: logout\n      operations:\n      - method: DELETE\n        name: logout\n        description: Revoke access token\n        call: knowi.logout\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users\n      name: listusers\n\
  \      operations:\n      - method: GET\n        name: listusers\n        description: List users\n        call: knowi.listusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users\n      name: createuser\n      operations:\n      - method: POST\n        name: createuser\n        description: Create user\n        call: knowi.createuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/search\n      name: searchuser\n      operations:\n      - method: GET\n        name: searchuser\n        description: Search user\n        call: knowi.searchuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}\n      name: getuser\n      operations:\n      - method: GET\n        name: getuser\n        description: Get user\n        call: knowi.getuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}\n      name:\
  \ updateuser\n      operations:\n      - method: PUT\n        name: updateuser\n        description: Update user\n        call: knowi.updateuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}\n      name: deleteuser\n      operations:\n      - method: DELETE\n        name: deleteuser\n        description: Delete user\n        call: knowi.deleteuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}/moveAssets\n      name: moveuserassets\n      operations:\n      - method: PUT\n        name: moveuserassets\n        description: Move user assets\n        call: knowi.moveuserassets\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/shareableEntities\n      name: listshareableentities\n      operations:\n      - method: GET\n        name: listshareableentities\n        description: List shareable\
  \ entities\n        call: knowi.listshareableentities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /groups\n      name: listgroups\n      operations:\n      - method: GET\n        name: listgroups\n        description: List groups\n        call: knowi.listgroups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /groups\n      name: creategroup\n      operations:\n      - method: POST\n        name: creategroup\n        description: Create group\n        call: knowi.creategroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /groups/{groupId}\n      name: getgroup\n      operations:\n      - method: GET\n        name: getgroup\n        description: Get group\n        call: knowi.getgroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /groups/{groupId}\n      name: updategroup\n      operations:\n      - method: PUT\n        name: updategroup\n\
  \        description: Update group\n        call: knowi.updategroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /groups/{groupId}\n      name: deletegroup\n      operations:\n      - method: DELETE\n        name: deletegroup\n        description: Delete group\n        call: knowi.deletegroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}/groups\n      name: listusergroups\n      operations:\n      - method: GET\n        name: listusergroups\n        description: List user groups\n        call: knowi.listusergroups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}/groups\n      name: createusergroup\n      operations:\n      - method: POST\n        name: createusergroup\n        description: Create group for user\n        call: knowi.createusergroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}/groups/{groupId}\n\
  \      name: removeusergroup\n      operations:\n      - method: DELETE\n        name: removeusergroup\n        description: Remove group from user\n        call: knowi.removeusergroup\n        with:\n          userId: rest.userId\n          groupId: rest.groupId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dashboards\n      name: listdashboards\n      operations:\n      - method: GET\n        name: listdashboards\n        description: List dashboards\n        call: knowi.listdashboards\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dashboards/{objectId}\n      name: getdashboard\n      operations:\n      - method: GET\n        name: getdashboard\n        description: Get dashboard\n        call: knowi.getdashboard\n        with:\n          objectId: rest.objectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dashboards/{objectId}/share\n      name: getdashboardshare\n\
  \      operations:\n      - method: GET\n        name: getdashboardshare\n        description: Get dashboard share info\n        call: knowi.getdashboardshare\n        with:\n          objectId: rest.objectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dashboards/{objectId}/share/url\n      name: generateshareurl\n      operations:\n      - method: POST\n        name: generateshareurl\n        description: Generate share URL\n        call: knowi.generateshareurl\n        with:\n          objectId: rest.objectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dashboards/{objectId}/share/url/secure\n      name: generatesecureshareurl\n      operations:\n      - method: POST\n        name: generatesecureshareurl\n        description: Generate secure share URL\n        call: knowi.generatesecureshareurl\n        with:\n          objectId: rest.objectId\n        outputParameters:\n        - type: object\n  \
  \        mapping: $.\n    - path: /dashboards/{objectId}/share/url/secure/hash\n      name: generatesecuresharehash\n      operations:\n      - method: POST\n        name: generatesecuresharehash\n        description: Generate secure share hash\n        call: knowi.generatesecuresharehash\n        with:\n          objectId: rest.objectId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: knowi-mcp\n    transport: http\n    description: MCP adapter for Knowi Management API for AI agent use.\n    tools:\n    - name: login\n      description: Obtain access token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: knowi.login\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: logout\n      description: Revoke access token\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: knowi.logout\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listusers\n      description: List users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: knowi.listusers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createuser\n      description: Create user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: knowi.createuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchuser\n      description: Search user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: knowi.searchuser\n      with:\n        username: tools.username\n      inputParameters:\n      - name: username\n        type: string\n        description: username\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getuser\n\
  \      description: Get user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: knowi.getuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateuser\n      description: Update user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: knowi.updateuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteuser\n      description: Delete user\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: knowi.deleteuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: moveuserassets\n      description: Move user assets\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: knowi.moveuserassets\n      with:\n        userId: tools.userId\n      inputParameters:\n      - name: userId\n        type:\
  \ string\n        description: userId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listshareableentities\n      description: List shareable entities\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: knowi.listshareableentities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listgroups\n      description: List groups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: knowi.listgroups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: creategroup\n      description: Create group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: knowi.creategroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getgroup\n      description: Get group\n      hints:\n        readOnly: true\n \
  \       destructive: false\n        idempotent: true\n      call: knowi.getgroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updategroup\n      description: Update group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: knowi.updategroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletegroup\n      description: Delete group\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: knowi.deletegroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listusergroups\n      description: List user groups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: knowi.listusergroups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createusergroup\n      description: Create group for user\n      hints:\n      \
  \  readOnly: false\n        destructive: false\n        idempotent: false\n      call: knowi.createusergroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: removeusergroup\n      description: Remove group from user\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: knowi.removeusergroup\n      with:\n        userId: tools.userId\n        groupId: tools.groupId\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      - name: groupId\n        type: string\n        description: groupId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdashboards\n      description: List dashboards\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: knowi.listdashboards\n      outputParameters:\n      - type: object\n        mapping: $.\n \
  \   - name: getdashboard\n      description: Get dashboard\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: knowi.getdashboard\n      with:\n        objectId: tools.objectId\n      inputParameters:\n      - name: objectId\n        type: string\n        description: objectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdashboardshare\n      description: Get dashboard share info\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: knowi.getdashboardshare\n      with:\n        objectId: tools.objectId\n      inputParameters:\n      - name: objectId\n        type: string\n        description: objectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generateshareurl\n      description: Generate share URL\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: false\n      call: knowi.generateshareurl\n      with:\n        objectId: tools.objectId\n      inputParameters:\n      - name: objectId\n        type: string\n        description: objectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generatesecureshareurl\n      description: Generate secure share URL\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: knowi.generatesecureshareurl\n      with:\n        objectId: tools.objectId\n      inputParameters:\n      - name: objectId\n        type: string\n        description: objectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: generatesecuresharehash\n      description: Generate secure share hash\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: knowi.generatesecuresharehash\n      with:\n   \
  \     objectId: tools.objectId\n      inputParameters:\n      - name: objectId\n        type: string\n        description: objectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    KNOWI_TOKEN: KNOWI_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/knowi/refs/heads/main/capabilities/knowi-capability.yaml
tags:
- Knowi
- API
tools:
- description: Obtain access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: login
- description: Revoke access token
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: logout
- description: List users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusers
- description: Create user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createuser
- description: Search user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchuser
- description: Get user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: Update user
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateuser
- description: Delete user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteuser
- description: Move user assets
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: moveuserassets
- description: List shareable entities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listshareableentities
- description: List groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgroups
- description: Create group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creategroup
- description: Get group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroup
- description: Update group
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updategroup
- description: Delete group
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletegroup
- description: List user groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusergroups
- description: Create group for user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createusergroup
- description: Remove group from user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removeusergroup
- description: List dashboards
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdashboards
- description: Get dashboard
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdashboard
- description: Get dashboard share info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdashboardshare
- description: Generate share URL
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generateshareurl
- description: Generate secure share URL
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generatesecureshareurl
- description: Generate secure share hash
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generatesecuresharehash
---
