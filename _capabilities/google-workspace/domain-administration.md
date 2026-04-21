---
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
- individual group management.
- create a new user.
- list users in the domain.
- get group details.
- google workspace
- update group
- delete group
- make user admin
- sign out a user from all sessions.
- list groups in the domain.
- calendar
- get group
- patch user properties.
- undelete a deleted user.
- email
- sign out user
- organizational unit management.
- video conferencing
- user account management.
- update user
- create a new group.
- get user
- list groups
- create user
- make a user an admin.
- domain administration
- productivity
- create an organizational unit.
- list users
- create org unit
- delete user
- get user details.
- patch user
- group management.
- list users in the google workspace domain.
- update a user.
- create a group.
- individual user management.
- delete a group.
- undelete user
- create group
- user management
- update a group.
- create a new user in the domain.
- list organizational units.
- collaboration
- list org units
- storage
- list groups.
- group management
slug: domain-administration
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
