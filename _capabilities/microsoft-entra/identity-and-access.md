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
- directory management
- list user group memberships.
- create user
- azure ad
- update application properties.
- individual service principal management.
- service principal management.
- update group properties.
- individual group management.
- get group
- list all groups in the directory.
- create a new user in the directory.
- list group members.
- list users
- get application
- get application details.
- list all groups.
- identity governance
- update application
- delete a user from the directory.
- remove group member
- delete application
- get user properties by id.
- list all applications.
- update service principal properties.
- entra
- delete a group.
- delete a service principal.
- security
- add group member
- get user
- delete an application.
- list all application registrations.
- individual application management.
- get group details.
- list user memberships
- list applications
- add a member to a group.
- get service principal
- create service principal
- application registration management.
- create a new service principal.
- group management.
- user account management.
- list group members
- remove a member from a group.
- update user
- create a new group.
- identity
- list all users in the directory.
- microsoft entra
- user group membership.
- access management
- update service principal
- delete service principal
- network security
- microsoft
- register a new application.
- update user properties.
- get user details.
- list all users in microsoft entra directory.
- group membership management.
- list all service principals.
- create group
- list groups and roles a user belongs to.
- authentication
- update group
- create a new user.
- zero trust
- list service principals
- delete user
- create application
- list groups
- update service principal.
- delete an application registration.
- delete a user.
- individual user management.
- list members of a group.
- get service principal details.
- delete group
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
