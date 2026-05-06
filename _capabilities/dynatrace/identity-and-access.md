---
categories:
- identity-access
consumed_apis: []
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
- update group name and description
- get details of a specific user
- intelligence
- manage user groups
- get, update, or delete a specific group
- apm
- list environments
- identity
- list all environments
- cloud monitoring
- list all permissions for the account
- dynatrace
- analytics
- permanently delete a group
- get details of a specific group
- delete group
- list all users in the account
- list all permissions defined for the account
- permanently remove a user from the account
- list all user groups in the account
- delete a user
- application performance monitoring
- create a new user
- create user
- get, update, or delete a specific user
- get group
- update a user's profile and group memberships
- create group
- list all groups
- list permissions
- create a new user and send an invitation email
- create a new user group
- query permissions
- update a group's name and description
- delete a group
- update group
- application security
- delete user
- get group details
- list all users in the dynatrace account
- digital experience management
- create a new group
- observability
- platform administration
- ai operations
- list all environments associated with the account
- update user
- access control
- get user
- update user profile and groups
- list users
- get user details
- manage account users
- list groups
- iam
- automation
slug: identity-and-access
source_filename: identity-and-access.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Dynatrace Identity And Access\n  description: Identity and access management workflow for platform admins managing Dynatrace users, groups, permissions,\n    and environments across the account.\n  tags:\n  - Dynatrace\n  - Identity\n  - Access Control\n  - Platform Administration\n  - IAM\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    DYNATRACE_OAUTH_TOKEN: DYNATRACE_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: account-management\n    baseUri: https://api.dynatrace.com\n    description: Dynatrace Account Management API for managing users, groups, permissions, and environments.\n    authentication:\n      type: bearer\n      token: '{{DYNATRACE_OAUTH_TOKEN}}'\n    resources:\n    - name: users\n      path: /iam/v1/accounts/{accountUuid}/users\n      description: Manage account users\n      operations:\n      - name: list-users\n        method: GET\n        description:\
  \ Returns a list of all users in the specified Dynatrace account.\n        inputParameters:\n        - name: accountUuid\n          in: path\n          type: string\n          required: true\n          description: The UUID of the Dynatrace account.\n        - name: nextPageKey\n          in: query\n          type: string\n          required: false\n          description: Cursor for the next page of results.\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: The number of users to return per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Creates a new user in the Dynatrace account and sends an invitation email.\n        inputParameters:\n        - name: accountUuid\n          in: path\n          type: string\n          required: true\n          description: The\
  \ UUID of the Dynatrace account.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            email: '{{tools.email}}'\n            firstName: '{{tools.first_name}}'\n            lastName: '{{tools.last_name}}'\n            groups: '{{tools.groups}}'\n    - name: user-detail\n      path: /iam/v1/accounts/{accountUuid}/users/{userId}\n      description: Get, update, or delete a specific user\n      operations:\n      - name: get-user\n        method: GET\n        description: Returns the details of a specific user in the account.\n        inputParameters:\n        - name: accountUuid\n          in: path\n          type: string\n          required: true\n          description: The UUID of the Dynatrace account.\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the user.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-user\n        method: PUT\n        description: Updates the profile information and group memberships for an existing user.\n        inputParameters:\n        - name: accountUuid\n          in: path\n          type: string\n          required: true\n          description: The UUID of the Dynatrace account.\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            email: '{{tools.email}}'\n            firstName: '{{tools.first_name}}'\n            lastName: '{{tools.last_name}}'\n            groups: '{{tools.groups}}'\n      - name: delete-user\n        method:\
  \ DELETE\n        description: Permanently removes the specified user from the Dynatrace account.\n        inputParameters:\n        - name: accountUuid\n          in: path\n          type: string\n          required: true\n          description: The UUID of the Dynatrace account.\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /iam/v1/accounts/{accountUuid}/groups\n      description: Manage user groups\n      operations:\n      - name: list-groups\n        method: GET\n        description: Returns a list of all user groups defined in the account.\n        inputParameters:\n        - name: accountUuid\n          in: path\n          type: string\n          required: true\n          description: The UUID of the Dynatrace account.\n\
  \        - name: nextPageKey\n          in: query\n          type: string\n          required: false\n          description: Cursor for the next page of results.\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: The number of groups to return per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-group\n        method: POST\n        description: Creates a new user group in the account.\n        inputParameters:\n        - name: accountUuid\n          in: path\n          type: string\n          required: true\n          description: The UUID of the Dynatrace account.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n\
  \    - name: group-detail\n      path: /iam/v1/accounts/{accountUuid}/groups/{groupId}\n      description: Get, update, or delete a specific group\n      operations:\n      - name: get-group\n        method: GET\n        description: Returns the details of a specific group.\n        inputParameters:\n        - name: accountUuid\n          in: path\n          type: string\n          required: true\n          description: The UUID of the Dynatrace account.\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the group.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-group\n        method: PUT\n        description: Updates the name and description of an existing group.\n        inputParameters:\n        - name: accountUuid\n          in: path\n          type: string\n          required: true\n      \
  \    description: The UUID of the Dynatrace account.\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the group.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n      - name: delete-group\n        method: DELETE\n        description: Permanently deletes the specified group from the account.\n        inputParameters:\n        - name: accountUuid\n          in: path\n          type: string\n          required: true\n          description: The UUID of the Dynatrace account.\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the group.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: permissions\n      path: /iam/v1/accounts/{accountUuid}/permissions\n      description: Query account-level permissions\n      operations:\n      - name: list-permissions\n        method: GET\n        description: Returns a list of all permissions defined for the account.\n        inputParameters:\n        - name: accountUuid\n          in: path\n          type: string\n          required: true\n          description: The UUID of the Dynatrace account.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments\n      path: /env/v1/accounts/{accountUuid}/environments\n      description: List environments associated with the account\n      operations:\n      - name: list-environments\n        method: GET\n        description: Returns a list of all Dynatrace environments associated with the specified account.\n    \
  \    inputParameters:\n        - name: accountUuid\n          in: path\n          type: string\n          required: true\n          description: The UUID of the Dynatrace account.\n        - name: nextPageKey\n          in: query\n          type: string\n          required: false\n          description: Cursor for the next page of results.\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: The number of environments to return per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8083\n    namespace: identity-access-api\n    description: Unified REST API for Dynatrace identity and access management.\n    resources:\n    - path: /v1/users\n      name: users\n      description: Manage account users\n      operations:\n      - method: GET\n        name: list-users\n        description: List all users\
  \ in the account\n        call: account-management.list-users\n        with:\n          accountUuid: rest.accountUuid\n          nextPageKey: rest.nextPageKey\n          pageSize: rest.pageSize\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-user\n        description: Create a new user\n        call: account-management.create-user\n        with:\n          accountUuid: rest.accountUuid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/{userId}\n      name: user-detail\n      description: Get, update, or delete a specific user\n      operations:\n      - method: GET\n        name: get-user\n        description: Get user details\n        call: account-management.get-user\n        with:\n          accountUuid: rest.accountUuid\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-user\n\
  \        description: Update user profile and groups\n        call: account-management.update-user\n        with:\n          accountUuid: rest.accountUuid\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-user\n        description: Delete a user\n        call: account-management.delete-user\n        with:\n          accountUuid: rest.accountUuid\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/groups\n      name: groups\n      description: Manage user groups\n      operations:\n      - method: GET\n        name: list-groups\n        description: List all groups\n        call: account-management.list-groups\n        with:\n          accountUuid: rest.accountUuid\n          nextPageKey: rest.nextPageKey\n          pageSize: rest.pageSize\n        outputParameters:\n        - type: object\n          mapping: $.\n    \
  \  - method: POST\n        name: create-group\n        description: Create a new group\n        call: account-management.create-group\n        with:\n          accountUuid: rest.accountUuid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/groups/{groupId}\n      name: group-detail\n      description: Get, update, or delete a specific group\n      operations:\n      - method: GET\n        name: get-group\n        description: Get group details\n        call: account-management.get-group\n        with:\n          accountUuid: rest.accountUuid\n          groupId: rest.groupId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-group\n        description: Update group name and description\n        call: account-management.update-group\n        with:\n          accountUuid: rest.accountUuid\n          groupId: rest.groupId\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n      - method: DELETE\n        name: delete-group\n        description: Delete a group\n        call: account-management.delete-group\n        with:\n          accountUuid: rest.accountUuid\n          groupId: rest.groupId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/permissions\n      name: permissions\n      description: Query permissions\n      operations:\n      - method: GET\n        name: list-permissions\n        description: List all permissions for the account\n        call: account-management.list-permissions\n        with:\n          accountUuid: rest.accountUuid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/environments\n      name: environments\n      description: List environments\n      operations:\n      - method: GET\n        name: list-environments\n        description: List all environments\n        call: account-management.list-environments\n        with:\n          accountUuid:\
  \ rest.accountUuid\n          nextPageKey: rest.nextPageKey\n          pageSize: rest.pageSize\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9093\n    namespace: identity-access-mcp\n    transport: http\n    description: MCP server for AI-assisted Dynatrace identity and access management.\n    tools:\n    - name: list-users\n      description: List all users in the Dynatrace account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: account-management.list-users\n      with:\n        accountUuid: tools.accountUuid\n        nextPageKey: tools.nextPageKey\n        pageSize: tools.pageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-user\n      description: Create a new user and send an invitation email\n      hints:\n        readOnly: false\n        openWorld: true\n      call: account-management.create-user\n      with:\n        accountUuid: tools.accountUuid\n    \
  \  outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user\n      description: Get details of a specific user\n      hints:\n        readOnly: true\n        openWorld: true\n      call: account-management.get-user\n      with:\n        accountUuid: tools.accountUuid\n        userId: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-user\n      description: Update a user's profile and group memberships\n      hints:\n        readOnly: false\n        idempotent: true\n        openWorld: true\n      call: account-management.update-user\n      with:\n        accountUuid: tools.accountUuid\n        userId: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-user\n      description: Permanently remove a user from the account\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n        openWorld: true\n      call: account-management.delete-user\n\
  \      with:\n        accountUuid: tools.accountUuid\n        userId: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-groups\n      description: List all user groups in the account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: account-management.list-groups\n      with:\n        accountUuid: tools.accountUuid\n        nextPageKey: tools.nextPageKey\n        pageSize: tools.pageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-group\n      description: Create a new user group\n      hints:\n        readOnly: false\n        openWorld: true\n      call: account-management.create-group\n      with:\n        accountUuid: tools.accountUuid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-group\n      description: Get details of a specific group\n      hints:\n        readOnly: true\n        openWorld: true\n      call: account-management.get-group\n\
  \      with:\n        accountUuid: tools.accountUuid\n        groupId: tools.groupId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-group\n      description: Update a group's name and description\n      hints:\n        readOnly: false\n        idempotent: true\n        openWorld: true\n      call: account-management.update-group\n      with:\n        accountUuid: tools.accountUuid\n        groupId: tools.groupId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-group\n      description: Permanently delete a group\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n        openWorld: true\n      call: account-management.delete-group\n      with:\n        accountUuid: tools.accountUuid\n        groupId: tools.groupId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-permissions\n      description: List all permissions defined for the\
  \ account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: account-management.list-permissions\n      with:\n        accountUuid: tools.accountUuid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-environments\n      description: List all environments associated with the account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: account-management.list-environments\n      with:\n        accountUuid: tools.accountUuid\n        nextPageKey: tools.nextPageKey\n        pageSize: tools.pageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
