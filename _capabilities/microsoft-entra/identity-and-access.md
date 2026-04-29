---
categories:
- identity-access
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
- list all groups.
- azure ad
- get group details.
- update application properties.
- security
- individual application management.
- microsoft entra
- get service principal details.
- add group member
- list all users in the directory.
- update service principal
- remove group member
- register a new application.
- group membership management.
- delete application
- list all service principals.
- delete an application registration.
- create service principal
- update user
- update group
- delete a service principal.
- list groups
- group management.
- get user properties by id.
- list group members.
- directory management
- delete an application.
- access management
- get user details.
- update service principal properties.
- create a new group.
- list groups and roles a user belongs to.
- list users
- list members of a group.
- list service principals
- get user
- update application
- create application
- create a new user in the directory.
- individual service principal management.
- add a member to a group.
- user group membership.
- create user
- create a new user.
- create a new service principal.
- delete a user.
- list all groups in the directory.
- identity governance
- create group
- entra
- update group properties.
- update user properties.
- remove a member from a group.
- list all users in microsoft entra directory.
- individual user management.
- zero trust
- network security
- get service principal
- user account management.
- delete user
- list user group memberships.
- get group
- delete group
- delete a user from the directory.
- list all application registrations.
- individual group management.
- delete a group.
- identity
- list applications
- list user memberships
- get application details.
- authentication
- list group members
- list all applications.
- application registration management.
- update service principal.
- service principal management.
- delete service principal
- microsoft
- get application
slug: identity-and-access
source_filename: identity-and-access.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Microsoft Entra Identity and Access Management\"\n  description: \"Unified workflow for managing identity and access including users, groups, applications, and service principals in Microsoft Entra ID. Used by IT administrators and identity engineers.\"\n  tags:\n    - Microsoft Entra\n    - Identity\n    - Access Management\n    - Directory Management\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      MICROSOFT_ENTRA_ACCESS_TOKEN: MICROSOFT_ENTRA_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: entra-graph\n      location: ./shared/graph-identity.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: entra-iam-api\n      description: \"Unified REST API for Microsoft Entra identity and access management.\"\n      resources:\n        - path: /v1/users\n          name: users\n          description: \"User account management.\"\n          operations:\n  \
  \          - method: GET\n              name: list-users\n              description: \"List all users in the directory.\"\n              call: \"entra-graph.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-user\n              description: \"Create a new user.\"\n              call: \"entra-graph.create-user\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users/{id}\n          name: user-details\n          description: \"Individual user management.\"\n          operations:\n            - method: GET\n              name: get-user\n              description: \"Get user details.\"\n              call: \"entra-graph.get-user\"\n              with:\n                user-id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method:\
  \ PATCH\n              name: update-user\n              description: \"Update user properties.\"\n              call: \"entra-graph.update-user\"\n              with:\n                user-id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-user\n              description: \"Delete a user.\"\n              call: \"entra-graph.delete-user\"\n              with:\n                user-id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users/{id}/memberships\n          name: user-memberships\n          description: \"User group membership.\"\n          operations:\n            - method: GET\n              name: list-user-memberships\n              description: \"List user group memberships.\"\n              call: \"entra-graph.list-user-memberships\"\n              with:\n            \
  \    user-id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/groups\n          name: groups\n          description: \"Group management.\"\n          operations:\n            - method: GET\n              name: list-groups\n              description: \"List all groups.\"\n              call: \"entra-graph.list-groups\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-group\n              description: \"Create a new group.\"\n              call: \"entra-graph.create-group\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/groups/{id}\n          name: group-details\n          description: \"Individual group management.\"\n          operations:\n            - method: GET\n              name: get-group\n              description: \"\
  Get group details.\"\n              call: \"entra-graph.get-group\"\n              with:\n                group-id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-group\n              description: \"Update group properties.\"\n              call: \"entra-graph.update-group\"\n              with:\n                group-id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-group\n              description: \"Delete a group.\"\n              call: \"entra-graph.delete-group\"\n              with:\n                group-id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/groups/{id}/members\n          name: group-members\n          description: \"Group membership management.\"\
  \n          operations:\n            - method: GET\n              name: list-group-members\n              description: \"List group members.\"\n              call: \"entra-graph.list-group-members\"\n              with:\n                group-id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: add-group-member\n              description: \"Add a member to a group.\"\n              call: \"entra-graph.add-group-member\"\n              with:\n                group-id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/applications\n          name: applications\n          description: \"Application registration management.\"\n          operations:\n            - method: GET\n              name: list-applications\n              description: \"List all applications.\"\n              call: \"entra-graph.list-applications\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-application\n              description: \"Register a new application.\"\n              call: \"entra-graph.create-application\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/applications/{id}\n          name: application-details\n          description: \"Individual application management.\"\n          operations:\n            - method: GET\n              name: get-application\n              description: \"Get application details.\"\n              call: \"entra-graph.get-application\"\n              with:\n                application-id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-application\n              description: \"Update application\
  \ properties.\"\n              call: \"entra-graph.update-application\"\n              with:\n                application-id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-application\n              description: \"Delete an application.\"\n              call: \"entra-graph.delete-application\"\n              with:\n                application-id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/service-principals\n          name: service-principals\n          description: \"Service principal management.\"\n          operations:\n            - method: GET\n              name: list-service-principals\n              description: \"List all service principals.\"\n              call: \"entra-graph.list-service-principals\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n            - method: POST\n              name: create-service-principal\n              description: \"Create a new service principal.\"\n              call: \"entra-graph.create-service-principal\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/service-principals/{id}\n          name: service-principal-details\n          description: \"Individual service principal management.\"\n          operations:\n            - method: GET\n              name: get-service-principal\n              description: \"Get service principal details.\"\n              call: \"entra-graph.get-service-principal\"\n              with:\n                service-principal-id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-service-principal\n              description: \"Update service principal.\"\
  \n              call: \"entra-graph.update-service-principal\"\n              with:\n                service-principal-id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-service-principal\n              description: \"Delete a service principal.\"\n              call: \"entra-graph.delete-service-principal\"\n              with:\n                service-principal-id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: entra-iam-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Microsoft Entra identity and access management.\"\n      tools:\n        - name: list-users\n          description: \"List all users in Microsoft Entra directory.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call:\
  \ \"entra-graph.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-user\n          description: \"Create a new user in the directory.\"\n          hints:\n            readOnly: false\n          call: \"entra-graph.create-user\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-user\n          description: \"Get user properties by ID.\"\n          hints:\n            readOnly: true\n          call: \"entra-graph.get-user\"\n          with:\n            user-id: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-user\n          description: \"Update user properties.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"entra-graph.update-user\"\n          with:\n            user-id: \"tools.userId\"\n          outputParameters:\n       \
  \     - type: object\n              mapping: \"$.\"\n        - name: delete-user\n          description: \"Delete a user from the directory.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"entra-graph.delete-user\"\n          with:\n            user-id: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-user-memberships\n          description: \"List groups and roles a user belongs to.\"\n          hints:\n            readOnly: true\n          call: \"entra-graph.list-user-memberships\"\n          with:\n            user-id: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-groups\n          description: \"List all groups in the directory.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"entra-graph.list-groups\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: create-group\n          description: \"Create a new group.\"\n          hints:\n            readOnly: false\n          call: \"entra-graph.create-group\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-group\n          description: \"Get group details.\"\n          hints:\n            readOnly: true\n          call: \"entra-graph.get-group\"\n          with:\n            group-id: \"tools.groupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-group\n          description: \"Update group properties.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"entra-graph.update-group\"\n          with:\n            group-id: \"tools.groupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-group\n\
  \          description: \"Delete a group.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"entra-graph.delete-group\"\n          with:\n            group-id: \"tools.groupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-group-members\n          description: \"List members of a group.\"\n          hints:\n            readOnly: true\n          call: \"entra-graph.list-group-members\"\n          with:\n            group-id: \"tools.groupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-group-member\n          description: \"Add a member to a group.\"\n          hints:\n            readOnly: false\n          call: \"entra-graph.add-group-member\"\n          with:\n            group-id: \"tools.groupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: remove-group-member\n\
  \          description: \"Remove a member from a group.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"entra-graph.remove-group-member\"\n          with:\n            group-id: \"tools.groupId\"\n            member-id: \"tools.memberId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-applications\n          description: \"List all application registrations.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"entra-graph.list-applications\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-application\n          description: \"Register a new application.\"\n          hints:\n            readOnly: false\n          call: \"entra-graph.create-application\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-application\n\
  \          description: \"Get application details.\"\n          hints:\n            readOnly: true\n          call: \"entra-graph.get-application\"\n          with:\n            application-id: \"tools.applicationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-application\n          description: \"Update application properties.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"entra-graph.update-application\"\n          with:\n            application-id: \"tools.applicationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-application\n          description: \"Delete an application registration.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"entra-graph.delete-application\"\n          with:\n            application-id: \"tools.applicationId\"\n         \
  \ outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-service-principals\n          description: \"List all service principals.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"entra-graph.list-service-principals\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-service-principal\n          description: \"Create a new service principal.\"\n          hints:\n            readOnly: false\n          call: \"entra-graph.create-service-principal\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-service-principal\n          description: \"Get service principal details.\"\n          hints:\n            readOnly: true\n          call: \"entra-graph.get-service-principal\"\n          with:\n            service-principal-id: \"tools.servicePrincipalId\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: update-service-principal\n          description: \"Update service principal properties.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"entra-graph.update-service-principal\"\n          with:\n            service-principal-id: \"tools.servicePrincipalId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-service-principal\n          description: \"Delete a service principal.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"entra-graph.delete-service-principal\"\n          with:\n            service-principal-id: \"tools.servicePrincipalId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-entra/refs/heads/main/capabilities/identity-and-access.yaml
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
