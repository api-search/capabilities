---
categories:
- identity-access
consumed_apis:
- account-management
description: Identity and access management workflow for platform admins managing Dynatrace users, groups, permissions, and environments across the account.
layout: capability
name: Dynatrace Identity And Access
operations:
- description: List all users in the account
  method: GET
  name: list-users
  path: /v1/users
- description: Create a new user
  method: POST
  name: create-user
  path: /v1/users
- description: Get user details
  method: GET
  name: get-user
  path: /v1/users/{userId}
- description: Update user profile and groups
  method: PUT
  name: update-user
  path: /v1/users/{userId}
- description: Delete a user
  method: DELETE
  name: delete-user
  path: /v1/users/{userId}
- description: List all groups
  method: GET
  name: list-groups
  path: /v1/groups
- description: Create a new group
  method: POST
  name: create-group
  path: /v1/groups
- description: Get group details
  method: GET
  name: get-group
  path: /v1/groups/{groupId}
- description: Update group name and description
  method: PUT
  name: update-group
  path: /v1/groups/{groupId}
- description: Delete a group
  method: DELETE
  name: delete-group
  path: /v1/groups/{groupId}
- description: List all permissions for the account
  method: GET
  name: list-permissions
  path: /v1/permissions
- description: List all environments
  method: GET
  name: list-environments
  path: /v1/environments
personas: []
provider_name: Dynatrace
provider_slug: dynatrace
search_terms:
- get details of a specific group
- get user
- list all users in the dynatrace account
- iam
- application performance monitoring
- permanently remove a user from the account
- list all groups
- list all user groups in the account
- delete a group
- list all environments associated with the account
- list all permissions for the account
- automation
- update user
- query permissions
- list all users in the account
- get user details
- update user profile and groups
- update a user's profile and group memberships
- create a new user group
- analytics
- delete group
- update a group's name and description
- list environments
- intelligence
- list all environments
- ai operations
- application security
- manage account users
- get, update, or delete a specific group
- create a new group
- list users
- get group details
- platform administration
- identity
- get, update, or delete a specific user
- delete user
- permanently delete a group
- create user
- list groups
- get group
- apm
- list all permissions defined for the account
- manage user groups
- delete a user
- digital experience management
- dynatrace
- get details of a specific user
- create group
- cloud monitoring
- list permissions
- create a new user and send an invitation email
- access control
- create a new user
- observability
- update group
- update group name and description
slug: identity-and-access
source_filename: identity-and-access.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Dynatrace Identity And Access\"\n  description: \"Identity and access management workflow for platform admins managing Dynatrace users, groups, permissions, and environments across the account.\"\n  tags:\n    - Dynatrace\n    - Identity\n    - Access Control\n    - Platform Administration\n    - IAM\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      DYNATRACE_OAUTH_TOKEN: DYNATRACE_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: account-management\n      location: ./shared/account-management.yaml\n\n  exposes:\n    - type: rest\n      port: 8083\n      namespace: identity-access-api\n      description: \"Unified REST API for Dynatrace identity and access management.\"\n      resources:\n        - path: /v1/users\n          name: users\n          description: \"Manage account users\"\n          operations:\n            - method: GET\n              name: list-users\n   \
  \           description: \"List all users in the account\"\n              call: \"account-management.list-users\"\n              with:\n                accountUuid: \"rest.accountUuid\"\n                nextPageKey: \"rest.nextPageKey\"\n                pageSize: \"rest.pageSize\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-user\n              description: \"Create a new user\"\n              call: \"account-management.create-user\"\n              with:\n                accountUuid: \"rest.accountUuid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users/{userId}\n          name: user-detail\n          description: \"Get, update, or delete a specific user\"\n          operations:\n            - method: GET\n              name: get-user\n              description: \"Get user details\"\n              call:\
  \ \"account-management.get-user\"\n              with:\n                accountUuid: \"rest.accountUuid\"\n                userId: \"rest.userId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-user\n              description: \"Update user profile and groups\"\n              call: \"account-management.update-user\"\n              with:\n                accountUuid: \"rest.accountUuid\"\n                userId: \"rest.userId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-user\n              description: \"Delete a user\"\n              call: \"account-management.delete-user\"\n              with:\n                accountUuid: \"rest.accountUuid\"\n                userId: \"rest.userId\"\n              outputParameters:\n                - type: object\n                \
  \  mapping: \"$.\"\n        - path: /v1/groups\n          name: groups\n          description: \"Manage user groups\"\n          operations:\n            - method: GET\n              name: list-groups\n              description: \"List all groups\"\n              call: \"account-management.list-groups\"\n              with:\n                accountUuid: \"rest.accountUuid\"\n                nextPageKey: \"rest.nextPageKey\"\n                pageSize: \"rest.pageSize\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-group\n              description: \"Create a new group\"\n              call: \"account-management.create-group\"\n              with:\n                accountUuid: \"rest.accountUuid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/groups/{groupId}\n          name: group-detail\n          description:\
  \ \"Get, update, or delete a specific group\"\n          operations:\n            - method: GET\n              name: get-group\n              description: \"Get group details\"\n              call: \"account-management.get-group\"\n              with:\n                accountUuid: \"rest.accountUuid\"\n                groupId: \"rest.groupId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-group\n              description: \"Update group name and description\"\n              call: \"account-management.update-group\"\n              with:\n                accountUuid: \"rest.accountUuid\"\n                groupId: \"rest.groupId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-group\n              description: \"Delete a group\"\n              call: \"account-management.delete-group\"\
  \n              with:\n                accountUuid: \"rest.accountUuid\"\n                groupId: \"rest.groupId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/permissions\n          name: permissions\n          description: \"Query permissions\"\n          operations:\n            - method: GET\n              name: list-permissions\n              description: \"List all permissions for the account\"\n              call: \"account-management.list-permissions\"\n              with:\n                accountUuid: \"rest.accountUuid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/environments\n          name: environments\n          description: \"List environments\"\n          operations:\n            - method: GET\n              name: list-environments\n              description: \"List all environments\"\n              call: \"account-management.list-environments\"\
  \n              with:\n                accountUuid: \"rest.accountUuid\"\n                nextPageKey: \"rest.nextPageKey\"\n                pageSize: \"rest.pageSize\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9093\n      namespace: identity-access-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Dynatrace identity and access management.\"\n      tools:\n        - name: list-users\n          description: \"List all users in the Dynatrace account\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"account-management.list-users\"\n          with:\n            accountUuid: \"tools.accountUuid\"\n            nextPageKey: \"tools.nextPageKey\"\n            pageSize: \"tools.pageSize\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-user\n          description: \"Create\
  \ a new user and send an invitation email\"\n          hints:\n            readOnly: false\n            openWorld: true\n          call: \"account-management.create-user\"\n          with:\n            accountUuid: \"tools.accountUuid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-user\n          description: \"Get details of a specific user\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"account-management.get-user\"\n          with:\n            accountUuid: \"tools.accountUuid\"\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-user\n          description: \"Update a user's profile and group memberships\"\n          hints:\n            readOnly: false\n            idempotent: true\n            openWorld: true\n          call: \"account-management.update-user\"\n          with:\n\
  \            accountUuid: \"tools.accountUuid\"\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-user\n          description: \"Permanently remove a user from the account\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n            openWorld: true\n          call: \"account-management.delete-user\"\n          with:\n            accountUuid: \"tools.accountUuid\"\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-groups\n          description: \"List all user groups in the account\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"account-management.list-groups\"\n          with:\n            accountUuid: \"tools.accountUuid\"\n            nextPageKey: \"tools.nextPageKey\"\n           \
  \ pageSize: \"tools.pageSize\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-group\n          description: \"Create a new user group\"\n          hints:\n            readOnly: false\n            openWorld: true\n          call: \"account-management.create-group\"\n          with:\n            accountUuid: \"tools.accountUuid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-group\n          description: \"Get details of a specific group\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"account-management.get-group\"\n          with:\n            accountUuid: \"tools.accountUuid\"\n            groupId: \"tools.groupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-group\n          description: \"Update a group's name and description\"\n          hints:\n\
  \            readOnly: false\n            idempotent: true\n            openWorld: true\n          call: \"account-management.update-group\"\n          with:\n            accountUuid: \"tools.accountUuid\"\n            groupId: \"tools.groupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-group\n          description: \"Permanently delete a group\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n            openWorld: true\n          call: \"account-management.delete-group\"\n          with:\n            accountUuid: \"tools.accountUuid\"\n            groupId: \"tools.groupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-permissions\n          description: \"List all permissions defined for the account\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call:\
  \ \"account-management.list-permissions\"\n          with:\n            accountUuid: \"tools.accountUuid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-environments\n          description: \"List all environments associated with the account\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"account-management.list-environments\"\n          with:\n            accountUuid: \"tools.accountUuid\"\n            nextPageKey: \"tools.nextPageKey\"\n            pageSize: \"tools.pageSize\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/dynatrace/refs/heads/main/capabilities/identity-and-access.yaml
tags:
- Dynatrace
- Identity
- Access Control
- Platform Administration
- IAM
tools:
- description: List all users in the Dynatrace account
  hints:
    openWorld: true
    readOnly: true
  name: list-users
- description: Create a new user and send an invitation email
  hints:
    openWorld: true
    readOnly: false
  name: create-user
- description: Get details of a specific user
  hints:
    openWorld: true
    readOnly: true
  name: get-user
- description: Update a user's profile and group memberships
  hints:
    idempotent: true
    openWorld: true
    readOnly: false
  name: update-user
- description: Permanently remove a user from the account
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: delete-user
- description: List all user groups in the account
  hints:
    openWorld: true
    readOnly: true
  name: list-groups
- description: Create a new user group
  hints:
    openWorld: true
    readOnly: false
  name: create-group
- description: Get details of a specific group
  hints:
    openWorld: true
    readOnly: true
  name: get-group
- description: Update a group's name and description
  hints:
    idempotent: true
    openWorld: true
    readOnly: false
  name: update-group
- description: Permanently delete a group
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: delete-group
- description: List all permissions defined for the account
  hints:
    openWorld: true
    readOnly: true
  name: list-permissions
- description: List all environments associated with the account
  hints:
    openWorld: true
    readOnly: true
  name: list-environments
---
