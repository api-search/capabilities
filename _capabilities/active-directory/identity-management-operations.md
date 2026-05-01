---
api_specs:
- filename: active-directory-users-openapi.yaml
  format: yaml
  label: active-directory-users
  slug: active-directory-users
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/active-directory/refs/heads/main/openapi/active-directory-users-openapi.yaml
- filename: active-directory-groups-openapi.yaml
  format: yaml
  label: active-directory-groups
  slug: active-directory-groups
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/active-directory/refs/heads/main/openapi/active-directory-groups-openapi.yaml
- filename: active-directory-applications-openapi.yaml
  format: yaml
  label: active-directory-applications
  slug: active-directory-applications
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/active-directory/refs/heads/main/openapi/active-directory-applications-openapi.yaml
categories:
- identity-access
consumed_apis:
- active-directory-users
- active-directory-groups
- active-directory-applications
description: Unified workflow for managing Microsoft Entra ID (Active Directory) identity and access operations including user lifecycle management, group management, and application registration. Used by IT administrators, identity engineers, and security teams to automate identity governance and access management.
layout: capability
name: Microsoft Active Directory Identity Management Operations
operations:
- description: List users
  method: GET
  name: list-users
  path: /v1/users
- description: Create user
  method: POST
  name: create-user
  path: /v1/users
- description: Get user by ID or UPN
  method: GET
  name: get-user
  path: /v1/users/{userId}
- description: Get signed-in user profile
  method: GET
  name: get-me
  path: /v1/me
- description: List groups
  method: GET
  name: list-groups
  path: /v1/groups
- description: Create group
  method: POST
  name: create-group
  path: /v1/groups
- description: Get group
  method: GET
  name: get-group
  path: /v1/groups/{groupId}
- description: List group members
  method: GET
  name: list-group-members
  path: /v1/groups/{groupId}/members
- description: List applications
  method: GET
  name: list-applications
  path: /v1/applications
- description: List service principals
  method: GET
  name: list-service-principals
  path: /v1/servicePrincipals
personas: []
provider_name: Microsoft Active Directory
provider_slug: active-directory
search_terms:
- create a new user account in microsoft entra id with required profile and password settings
- get user by id or upn
- application registrations
- group member management
- get user
- signed-in user profile
- get group
- periodic access reviews and identity risk remediation
- get signed-in user profile
- list microsoft entra id users with optional filtering by department, job title, or other attributes
- get the signed-in user's microsoft entra profile
- list microsoft entra id groups — security groups and microsoft 365 groups
- authorization
- enterprise it admin managing user accounts, groups, device policies, and access management
- list applications
- zero trust
- list groups
- list service principals in the microsoft entra tenant
- individual group operations
- get details about a specific microsoft entra user by object id or userprincipalname
- directory services
- conditional access policy automation for zero-trust enforcement
- group management
- Security Analyst
- group-based access control and app role assignment for resource permissions
- identity platform engineer managing application registrations, service principals, and oauth2 permission grants
- list service principals
- microsoft entra
- service principals
- user lifecycle management
- user management
- application registration and service principal lifecycle for zero-trust app governance
- IT Administrator
- security professional monitoring identity risks, conditional access policies, and audit logs
- list group members
- list application registrations in the microsoft entra tenant
- get details about a specific microsoft entra group including type and membership settings
- Identity Engineer
- list users
- get application
- get details about a specific microsoft entra application registration
- individual user operations
- list direct members of a microsoft entra group
- unified user, group, and application management for microsoft entra id
- create user
- get me
- registered and joined device management for compliant device access policies
- authentication
- create, update, and deactivate user accounts throughout the employee/guest lifecycle
- identity management
- active directory
- create group
slug: identity-management-operations
source_filename: identity-management-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Microsoft Active Directory Identity Management Operations\n  description: >-\n    Unified workflow for managing Microsoft Entra ID (Active Directory) identity and access\n    operations including user lifecycle management, group management, and application\n    registration. Used by IT administrators, identity engineers, and security teams to\n    automate identity governance and access management.\n  tags:\n    - Active Directory\n    - Identity Management\n    - Microsoft Entra\n    - User Management\n    - Zero Trust\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AD_ACCESS_TOKEN: AD_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: active-directory-users\n      location: ./shared/active-directory-users.yaml\n    - import: active-directory-groups\n      location: ./shared/active-directory-groups.yaml\n    - import: active-directory-applications\n      location: ./shared/active-directory-applications.yaml\n\
  \n  exposes:\n    - type: rest\n      port: 8080\n      namespace: active-directory-identity-api\n      description: Unified REST API for Microsoft Active Directory identity management operations.\n      resources:\n        - path: /v1/users\n          name: users\n          description: User lifecycle management\n          operations:\n            - method: GET\n              name: list-users\n              description: List users\n              call: \"active-directory-users.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-user\n              description: Create user\n              call: \"active-directory-users.create-user\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users/{userId}\n          name: user\n          description: Individual user operations\n          operations:\n          \
  \  - method: GET\n              name: get-user\n              description: Get user by ID or UPN\n              call: \"active-directory-users.get-user\"\n              with:\n                userId: \"rest.userId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/me\n          name: me\n          description: Signed-in user profile\n          operations:\n            - method: GET\n              name: get-me\n              description: Get signed-in user profile\n              call: \"active-directory-users.get-me\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/groups\n          name: groups\n          description: Group management\n          operations:\n            - method: GET\n              name: list-groups\n              description: List groups\n              call: \"active-directory-groups.list-groups\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-group\n              description: Create group\n              call: \"active-directory-groups.create-group\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/groups/{groupId}\n          name: group\n          description: Individual group operations\n          operations:\n            - method: GET\n              name: get-group\n              description: Get group\n              call: \"active-directory-groups.get-group\"\n              with:\n                groupId: \"rest.groupId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/groups/{groupId}/members\n          name: group-members\n          description: Group member management\n          operations:\n            - method: GET\n              name: list-group-members\n\
  \              description: List group members\n              call: \"active-directory-groups.list-group-members\"\n              with:\n                groupId: \"rest.groupId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/applications\n          name: applications\n          description: Application registrations\n          operations:\n            - method: GET\n              name: list-applications\n              description: List applications\n              call: \"active-directory-applications.list-applications\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/servicePrincipals\n          name: service-principals\n          description: Service principals\n          operations:\n            - method: GET\n              name: list-service-principals\n              description: List service principals\n              call: \"active-directory-applications.list-service-principals\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: active-directory-identity-mcp\n      transport: http\n      description: MCP server for AI-assisted Microsoft Active Directory identity management.\n      tools:\n        - name: list-users\n          description: List Microsoft Entra ID users with optional filtering by department, job title, or other attributes\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"active-directory-users.list-users\"\n          with:\n            $filter: \"tools.$filter\"\n            $select: \"tools.$select\"\n            $top: \"tools.$top\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-user\n          description: Get details about a specific Microsoft Entra user by object ID or userPrincipalName\n          hints:\n            readOnly: true\n\
  \            idempotent: true\n          call: \"active-directory-users.get-user\"\n          with:\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-user\n          description: Create a new user account in Microsoft Entra ID with required profile and password settings\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"active-directory-users.create-user\"\n          with:\n            displayName: \"tools.displayName\"\n            userPrincipalName: \"tools.userPrincipalName\"\n            mailNickname: \"tools.mailNickname\"\n            accountEnabled: \"tools.accountEnabled\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-me\n          description: Get the signed-in user's Microsoft Entra profile\n          hints:\n            readOnly: true\n            idempotent: true\n   \
  \       call: \"active-directory-users.get-me\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-groups\n          description: List Microsoft Entra ID groups — security groups and Microsoft 365 groups\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"active-directory-groups.list-groups\"\n          with:\n            $filter: \"tools.$filter\"\n            $select: \"tools.$select\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-group\n          description: Get details about a specific Microsoft Entra group including type and membership settings\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"active-directory-groups.get-group\"\n          with:\n            groupId: \"tools.groupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n \
  \       - name: list-group-members\n          description: List direct members of a Microsoft Entra group\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"active-directory-groups.list-group-members\"\n          with:\n            groupId: \"tools.groupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-applications\n          description: List application registrations in the Microsoft Entra tenant\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"active-directory-applications.list-applications\"\n          with:\n            $filter: \"tools.$filter\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-application\n          description: Get details about a specific Microsoft Entra application registration\n          hints:\n            readOnly: true\n            idempotent: true\n\
  \          call: \"active-directory-applications.get-application\"\n          with:\n            applicationId: \"tools.applicationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-service-principals\n          description: List service principals in the Microsoft Entra tenant\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"active-directory-applications.list-service-principals\"\n          with:\n            $filter: \"tools.$filter\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/active-directory/refs/heads/main/capabilities/identity-management-operations.yaml
tags:
- Active Directory
- Identity Management
- Microsoft Entra
- User Management
- Zero Trust
tools:
- description: List Microsoft Entra ID users with optional filtering by department, job title, or other attributes
  hints:
    openWorld: true
    readOnly: true
  name: list-users
- description: Get details about a specific Microsoft Entra user by object ID or userPrincipalName
  hints:
    idempotent: true
    readOnly: true
  name: get-user
- description: Create a new user account in Microsoft Entra ID with required profile and password settings
  hints:
    idempotent: false
    readOnly: false
  name: create-user
- description: Get the signed-in user's Microsoft Entra profile
  hints:
    idempotent: true
    readOnly: true
  name: get-me
- description: List Microsoft Entra ID groups — security groups and Microsoft 365 groups
  hints:
    openWorld: true
    readOnly: true
  name: list-groups
- description: Get details about a specific Microsoft Entra group including type and membership settings
  hints:
    idempotent: true
    readOnly: true
  name: get-group
- description: List direct members of a Microsoft Entra group
  hints:
    openWorld: true
    readOnly: true
  name: list-group-members
- description: List application registrations in the Microsoft Entra tenant
  hints:
    openWorld: true
    readOnly: true
  name: list-applications
- description: Get details about a specific Microsoft Entra application registration
  hints:
    idempotent: true
    readOnly: true
  name: get-application
- description: List service principals in the Microsoft Entra tenant
  hints:
    openWorld: true
    readOnly: true
  name: list-service-principals
---
