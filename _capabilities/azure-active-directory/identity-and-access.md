---
categories:
- identity-access
consumed_apis:
- graph-identity
description: Unified identity and access management workflow combining user lifecycle, group management, application registration, and service principal operations. Used by IT administrators and identity engineers to manage enterprise identity infrastructure.
layout: capability
name: Azure AD Identity and Access Management
operations:
- description: List directory users.
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
  path: /v1/users/{userId}
- description: Update user properties.
  method: PATCH
  name: update-user
  path: /v1/users/{userId}
- description: Delete a user.
  method: DELETE
  name: delete-user
  path: /v1/users/{userId}
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
  path: /v1/groups/{groupId}
- description: List group members.
  method: GET
  name: list-group-members
  path: /v1/groups/{groupId}/members
- description: Add a group member.
  method: POST
  name: add-group-member
  path: /v1/groups/{groupId}/members
- description: List app registrations.
  method: GET
  name: list-applications
  path: /v1/applications
- description: List service principals.
  method: GET
  name: list-service-principals
  path: /v1/service-principals
personas: []
provider_name: Azure Active Directory
provider_slug: azure-active-directory
search_terms:
- get user
- create application
- create a new azure ad user account.
- scim
- get azure ad user details by id or upn.
- get application
- update user properties.
- create a new azure ad group.
- list groups and roles a user belongs to.
- create a new user.
- get user details.
- get group details.
- list applications
- service principal management.
- update user
- single user operations.
- list groups.
- list user memberships
- list azure ad groups with optional filtering.
- get an application registration by id.
- authorization
- create a group.
- saml
- delete group
- microsoft
- authentication
- user lifecycle management.
- single group operations.
- list users
- app registration management.
- register a new application in azure ad.
- group membership.
- identity
- delete an azure ad user account.
- list directory users.
- microsoft entra
- delete user
- list group members.
- zero trust
- update azure ad user properties.
- list members of an azure ad group.
- create user
- get service principal
- list groups
- oauth
- delete an azure ad group.
- add a member to an azure ad group.
- access management
- get group
- list group members
- openid connect
- add a group member.
- list app registrations.
- list azure ad application registrations.
- delete a user.
- create group
- list service principals.
- list azure ad service principals.
- group management.
- azure active directory
- list service principals
- list azure ad users with optional filtering.
- get azure ad group details.
- single sign-on
- get a service principal by id.
- add group member
slug: identity-and-access
source_filename: identity-and-access.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Azure AD Identity and Access Management\"\n  description: \"Unified identity and access management workflow combining user lifecycle, group management, application registration, and service principal operations. Used by IT administrators and identity engineers to manage enterprise identity infrastructure.\"\n  tags:\n    - Microsoft Entra\n    - Identity\n    - Access Management\n    - Azure Active Directory\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      MICROSOFT_GRAPH_ACCESS_TOKEN: MICROSOFT_GRAPH_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: graph-identity\n      location: ./shared/microsoft-graph-identity.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: azure-ad-iam-api\n      description: \"Unified REST API for Azure AD identity and access management.\"\n      resources:\n        - path: /v1/users\n          name: users\n          description:\
  \ \"User lifecycle management.\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List directory users.\"\n              call: \"graph-identity.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-user\n              description: \"Create a new user.\"\n              call: \"graph-identity.create-user\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users/{userId}\n          name: user-detail\n          description: \"Single user operations.\"\n          operations:\n            - method: GET\n              name: get-user\n              description: \"Get user details.\"\n              call: \"graph-identity.get-user\"\n              with:\n                userId: \"rest.userId\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-user\n              description: \"Update user properties.\"\n              call: \"graph-identity.update-user\"\n              with:\n                userId: \"rest.userId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-user\n              description: \"Delete a user.\"\n              call: \"graph-identity.delete-user\"\n              with:\n                userId: \"rest.userId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/groups\n          name: groups\n          description: \"Group management.\"\n          operations:\n            - method: GET\n              name: list-groups\n              description: \"List groups.\"\n              call: \"graph-identity.list-groups\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-group\n              description: \"Create a group.\"\n              call: \"graph-identity.create-group\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/groups/{groupId}\n          name: group-detail\n          description: \"Single group operations.\"\n          operations:\n            - method: GET\n              name: get-group\n              description: \"Get group details.\"\n              call: \"graph-identity.get-group\"\n              with:\n                groupId: \"rest.groupId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/groups/{groupId}/members\n          name: group-members\n          description: \"Group membership.\"\n          operations:\n            - method: GET\n              name: list-group-members\n\
  \              description: \"List group members.\"\n              call: \"graph-identity.list-group-members\"\n              with:\n                groupId: \"rest.groupId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: add-group-member\n              description: \"Add a group member.\"\n              call: \"graph-identity.add-group-member\"\n              with:\n                groupId: \"rest.groupId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/applications\n          name: applications\n          description: \"App registration management.\"\n          operations:\n            - method: GET\n              name: list-applications\n              description: \"List app registrations.\"\n              call: \"graph-identity.list-applications\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n        - path: /v1/service-principals\n          name: service-principals\n          description: \"Service principal management.\"\n          operations:\n            - method: GET\n              name: list-service-principals\n              description: \"List service principals.\"\n              call: \"graph-identity.list-service-principals\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: azure-ad-iam-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Azure AD identity and access management.\"\n      tools:\n        - name: list-users\n          description: \"List Azure AD users with optional filtering.\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"graph-identity.list-users\"\n          outputParameters:\n            - type: object\n  \
  \            mapping: \"$.\"\n        - name: create-user\n          description: \"Create a new Azure AD user account.\"\n          hints:\n            readOnly: false\n          call: \"graph-identity.create-user\"\n          with:\n            display_name: \"tools.display_name\"\n            mail_nickname: \"tools.mail_nickname\"\n            user_principal_name: \"tools.user_principal_name\"\n            password: \"tools.password\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-user\n          description: \"Get Azure AD user details by ID or UPN.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"graph-identity.get-user\"\n          with:\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-user\n          description: \"Update Azure AD user properties.\"\n          hints:\n  \
  \          readOnly: false\n            idempotent: true\n          call: \"graph-identity.update-user\"\n          with:\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-user\n          description: \"Delete an Azure AD user account.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"graph-identity.delete-user\"\n          with:\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-user-memberships\n          description: \"List groups and roles a user belongs to.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"graph-identity.list-user-member-of\"\n          with:\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: object\n         \
  \     mapping: \"$.\"\n        - name: list-groups\n          description: \"List Azure AD groups with optional filtering.\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"graph-identity.list-groups\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-group\n          description: \"Create a new Azure AD group.\"\n          hints:\n            readOnly: false\n          call: \"graph-identity.create-group\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-group\n          description: \"Get Azure AD group details.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"graph-identity.get-group\"\n          with:\n            groupId: \"tools.groupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name:\
  \ delete-group\n          description: \"Delete an Azure AD group.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"graph-identity.delete-group\"\n          with:\n            groupId: \"tools.groupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-group-members\n          description: \"List members of an Azure AD group.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"graph-identity.list-group-members\"\n          with:\n            groupId: \"tools.groupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-group-member\n          description: \"Add a member to an Azure AD group.\"\n          hints:\n            readOnly: false\n          call: \"graph-identity.add-group-member\"\n          with:\n            groupId: \"tools.groupId\"\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-applications\n          description: \"List Azure AD application registrations.\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"graph-identity.list-applications\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-application\n          description: \"Register a new application in Azure AD.\"\n          hints:\n            readOnly: false\n          call: \"graph-identity.create-application\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-application\n          description: \"Get an application registration by ID.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"graph-identity.get-application\"\n          with:\n            applicationId:\
  \ \"tools.applicationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-service-principals\n          description: \"List Azure AD service principals.\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"graph-identity.list-service-principals\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-service-principal\n          description: \"Get a service principal by ID.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"graph-identity.get-service-principal\"\n          with:\n            servicePrincipalId: \"tools.servicePrincipalId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/azure-active-directory/refs/heads/main/capabilities/identity-and-access.yaml
tags:
- Microsoft Entra
- Identity
- Access Management
- Azure Active Directory
tools:
- description: List Azure AD users with optional filtering.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-users
- description: Create a new Azure AD user account.
  hints:
    readOnly: false
  name: create-user
- description: Get Azure AD user details by ID or UPN.
  hints:
    idempotent: true
    readOnly: true
  name: get-user
- description: Update Azure AD user properties.
  hints:
    idempotent: true
    readOnly: false
  name: update-user
- description: Delete an Azure AD user account.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-user
- description: List groups and roles a user belongs to.
  hints:
    idempotent: true
    readOnly: true
  name: list-user-memberships
- description: List Azure AD groups with optional filtering.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-groups
- description: Create a new Azure AD group.
  hints:
    readOnly: false
  name: create-group
- description: Get Azure AD group details.
  hints:
    idempotent: true
    readOnly: true
  name: get-group
- description: Delete an Azure AD group.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-group
- description: List members of an Azure AD group.
  hints:
    idempotent: true
    readOnly: true
  name: list-group-members
- description: Add a member to an Azure AD group.
  hints:
    readOnly: false
  name: add-group-member
- description: List Azure AD application registrations.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-applications
- description: Register a new application in Azure AD.
  hints:
    readOnly: false
  name: create-application
- description: Get an application registration by ID.
  hints:
    idempotent: true
    readOnly: true
  name: get-application
- description: List Azure AD service principals.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-service-principals
- description: Get a service principal by ID.
  hints:
    idempotent: true
    readOnly: true
  name: get-service-principal
---
