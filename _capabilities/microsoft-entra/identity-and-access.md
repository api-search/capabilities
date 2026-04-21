---
consumed_apis:
- entra-graph
description: Unified workflow for managing identity and access including users, groups, applications, and service principals in Microsoft Entra ID. Used by IT administrators and identity engineers.
layout: capability
name: Microsoft Entra Identity and Access Management
operations:
- description: List all users in the directory.
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
- description: Update user properties.
  method: PATCH
  name: update-user
  path: /v1/users/{id}
- description: Delete a user.
  method: DELETE
  name: delete-user
  path: /v1/users/{id}
- description: List user group memberships.
  method: GET
  name: list-user-memberships
  path: /v1/users/{id}/memberships
- description: List all groups.
  method: GET
  name: list-groups
  path: /v1/groups
- description: Create a new group.
  method: POST
  name: create-group
  path: /v1/groups
- description: Get group details.
  method: GET
  name: get-group
  path: /v1/groups/{id}
- description: Update group properties.
  method: PATCH
  name: update-group
  path: /v1/groups/{id}
- description: Delete a group.
  method: DELETE
  name: delete-group
  path: /v1/groups/{id}
- description: List group members.
  method: GET
  name: list-group-members
  path: /v1/groups/{id}/members
- description: Add a member to a group.
  method: POST
  name: add-group-member
  path: /v1/groups/{id}/members
- description: List all applications.
  method: GET
  name: list-applications
  path: /v1/applications
- description: Register a new application.
  method: POST
  name: create-application
  path: /v1/applications
- description: Get application details.
  method: GET
  name: get-application
  path: /v1/applications/{id}
- description: Update application properties.
  method: PATCH
  name: update-application
  path: /v1/applications/{id}
- description: Delete an application.
  method: DELETE
  name: delete-application
  path: /v1/applications/{id}
- description: List all service principals.
  method: GET
  name: list-service-principals
  path: /v1/service-principals
- description: Create a new service principal.
  method: POST
  name: create-service-principal
  path: /v1/service-principals
- description: Get service principal details.
  method: GET
  name: get-service-principal
  path: /v1/service-principals/{id}
- description: Update service principal.
  method: PATCH
  name: update-service-principal
  path: /v1/service-principals/{id}
- description: Delete a service principal.
  method: DELETE
  name: delete-service-principal
  path: /v1/service-principals/{id}
personas: []
provider_name: Microsoft Entra
provider_slug: microsoft-entra
search_terms:
- update application properties.
- update group
- update service principal
- azure ad
- delete service principal
- list users
- list user memberships
- individual user management.
- user group membership.
- list user group memberships.
- get application
- remove group member
- create user
- application registration management.
- get service principal details.
- group membership management.
- create service principal
- create application
- list groups and roles a user belongs to.
- update application
- delete group
- update user properties.
- identity governance
- group management.
- create a new group.
- get group details.
- identity
- individual service principal management.
- delete a user.
- authentication
- entra
- list all applications.
- get service principal
- directory management
- delete application
- microsoft entra
- user account management.
- delete an application registration.
- access management
- list groups
- individual application management.
- list all users in microsoft entra directory.
- list all service principals.
- list applications
- zero trust
- list all users in the directory.
- delete a service principal.
- delete a user from the directory.
- security
- list all groups in the directory.
- create a new user in the directory.
- update service principal.
- individual group management.
- delete a group.
- get application details.
- get group
- update service principal properties.
- create a new user.
- list group members
- create a new service principal.
- service principal management.
- list group members.
- delete user
- update user
- register a new application.
- get user properties by id.
- network security
- microsoft
- list members of a group.
- remove a member from a group.
- delete an application.
- add a member to a group.
- get user details.
- add group member
- list service principals
- get user
- update group properties.
- list all application registrations.
- create group
- list all groups.
slug: identity-and-access
tags:
- Microsoft Entra
- Identity
- Access Management
- Directory Management
tools:
- description: List all users in Microsoft Entra directory.
  hints:
    openWorld: true
    readOnly: true
  name: list-users
- description: Create a new user in the directory.
  hints:
    readOnly: false
  name: create-user
- description: Get user properties by ID.
  hints:
    readOnly: true
  name: get-user
- description: Update user properties.
  hints:
    idempotent: true
    readOnly: false
  name: update-user
- description: Delete a user from the directory.
  hints:
    destructive: true
    idempotent: true
  name: delete-user
- description: List groups and roles a user belongs to.
  hints:
    readOnly: true
  name: list-user-memberships
- description: List all groups in the directory.
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
- description: Update group properties.
  hints:
    idempotent: true
    readOnly: false
  name: update-group
- description: Delete a group.
  hints:
    destructive: true
    idempotent: true
  name: delete-group
- description: List members of a group.
  hints:
    readOnly: true
  name: list-group-members
- description: Add a member to a group.
  hints:
    readOnly: false
  name: add-group-member
- description: Remove a member from a group.
  hints:
    destructive: true
    idempotent: true
  name: remove-group-member
- description: List all application registrations.
  hints:
    openWorld: true
    readOnly: true
  name: list-applications
- description: Register a new application.
  hints:
    readOnly: false
  name: create-application
- description: Get application details.
  hints:
    readOnly: true
  name: get-application
- description: Update application properties.
  hints:
    idempotent: true
    readOnly: false
  name: update-application
- description: Delete an application registration.
  hints:
    destructive: true
    idempotent: true
  name: delete-application
- description: List all service principals.
  hints:
    openWorld: true
    readOnly: true
  name: list-service-principals
- description: Create a new service principal.
  hints:
    readOnly: false
  name: create-service-principal
- description: Get service principal details.
  hints:
    readOnly: true
  name: get-service-principal
- description: Update service principal properties.
  hints:
    idempotent: true
    readOnly: false
  name: update-service-principal
- description: Delete a service principal.
  hints:
    destructive: true
    idempotent: true
  name: delete-service-principal
---
