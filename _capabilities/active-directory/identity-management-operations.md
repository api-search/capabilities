---
categories:
- identity-access
consumed_apis: []
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
- get me
- group member management
- unified user, group, and application management for microsoft entra id
- registered and joined device management for compliant device access policies
- identity platform engineer managing application registrations, service principals, and oauth2 permission grants
- list group members
- service principals
- IT Administrator
- Identity Engineer
- directory services
- security professional monitoring identity risks, conditional access policies, and audit logs
- microsoft entra
- signed-in user profile
- list service principals in the microsoft entra tenant
- list microsoft entra id groups — security groups and microsoft 365 groups
- user lifecycle management
- create user
- get group
- identity management
- active directory
- individual group operations
- get details about a specific microsoft entra user by object id or userprincipalname
- create, update, and deactivate user accounts throughout the employee/guest lifecycle
- individual user operations
- get details about a specific microsoft entra application registration
- group management
- conditional access policy automation for zero-trust enforcement
- enterprise it admin managing user accounts, groups, device policies, and access management
- zero trust
- get the signed-in user's microsoft entra profile
- get signed-in user profile
- list application registrations in the microsoft entra tenant
- application registrations
- authentication
- authorization
- get user
- list users
- get user by id or upn
- create a new user account in microsoft entra id with required profile and password settings
- list microsoft entra id users with optional filtering by department, job title, or other attributes
- list groups
- list service principals
- list direct members of a microsoft entra group
- get application
- Security Analyst
- application registration and service principal lifecycle for zero-trust app governance
- periodic access reviews and identity risk remediation
- list applications
- create group
- get details about a specific microsoft entra group including type and membership settings
- group-based access control and app role assignment for resource permissions
- user management
slug: identity-management-operations
source_filename: identity-management-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Microsoft Active Directory Identity Management Operations\n  description: Unified workflow for managing Microsoft Entra ID (Active Directory) identity and access operations including\n    user lifecycle management, group management, and application registration. Used by IT administrators, identity engineers,\n    and security teams to automate identity governance and access management.\n  tags:\n  - Active Directory\n  - Identity Management\n  - Microsoft Entra\n  - User Management\n  - Zero Trust\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AD_ACCESS_TOKEN: AD_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: active-directory-users\n    baseUri: https://graph.microsoft.com/v1.0\n    description: Microsoft Graph Users API v1.0\n    authentication:\n      type: bearer\n      token: '{{AD_ACCESS_TOKEN}}'\n    resources:\n    - name: users\n      path: /users\n      description:\
  \ Microsoft Entra ID user accounts\n      operations:\n      - name: list-users\n        method: GET\n        description: List all users in the Microsoft Entra tenant with optional OData filtering\n        inputParameters:\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter expression\n        - name: $select\n          in: query\n          type: string\n          required: false\n          description: Properties to include in response\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create a new user in Microsoft Entra ID\n        inputParameters:\n        - name: displayName\n          in: body\n          type: string\n\
  \          required: true\n          description: Display name for the user\n        - name: userPrincipalName\n          in: body\n          type: string\n          required: true\n          description: UPN in alias@domain format\n        - name: mailNickname\n          in: body\n          type: string\n          required: true\n          description: Mail alias for the user\n        - name: accountEnabled\n          in: body\n          type: boolean\n          required: true\n          description: Whether the account is active\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user\n      path: /users/{userId}\n      description: Individual user operations\n      operations:\n      - name: get-user\n        method: GET\n        description: Get a specific user by object ID or UPN\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n\
  \          description: User object ID or userPrincipalName\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-user\n        method: PATCH\n        description: Update user properties\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User object ID or userPrincipalName\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-user\n        method: DELETE\n        description: Delete a user (soft-delete with 30-day recycle bin)\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User object ID or userPrincipalName\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: me\n      path: /me\n      description: Signed-in user profile\n      operations:\n      - name: get-me\n        method: GET\n        description: Get the signed-in user's profile (delegated auth only)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: active-directory-groups\n    baseUri: https://graph.microsoft.com/v1.0\n    description: Microsoft Graph Groups API v1.0\n    authentication:\n      type: bearer\n      token: '{{AD_ACCESS_TOKEN}}'\n    resources:\n    - name: groups\n      path: /groups\n      description: Microsoft Entra group registry\n      operations:\n      - name: list-groups\n        method: GET\n        description: List all groups with optional OData filtering\n        inputParameters:\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter (e.g.\
  \ groupTypes/any(c:c eq 'Unified'))\n        - name: $select\n          in: query\n          type: string\n          required: false\n          description: Properties to include\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Maximum results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-group\n        method: POST\n        description: Create a new security group or Microsoft 365 group\n        inputParameters:\n        - name: displayName\n          in: body\n          type: string\n          required: true\n        - name: mailEnabled\n          in: body\n          type: boolean\n          required: true\n        - name: mailNickname\n          in: body\n          type: string\n          required: true\n        - name: securityEnabled\n          in: body\n          type: boolean\n          required: true\n     \
  \   outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: group\n      path: /groups/{groupId}\n      description: Individual group operations\n      operations:\n      - name: get-group\n        method: GET\n        description: Get a specific group by object ID\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: group-members\n      path: /groups/{groupId}/members\n      description: Group member management\n      operations:\n      - name: list-group-members\n        method: GET\n        description: List direct members of a group\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: active-directory-applications\n    baseUri: https://graph.microsoft.com/v1.0\n    description: Microsoft Graph Applications API v1.0\n    authentication:\n      type: bearer\n      token: '{{AD_ACCESS_TOKEN}}'\n    resources:\n    - name: applications\n      path: /applications\n      description: Application registration management\n      operations:\n      - name: list-applications\n        method: GET\n        description: List all registered applications in the tenant\n        inputParameters:\n        - name: $filter\n          in: query\n          type: string\n          required: false\n        - name: $select\n          in: query\n          type: string\n          required: false\n        - name: $top\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: get-application\n        method: GET\n        description: Get an application registration by object ID\n        inputParameters:\n        - name: applicationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: service-principals\n      path: /servicePrincipals\n      description: Service principal management\n      operations:\n      - name: list-service-principals\n        method: GET\n        description: List all service principals in the tenant\n        inputParameters:\n        - name: $filter\n          in: query\n          type: string\n          required: false\n        - name: $top\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n   \
  \   - name: get-service-principal\n        method: GET\n        description: Get a service principal by object ID\n        inputParameters:\n        - name: servicePrincipalId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: active-directory-identity-api\n    description: Unified REST API for Microsoft Active Directory identity management operations.\n    resources:\n    - path: /v1/users\n      name: users\n      description: User lifecycle management\n      operations:\n      - method: GET\n        name: list-users\n        description: List users\n        call: active-directory-users.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-user\n        description: Create user\n        call: active-directory-users.create-user\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/{userId}\n      name: user\n      description: Individual user operations\n      operations:\n      - method: GET\n        name: get-user\n        description: Get user by ID or UPN\n        call: active-directory-users.get-user\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/me\n      name: me\n      description: Signed-in user profile\n      operations:\n      - method: GET\n        name: get-me\n        description: Get signed-in user profile\n        call: active-directory-users.get-me\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/groups\n      name: groups\n      description: Group management\n      operations:\n      - method: GET\n        name: list-groups\n        description: List groups\n        call: active-directory-groups.list-groups\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: POST\n        name: create-group\n        description: Create group\n        call: active-directory-groups.create-group\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/groups/{groupId}\n      name: group\n      description: Individual group operations\n      operations:\n      - method: GET\n        name: get-group\n        description: Get group\n        call: active-directory-groups.get-group\n        with:\n          groupId: rest.groupId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/groups/{groupId}/members\n      name: group-members\n      description: Group member management\n      operations:\n      - method: GET\n        name: list-group-members\n        description: List group members\n        call: active-directory-groups.list-group-members\n        with:\n          groupId: rest.groupId\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /v1/applications\n      name: applications\n      description: Application registrations\n      operations:\n      - method: GET\n        name: list-applications\n        description: List applications\n        call: active-directory-applications.list-applications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/servicePrincipals\n      name: service-principals\n      description: Service principals\n      operations:\n      - method: GET\n        name: list-service-principals\n        description: List service principals\n        call: active-directory-applications.list-service-principals\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: active-directory-identity-mcp\n    transport: http\n    description: MCP server for AI-assisted Microsoft Active Directory identity management.\n    tools:\n    - name: list-users\n      description:\
  \ List Microsoft Entra ID users with optional filtering by department, job title, or other attributes\n      hints:\n        readOnly: true\n        openWorld: true\n      call: active-directory-users.list-users\n      with:\n        $filter: tools.$filter\n        $select: tools.$select\n        $top: tools.$top\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user\n      description: Get details about a specific Microsoft Entra user by object ID or userPrincipalName\n      hints:\n        readOnly: true\n        idempotent: true\n      call: active-directory-users.get-user\n      with:\n        userId: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-user\n      description: Create a new user account in Microsoft Entra ID with required profile and password settings\n      hints:\n        readOnly: false\n        idempotent: false\n      call: active-directory-users.create-user\n      with:\n     \
  \   displayName: tools.displayName\n        userPrincipalName: tools.userPrincipalName\n        mailNickname: tools.mailNickname\n        accountEnabled: tools.accountEnabled\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-me\n      description: Get the signed-in user's Microsoft Entra profile\n      hints:\n        readOnly: true\n        idempotent: true\n      call: active-directory-users.get-me\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-groups\n      description: List Microsoft Entra ID groups — security groups and Microsoft 365 groups\n      hints:\n        readOnly: true\n        openWorld: true\n      call: active-directory-groups.list-groups\n      with:\n        $filter: tools.$filter\n        $select: tools.$select\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-group\n      description: Get details about a specific Microsoft Entra group including type and membership\
  \ settings\n      hints:\n        readOnly: true\n        idempotent: true\n      call: active-directory-groups.get-group\n      with:\n        groupId: tools.groupId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-group-members\n      description: List direct members of a Microsoft Entra group\n      hints:\n        readOnly: true\n        openWorld: true\n      call: active-directory-groups.list-group-members\n      with:\n        groupId: tools.groupId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-applications\n      description: List application registrations in the Microsoft Entra tenant\n      hints:\n        readOnly: true\n        openWorld: true\n      call: active-directory-applications.list-applications\n      with:\n        $filter: tools.$filter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-application\n      description: Get details about a specific Microsoft\
  \ Entra application registration\n      hints:\n        readOnly: true\n        idempotent: true\n      call: active-directory-applications.get-application\n      with:\n        applicationId: tools.applicationId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-service-principals\n      description: List service principals in the Microsoft Entra tenant\n      hints:\n        readOnly: true\n        openWorld: true\n      call: active-directory-applications.list-service-principals\n      with:\n        $filter: tools.$filter\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
