---
categories: []
consumed_apis:
- gws-admin
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
- delete a user.
- organizational unit management.
- get group details.
- individual user management.
- create org unit
- list users
- make user admin
- list users in the google workspace domain.
- get group
- create a new group.
- update a user.
- undelete a deleted user.
- user management
- collaboration
- delete a group.
- patch user
- list groups.
- delete user
- video conferencing
- create a group.
- patch user properties.
- get user
- update user
- list org units
- individual group management.
- undelete user
- email
- list groups in the domain.
- list users in the domain.
- sign out user
- update a group.
- domain administration
- delete group
- create a new user in the domain.
- list groups
- productivity
- google workspace
- update group
- create user
- create an organizational unit.
- make a user an admin.
- user account management.
- sign out a user from all sessions.
- group management
- create a new user.
- create group
- get user details.
- group management.
- list organizational units.
- storage
- calendar
slug: domain-administration
source_filename: domain-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Google Workspace Domain Administration\"\n  description: \"Unified workflow for managing Google Workspace domain resources including users, groups, and organizational units. Used by IT administrators and workspace domain managers.\"\n  tags:\n    - Google Workspace\n    - Domain Administration\n    - User Management\n    - Group Management\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      GOOGLE_WORKSPACE_ACCESS_TOKEN: GOOGLE_WORKSPACE_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: gws-admin\n      location: ./shared/admin-directory.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: gws-domain-admin-api\n      description: \"Unified REST API for Google Workspace domain administration.\"\n      resources:\n        - path: /v1/users\n          name: users\n          description: \"User account management.\"\n          operations:\n            - method:\
  \ GET\n              name: list-users\n              description: \"List users in the domain.\"\n              call: \"gws-admin.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-user\n              description: \"Create a new user.\"\n              call: \"gws-admin.create-user\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users/{id}\n          name: user-details\n          description: \"Individual user management.\"\n          operations:\n            - method: GET\n              name: get-user\n              description: \"Get user details.\"\n              call: \"gws-admin.get-user\"\n              with:\n                userKey: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name:\
  \ update-user\n              description: \"Update a user.\"\n              call: \"gws-admin.update-user\"\n              with:\n                userKey: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-user\n              description: \"Delete a user.\"\n              call: \"gws-admin.delete-user\"\n              with:\n                userKey: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/groups\n          name: groups\n          description: \"Group management.\"\n          operations:\n            - method: GET\n              name: list-groups\n              description: \"List groups.\"\n              call: \"gws-admin.list-groups\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name:\
  \ create-group\n              description: \"Create a group.\"\n              call: \"gws-admin.create-group\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/groups/{id}\n          name: group-details\n          description: \"Individual group management.\"\n          operations:\n            - method: GET\n              name: get-group\n              description: \"Get group details.\"\n              call: \"gws-admin.get-group\"\n              with:\n                groupKey: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-group\n              description: \"Update a group.\"\n              call: \"gws-admin.update-group\"\n              with:\n                groupKey: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            -\
  \ method: DELETE\n              name: delete-group\n              description: \"Delete a group.\"\n              call: \"gws-admin.delete-group\"\n              with:\n                groupKey: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/org-units\n          name: org-units\n          description: \"Organizational unit management.\"\n          operations:\n            - method: GET\n              name: list-org-units\n              description: \"List organizational units.\"\n              call: \"gws-admin.list-org-units\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-org-unit\n              description: \"Create an organizational unit.\"\n              call: \"gws-admin.create-org-unit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\
  \n    - type: mcp\n      port: 9080\n      namespace: gws-domain-admin-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Google Workspace domain administration.\"\n      tools:\n        - name: list-users\n          description: \"List users in the Google Workspace domain.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"gws-admin.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-user\n          description: \"Create a new user in the domain.\"\n          hints:\n            readOnly: false\n          call: \"gws-admin.create-user\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-user\n          description: \"Get user details.\"\n          hints:\n            readOnly: true\n          call: \"gws-admin.get-user\"\n          with:\n            userKey: \"tools.userKey\"\n        \
  \  outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-user\n          description: \"Update a user.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"gws-admin.update-user\"\n          with:\n            userKey: \"tools.userKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: patch-user\n          description: \"Patch user properties.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"gws-admin.patch-user\"\n          with:\n            userKey: \"tools.userKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-user\n          description: \"Delete a user.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"gws-admin.delete-user\"\n          with:\n            userKey: \"tools.userKey\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: make-user-admin\n          description: \"Make a user an admin.\"\n          hints:\n            readOnly: false\n          call: \"gws-admin.make-user-admin\"\n          with:\n            userKey: \"tools.userKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: undelete-user\n          description: \"Undelete a deleted user.\"\n          hints:\n            readOnly: false\n          call: \"gws-admin.undelete-user\"\n          with:\n            userKey: \"tools.userKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: sign-out-user\n          description: \"Sign out a user from all sessions.\"\n          hints:\n            readOnly: false\n          call: \"gws-admin.sign-out-user\"\n          with:\n            userKey: \"tools.userKey\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: list-groups\n          description: \"List groups in the domain.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"gws-admin.list-groups\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-group\n          description: \"Create a new group.\"\n          hints:\n            readOnly: false\n          call: \"gws-admin.create-group\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-group\n          description: \"Get group details.\"\n          hints:\n            readOnly: true\n          call: \"gws-admin.get-group\"\n          with:\n            groupKey: \"tools.groupKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-group\n          description: \"Update a group.\"\n          hints:\n\
  \            readOnly: false\n            idempotent: true\n          call: \"gws-admin.update-group\"\n          with:\n            groupKey: \"tools.groupKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-group\n          description: \"Delete a group.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"gws-admin.delete-group\"\n          with:\n            groupKey: \"tools.groupKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-org-units\n          description: \"List organizational units.\"\n          hints:\n            readOnly: true\n          call: \"gws-admin.list-org-units\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-org-unit\n          description: \"Create an organizational unit.\"\n          hints:\n            readOnly: false\n\
  \          call: \"gws-admin.create-org-unit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
