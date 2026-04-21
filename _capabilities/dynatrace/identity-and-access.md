---
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
- apm
- get user details
- dynatrace
- manage user groups
- create group
- manage account users
- delete a user
- delete group
- list all users in the dynatrace account
- application performance monitoring
- query permissions
- list all users in the account
- update user
- permanently remove a user from the account
- update a group's name and description
- list all environments
- analytics
- get details of a specific user
- list all environments associated with the account
- observability
- iam
- list all user groups in the account
- intelligence
- update group name and description
- create a new group
- update a user's profile and group memberships
- update group
- access control
- cloud monitoring
- create a new user and send an invitation email
- get details of a specific group
- get group details
- create a new user group
- list all permissions defined for the account
- get, update, or delete a specific user
- list permissions
- get group
- get user
- digital experience management
- automation
- update user profile and groups
- list all permissions for the account
- list environments
- list groups
- platform administration
- get, update, or delete a specific group
- application security
- delete a group
- identity
- list all groups
- create a new user
- delete user
- ai operations
- permanently delete a group
- list users
- create user
slug: identity-and-access
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
