---
categories: []
consumed_apis: []
description: Unified workflow for managing Google Workspace domain resources including users, groups, and organizational units. Used by IT administrators and workspace domain managers.
layout: capability
name: Google Workspace Domain Administration
operations:
- description: List users in the domain.
  method: GET
  name: list-users
  path: /v1/users
- description: Create a new user.
  method: POST
  name: create-user
  path: /v1/users
- description: Get user details.
  method: GET
  name: get-user
  path: /v1/users/{id}
- description: Update a user.
  method: PUT
  name: update-user
  path: /v1/users/{id}
- description: Delete a user.
  method: DELETE
  name: delete-user
  path: /v1/users/{id}
- description: List groups.
  method: GET
  name: list-groups
  path: /v1/groups
- description: Create a group.
  method: POST
  name: create-group
  path: /v1/groups
- description: Get group details.
  method: GET
  name: get-group
  path: /v1/groups/{id}
- description: Update a group.
  method: PUT
  name: update-group
  path: /v1/groups/{id}
- description: Delete a group.
  method: DELETE
  name: delete-group
  path: /v1/groups/{id}
- description: List organizational units.
  method: GET
  name: list-org-units
  path: /v1/org-units
- description: Create an organizational unit.
  method: POST
  name: create-org-unit
  path: /v1/org-units
personas: []
provider_name: Google Workspace
provider_slug: google-workspace
search_terms:
- create a new group.
- sign out a user from all sessions.
- google workspace
- create org unit
- update a user.
- storage
- create an organizational unit.
- calendar
- delete group
- create a new user in the domain.
- list users in the google workspace domain.
- individual group management.
- delete a user.
- create user
- get group
- get user details.
- update a group.
- list users in the domain.
- patch user properties.
- create group
- make user admin
- update group
- list organizational units.
- domain administration
- productivity
- delete user
- delete a group.
- undelete user
- get group details.
- group management
- organizational unit management.
- patch user
- individual user management.
- list groups in the domain.
- video conferencing
- update user
- make a user an admin.
- get user
- create a group.
- email
- list org units
- sign out user
- list users
- list groups.
- list groups
- user management
- group management.
- user account management.
- collaboration
- undelete a deleted user.
- create a new user.
slug: domain-administration
source_filename: domain-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Workspace Domain Administration\n  description: Unified workflow for managing Google Workspace domain resources including users, groups, and organizational\n    units. Used by IT administrators and workspace domain managers.\n  tags:\n  - Google Workspace\n  - Domain Administration\n  - User Management\n  - Group Management\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_WORKSPACE_ACCESS_TOKEN: GOOGLE_WORKSPACE_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: gws-admin\n    baseUri: https://admin.googleapis.com\n    description: Google Admin SDK Directory API for domain management.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_WORKSPACE_ACCESS_TOKEN}}'\n    resources:\n    - name: users\n      path: /admin/directory/v1/users\n      description: User account management.\n      operations:\n      - name: list-users\n        method: GET\n   \
  \     description: List users in the domain.\n        inputParameters:\n        - name: domain\n          in: query\n          type: string\n          required: false\n          description: Domain name.\n        - name: customer\n          in: query\n          type: string\n          required: false\n          description: Customer ID.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: Maximum results (1-500).\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description: Page token.\n        - name: query\n          in: query\n          type: string\n          required: false\n          description: Search query.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create a new user.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            primaryEmail: '{{tools.primaryEmail}}'\n            name:\n              givenName: '{{tools.givenName}}'\n              familyName: '{{tools.familyName}}'\n            password: '{{tools.password}}'\n    - name: user-details\n      path: /admin/directory/v1/users/{userKey}\n      description: Individual user management.\n      operations:\n      - name: get-user\n        method: GET\n        description: Get user details.\n        inputParameters:\n        - name: userKey\n          in: path\n          type: string\n          required: true\n          description: User email or ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-user\n        method: PUT\n        description: Update a user.\n        inputParameters:\n\
  \        - name: userKey\n          in: path\n          type: string\n          required: true\n          description: User email or ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name:\n              givenName: '{{tools.givenName}}'\n      - name: patch-user\n        method: PATCH\n        description: Patch a user.\n        inputParameters:\n        - name: userKey\n          in: path\n          type: string\n          required: true\n          description: User email or ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            suspended: '{{tools.suspended}}'\n      - name: delete-user\n        method: DELETE\n        description: Delete a user.\n        inputParameters:\n        - name: userKey\n\
  \          in: path\n          type: string\n          required: true\n          description: User email or ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-admin\n      path: /admin/directory/v1/users/{userKey}/makeAdmin\n      description: User admin operations.\n      operations:\n      - name: make-user-admin\n        method: POST\n        description: Make a user an admin.\n        inputParameters:\n        - name: userKey\n          in: path\n          type: string\n          required: true\n          description: User email or ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            status: '{{tools.status}}'\n    - name: user-undelete\n      path: /admin/directory/v1/users/{userKey}/undelete\n      description: User undelete.\n      operations:\n\
  \      - name: undelete-user\n        method: POST\n        description: Undelete a user.\n        inputParameters:\n        - name: userKey\n          in: path\n          type: string\n          required: true\n          description: User email or ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-signout\n      path: /admin/directory/v1/users/{userKey}/signOut\n      description: User sign out.\n      operations:\n      - name: sign-out-user\n        method: POST\n        description: Sign out a user from all sessions.\n        inputParameters:\n        - name: userKey\n          in: path\n          type: string\n          required: true\n          description: User email or ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /admin/directory/v1/groups\n      description: Group\
  \ management.\n      operations:\n      - name: list-groups\n        method: GET\n        description: List groups in the domain.\n        inputParameters:\n        - name: domain\n          in: query\n          type: string\n          required: false\n          description: Domain name.\n        - name: customer\n          in: query\n          type: string\n          required: false\n          description: Customer ID.\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: Maximum results.\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description: Page token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-group\n        method: POST\n        description: Create a new group.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            email: '{{tools.email}}'\n            name: '{{tools.name}}'\n    - name: group-details\n      path: /admin/directory/v1/groups/{groupKey}\n      description: Individual group management.\n      operations:\n      - name: get-group\n        method: GET\n        description: Get group details.\n        inputParameters:\n        - name: groupKey\n          in: path\n          type: string\n          required: true\n          description: Group email or ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-group\n        method: PUT\n        description: Update a group.\n        inputParameters:\n        - name: groupKey\n          in: path\n          type: string\n          required: true\n          description: Group email or ID.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: delete-group\n        method: DELETE\n        description: Delete a group.\n        inputParameters:\n        - name: groupKey\n          in: path\n          type: string\n          required: true\n          description: Group email or ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: org-units\n      path: /admin/directory/v1/customer/{customerId}/orgunits\n      description: Organizational unit management.\n      operations:\n      - name: list-org-units\n        method: GET\n        description: List organizational units.\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n          description: Customer ID.\n        outputRawFormat: json\n       \
  \ outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-org-unit\n        method: POST\n        description: Create an organizational unit.\n        inputParameters:\n        - name: customerId\n          in: path\n          type: string\n          required: true\n          description: Customer ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            parentOrgUnitPath: '{{tools.parentOrgUnitPath}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: gws-domain-admin-api\n    description: Unified REST API for Google Workspace domain administration.\n    resources:\n    - path: /v1/users\n      name: users\n      description: User account management.\n      operations:\n      - method: GET\n        name: list-users\n        description: List users in\
  \ the domain.\n        call: gws-admin.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-user\n        description: Create a new user.\n        call: gws-admin.create-user\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/{id}\n      name: user-details\n      description: Individual user management.\n      operations:\n      - method: GET\n        name: get-user\n        description: Get user details.\n        call: gws-admin.get-user\n        with:\n          userKey: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-user\n        description: Update a user.\n        call: gws-admin.update-user\n        with:\n          userKey: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-user\n        description: Delete\
  \ a user.\n        call: gws-admin.delete-user\n        with:\n          userKey: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/groups\n      name: groups\n      description: Group management.\n      operations:\n      - method: GET\n        name: list-groups\n        description: List groups.\n        call: gws-admin.list-groups\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-group\n        description: Create a group.\n        call: gws-admin.create-group\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/groups/{id}\n      name: group-details\n      description: Individual group management.\n      operations:\n      - method: GET\n        name: get-group\n        description: Get group details.\n        call: gws-admin.get-group\n        with:\n          groupKey: rest.id\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n      - method: PUT\n        name: update-group\n        description: Update a group.\n        call: gws-admin.update-group\n        with:\n          groupKey: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-group\n        description: Delete a group.\n        call: gws-admin.delete-group\n        with:\n          groupKey: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/org-units\n      name: org-units\n      description: Organizational unit management.\n      operations:\n      - method: GET\n        name: list-org-units\n        description: List organizational units.\n        call: gws-admin.list-org-units\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-org-unit\n        description: Create an organizational unit.\n        call: gws-admin.create-org-unit\n    \
  \    outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: gws-domain-admin-mcp\n    transport: http\n    description: MCP server for AI-assisted Google Workspace domain administration.\n    tools:\n    - name: list-users\n      description: List users in the Google Workspace domain.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: gws-admin.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-user\n      description: Create a new user in the domain.\n      hints:\n        readOnly: false\n      call: gws-admin.create-user\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user\n      description: Get user details.\n      hints:\n        readOnly: true\n      call: gws-admin.get-user\n      with:\n        userKey: tools.userKey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-user\n  \
  \    description: Update a user.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: gws-admin.update-user\n      with:\n        userKey: tools.userKey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patch-user\n      description: Patch user properties.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: gws-admin.patch-user\n      with:\n        userKey: tools.userKey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-user\n      description: Delete a user.\n      hints:\n        destructive: true\n        idempotent: true\n      call: gws-admin.delete-user\n      with:\n        userKey: tools.userKey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: make-user-admin\n      description: Make a user an admin.\n      hints:\n        readOnly: false\n      call: gws-admin.make-user-admin\n      with:\n        userKey: tools.userKey\n    \
  \  outputParameters:\n      - type: object\n        mapping: $.\n    - name: undelete-user\n      description: Undelete a deleted user.\n      hints:\n        readOnly: false\n      call: gws-admin.undelete-user\n      with:\n        userKey: tools.userKey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sign-out-user\n      description: Sign out a user from all sessions.\n      hints:\n        readOnly: false\n      call: gws-admin.sign-out-user\n      with:\n        userKey: tools.userKey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-groups\n      description: List groups in the domain.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: gws-admin.list-groups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-group\n      description: Create a new group.\n      hints:\n        readOnly: false\n      call: gws-admin.create-group\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-group\n      description: Get group details.\n      hints:\n        readOnly: true\n      call: gws-admin.get-group\n      with:\n        groupKey: tools.groupKey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-group\n      description: Update a group.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: gws-admin.update-group\n      with:\n        groupKey: tools.groupKey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-group\n      description: Delete a group.\n      hints:\n        destructive: true\n        idempotent: true\n      call: gws-admin.delete-group\n      with:\n        groupKey: tools.groupKey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-org-units\n      description: List organizational units.\n      hints:\n        readOnly: true\n      call: gws-admin.list-org-units\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-org-unit\n      description: Create an organizational unit.\n      hints:\n        readOnly: false\n      call: gws-admin.create-org-unit\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-workspace/refs/heads/main/capabilities/domain-administration.yaml
tags:
- Google Workspace
- Domain Administration
- User Management
- Group Management
tools:
- description: List users in the Google Workspace domain.
  hints:
    openWorld: true
    readOnly: true
  name: list-users
- description: Create a new user in the domain.
  hints:
    readOnly: false
  name: create-user
- description: Get user details.
  hints:
    readOnly: true
  name: get-user
- description: Update a user.
  hints:
    idempotent: true
    readOnly: false
  name: update-user
- description: Patch user properties.
  hints:
    idempotent: true
    readOnly: false
  name: patch-user
- description: Delete a user.
  hints:
    destructive: true
    idempotent: true
  name: delete-user
- description: Make a user an admin.
  hints:
    readOnly: false
  name: make-user-admin
- description: Undelete a deleted user.
  hints:
    readOnly: false
  name: undelete-user
- description: Sign out a user from all sessions.
  hints:
    readOnly: false
  name: sign-out-user
- description: List groups in the domain.
  hints:
    openWorld: true
    readOnly: true
  name: list-groups
- description: Create a new group.
  hints:
    readOnly: false
  name: create-group
- description: Get group details.
  hints:
    readOnly: true
  name: get-group
- description: Update a group.
  hints:
    idempotent: true
    readOnly: false
  name: update-group
- description: Delete a group.
  hints:
    destructive: true
    idempotent: true
  name: delete-group
- description: List organizational units.
  hints:
    readOnly: true
  name: list-org-units
- description: Create an organizational unit.
  hints:
    readOnly: false
  name: create-org-unit
---
