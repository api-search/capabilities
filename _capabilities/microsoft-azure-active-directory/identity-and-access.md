---
categories: []
consumed_apis: []
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
provider_name: Microsoft Azure Active Directory
provider_slug: microsoft-azure-active-directory
search_terms:
- app registration management.
- get group details.
- microsoft entra
- create group
- register a new application in azure ad.
- get application
- update azure ad user properties.
- create a new user.
- list members of an azure ad group.
- saml
- list groups.
- list groups
- add a member to an azure ad group.
- update user
- list group members
- list user memberships
- create application
- authentication
- list service principals.
- list groups and roles a user belongs to.
- delete an azure ad user account.
- list group members.
- get azure ad user details by id or upn.
- list azure ad service principals.
- add a group member.
- delete user
- list azure ad groups with optional filtering.
- get group
- list azure ad users with optional filtering.
- list azure ad application registrations.
- identity
- list service principals
- azure active directory
- delete an azure ad group.
- microsoft
- openid connect
- group membership.
- list users
- scim
- create a new azure ad group.
- create a group.
- authorization
- service principal management.
- user lifecycle management.
- list directory users.
- get azure ad group details.
- get an application registration by id.
- access management
- get service principal
- list applications
- get user
- group management.
- create a new azure ad user account.
- zero trust
- create user
- get user details.
- single group operations.
- add group member
- delete a user.
- get a service principal by id.
- delete group
- single user operations.
- oauth
- single sign-on
- update user properties.
- list app registrations.
slug: identity-and-access
source_filename: identity-and-access.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Azure AD Identity and Access Management\n  description: Unified identity and access management workflow combining user lifecycle, group management, application registration,\n    and service principal operations. Used by IT administrators and identity engineers to manage enterprise identity infrastructure.\n  tags:\n  - Microsoft Entra\n  - Identity\n  - Access Management\n  - Azure Active Directory\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    MICROSOFT_GRAPH_ACCESS_TOKEN: MICROSOFT_GRAPH_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: graph-identity\n    baseUri: https://graph.microsoft.com/v1.0\n    description: Microsoft Graph Identity API for user, group, application, and service principal management.\n    authentication:\n      type: bearer\n      token: '{{MICROSOFT_GRAPH_ACCESS_TOKEN}}'\n    resources:\n    - name: users\n      path: /users\n      description:\
  \ Manage user accounts in Azure AD.\n      operations:\n      - name: list-users\n        method: GET\n        description: List all users in the directory.\n        inputParameters:\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Number of results to return.\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter expression.\n        - name: $select\n          in: query\n          type: string\n          required: false\n          description: Properties to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create a new user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n\
  \          data:\n            displayName: '{{tools.display_name}}'\n            mailNickname: '{{tools.mail_nickname}}'\n            userPrincipalName: '{{tools.user_principal_name}}'\n            accountEnabled: true\n            passwordProfile:\n              password: '{{tools.password}}'\n      - name: get-user\n        method: GET\n        description: Get a user by ID or UPN.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User ID or UPN.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-user\n        method: PATCH\n        description: Update user properties.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User ID or UPN.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: delete-user\n        method: DELETE\n        description: Delete a user.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User ID or UPN.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-user-member-of\n        method: GET\n        description: List groups and roles the user is a member of.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: User ID or UPN.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /groups\n      description: Manage groups in Azure AD.\n      operations:\n      - name: list-groups\n        method: GET\n  \
  \      description: List all groups.\n        inputParameters:\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-group\n        method: POST\n        description: Create a new group.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-group\n        method: GET\n        description: Get a group by ID.\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Group ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-group\n        method: PATCH\n        description: Update group properties.\n\
  \        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Group ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-group\n        method: DELETE\n        description: Delete a group.\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Group ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-group-members\n        method: GET\n        description: List members of a group.\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Group ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n     \
  \     type: object\n          value: $.\n      - name: add-group-member\n        method: POST\n        description: Add a member to a group.\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Group ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications\n      path: /applications\n      description: Manage application registrations.\n      operations:\n      - name: list-applications\n        method: GET\n        description: List application registrations.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-application\n        method: POST\n        description: Register a new application.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n      - name: get-application\n        method: GET\n        description: Get an application by ID.\n        inputParameters:\n        - name: applicationId\n          in: path\n          type: string\n          required: true\n          description: Application ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-application\n        method: DELETE\n        description: Delete an application registration.\n        inputParameters:\n        - name: applicationId\n          in: path\n          type: string\n          required: true\n          description: Application ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: service-principals\n      path: /servicePrincipals\n      description: Manage service principals.\n      operations:\n      - name: list-service-principals\n      \
  \  method: GET\n        description: List service principals.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-service-principal\n        method: POST\n        description: Create a service principal.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-service-principal\n        method: GET\n        description: Get a service principal by ID.\n        inputParameters:\n        - name: servicePrincipalId\n          in: path\n          type: string\n          required: true\n          description: Service principal ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-service-principal\n        method: DELETE\n        description: Delete a service principal.\n        inputParameters:\n        - name:\
  \ servicePrincipalId\n          in: path\n          type: string\n          required: true\n          description: Service principal ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: azure-ad-iam-api\n    description: Unified REST API for Azure AD identity and access management.\n    resources:\n    - path: /v1/users\n      name: users\n      description: User lifecycle management.\n      operations:\n      - method: GET\n        name: list-users\n        description: List directory users.\n        call: graph-identity.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-user\n        description: Create a new user.\n        call: graph-identity.create-user\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/{userId}\n      name:\
  \ user-detail\n      description: Single user operations.\n      operations:\n      - method: GET\n        name: get-user\n        description: Get user details.\n        call: graph-identity.get-user\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-user\n        description: Update user properties.\n        call: graph-identity.update-user\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-user\n        description: Delete a user.\n        call: graph-identity.delete-user\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/groups\n      name: groups\n      description: Group management.\n      operations:\n      - method: GET\n        name: list-groups\n        description:\
  \ List groups.\n        call: graph-identity.list-groups\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-group\n        description: Create a group.\n        call: graph-identity.create-group\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/groups/{groupId}\n      name: group-detail\n      description: Single group operations.\n      operations:\n      - method: GET\n        name: get-group\n        description: Get group details.\n        call: graph-identity.get-group\n        with:\n          groupId: rest.groupId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/groups/{groupId}/members\n      name: group-members\n      description: Group membership.\n      operations:\n      - method: GET\n        name: list-group-members\n        description: List group members.\n        call: graph-identity.list-group-members\n        with:\n  \
  \        groupId: rest.groupId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: add-group-member\n        description: Add a group member.\n        call: graph-identity.add-group-member\n        with:\n          groupId: rest.groupId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications\n      name: applications\n      description: App registration management.\n      operations:\n      - method: GET\n        name: list-applications\n        description: List app registrations.\n        call: graph-identity.list-applications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/service-principals\n      name: service-principals\n      description: Service principal management.\n      operations:\n      - method: GET\n        name: list-service-principals\n        description: List service principals.\n        call: graph-identity.list-service-principals\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: azure-ad-iam-mcp\n    transport: http\n    description: MCP server for AI-assisted Azure AD identity and access management.\n    tools:\n    - name: list-users\n      description: List Azure AD users with optional filtering.\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: graph-identity.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-user\n      description: Create a new Azure AD user account.\n      hints:\n        readOnly: false\n      call: graph-identity.create-user\n      with:\n        display_name: tools.display_name\n        mail_nickname: tools.mail_nickname\n        user_principal_name: tools.user_principal_name\n        password: tools.password\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user\n      description:\
  \ Get Azure AD user details by ID or UPN.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: graph-identity.get-user\n      with:\n        userId: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-user\n      description: Update Azure AD user properties.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: graph-identity.update-user\n      with:\n        userId: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-user\n      description: Delete an Azure AD user account.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: graph-identity.delete-user\n      with:\n        userId: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-user-memberships\n      description: List groups and roles a user belongs to.\n      hints:\n        readOnly: true\n\
  \        idempotent: true\n      call: graph-identity.list-user-member-of\n      with:\n        userId: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-groups\n      description: List Azure AD groups with optional filtering.\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: graph-identity.list-groups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-group\n      description: Create a new Azure AD group.\n      hints:\n        readOnly: false\n      call: graph-identity.create-group\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-group\n      description: Get Azure AD group details.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: graph-identity.get-group\n      with:\n        groupId: tools.groupId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-group\n\
  \      description: Delete an Azure AD group.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: graph-identity.delete-group\n      with:\n        groupId: tools.groupId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-group-members\n      description: List members of an Azure AD group.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: graph-identity.list-group-members\n      with:\n        groupId: tools.groupId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-group-member\n      description: Add a member to an Azure AD group.\n      hints:\n        readOnly: false\n      call: graph-identity.add-group-member\n      with:\n        groupId: tools.groupId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-applications\n      description: List Azure AD application registrations.\n      hints:\n       \
  \ readOnly: true\n        idempotent: true\n        openWorld: true\n      call: graph-identity.list-applications\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-application\n      description: Register a new application in Azure AD.\n      hints:\n        readOnly: false\n      call: graph-identity.create-application\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-application\n      description: Get an application registration by ID.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: graph-identity.get-application\n      with:\n        applicationId: tools.applicationId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-service-principals\n      description: List Azure AD service principals.\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: graph-identity.list-service-principals\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-service-principal\n      description: Get a service principal by ID.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: graph-identity.get-service-principal\n      with:\n        servicePrincipalId: tools.servicePrincipalId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-azure-active-directory/refs/heads/main/capabilities/identity-and-access.yaml
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
