---
categories: []
consumed_apis: []
description: The JetBrains Hub REST API provides programmatic access to Hub, the centralized authentication and authorization service for JetBrains tools. It allows management of users, groups, projects, roles, permissions, and OAuth 2.0 services. Hub serves as the identity provider for YouTrack, TeamCity, and other connected JetBrains services.
layout: capability
name: JetBrains Hub REST API
operations:
- description: JetBrains List Users
  method: GET
  name: listusers
  path: /users
- description: JetBrains Get User
  method: GET
  name: getuser
  path: /users/{userId}
- description: JetBrains List User Groups
  method: GET
  name: listusergroups
  path: /usergroups
- description: JetBrains List Projects
  method: GET
  name: listprojects
  path: /projects
- description: JetBrains List Roles
  method: GET
  name: listroles
  path: /roles
- description: JetBrains List Permissions
  method: GET
  name: listpermissions
  path: /permissions
- description: JetBrains List Services
  method: GET
  name: listservices
  path: /services
- description: JetBrains List OAuth2 Clients
  method: GET
  name: listoauth2clients
  path: /oauth2clients
personas: []
provider_name: JetBrains
provider_slug: jetbrains
search_terms:
- jetbrains get user
- jetbrains list roles
- jetbrains list permissions
- ci/cd
- jetbrains list user groups
- api
- jetbrains list services
- getuser
- ide
- jetbrains list projects
- developer tools
- jetbrains list oauth2 clients
- jetbrains list users
- jetbrains
- listusergroups
- listroles
- listpermissions
- listusers
- listoauth2clients
- listprojects
- listservices
slug: jetbrains-capability
source_filename: jetbrains-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: JetBrains Hub REST API\n  description: The JetBrains Hub REST API provides programmatic access to Hub, the centralized authentication and authorization\n    service for JetBrains tools. It allows management of users, groups, projects, roles, permissions, and OAuth 2.0 services.\n    Hub serves as the identity provider for YouTrack, TeamCity, and other connected JetBrains services.\n  tags:\n  - Jetbrains\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: jetbrains\n    baseUri: https://myinstance.youtrack.cloud/hub/api/rest\n    description: JetBrains Hub REST API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{JETBRAINS_TOKEN}}'\n    resources:\n    - name: users\n      path: /users\n      operations:\n      - name: listusers\n        method: GET\n        description: JetBrains List Users\n        inputParameters:\n        - name: fields\n         \
  \ in: query\n          type: string\n        - name: $skip\n          in: query\n          type: integer\n        - name: $top\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-userid\n      path: /users/{userId}\n      operations:\n      - name: getuser\n        method: GET\n        description: JetBrains Get User\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: usergroups\n      path: /usergroups\n      operations:\n      - name: listusergroups\n        method: GET\n        description: JetBrains List User Groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: projects\n      path: /projects\n      operations:\n      - name: listprojects\n        method: GET\n        description: JetBrains List Projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: roles\n      path: /roles\n      operations:\n      - name: listroles\n        method: GET\n        description: JetBrains List Roles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: permissions\n      path: /permissions\n      operations:\n      - name: listpermissions\n        method: GET\n        description: JetBrains List Permissions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services\n      path: /services\n      operations:\n      - name: listservices\n        method: GET\n        description: JetBrains\
  \ List Services\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oauth2clients\n      path: /oauth2clients\n      operations:\n      - name: listoauth2clients\n        method: GET\n        description: JetBrains List OAuth2 Clients\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: jetbrains-rest\n    description: REST adapter for JetBrains Hub REST API.\n    resources:\n    - path: /users\n      name: listusers\n      operations:\n      - method: GET\n        name: listusers\n        description: JetBrains List Users\n        call: jetbrains.listusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{userId}\n      name: getuser\n      operations:\n      - method: GET\n        name: getuser\n        description: JetBrains\
  \ Get User\n        call: jetbrains.getuser\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /usergroups\n      name: listusergroups\n      operations:\n      - method: GET\n        name: listusergroups\n        description: JetBrains List User Groups\n        call: jetbrains.listusergroups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects\n      name: listprojects\n      operations:\n      - method: GET\n        name: listprojects\n        description: JetBrains List Projects\n        call: jetbrains.listprojects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /roles\n      name: listroles\n      operations:\n      - method: GET\n        name: listroles\n        description: JetBrains List Roles\n        call: jetbrains.listroles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /permissions\n\
  \      name: listpermissions\n      operations:\n      - method: GET\n        name: listpermissions\n        description: JetBrains List Permissions\n        call: jetbrains.listpermissions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /services\n      name: listservices\n      operations:\n      - method: GET\n        name: listservices\n        description: JetBrains List Services\n        call: jetbrains.listservices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oauth2clients\n      name: listoauth2clients\n      operations:\n      - method: GET\n        name: listoauth2clients\n        description: JetBrains List OAuth2 Clients\n        call: jetbrains.listoauth2clients\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: jetbrains-mcp\n    transport: http\n    description: MCP adapter for JetBrains Hub REST API for AI agent use.\n \
  \   tools:\n    - name: listusers\n      description: JetBrains List Users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jetbrains.listusers\n      with:\n        fields: tools.fields\n        $skip: tools.$skip\n        $top: tools.$top\n      inputParameters:\n      - name: fields\n        type: string\n        description: fields\n      - name: $skip\n        type: integer\n        description: $skip\n      - name: $top\n        type: integer\n        description: $top\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getuser\n      description: JetBrains Get User\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jetbrains.getuser\n      with:\n        userId: tools.userId\n      inputParameters:\n      - name: userId\n        type: string\n        description: userId\n        required: true\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: listusergroups\n      description: JetBrains List User Groups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jetbrains.listusergroups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listprojects\n      description: JetBrains List Projects\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jetbrains.listprojects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listroles\n      description: JetBrains List Roles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jetbrains.listroles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpermissions\n      description: JetBrains List Permissions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jetbrains.listpermissions\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listservices\n      description: JetBrains List Services\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jetbrains.listservices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listoauth2clients\n      description: JetBrains List OAuth2 Clients\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jetbrains.listoauth2clients\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    JETBRAINS_TOKEN: JETBRAINS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/jetbrains/refs/heads/main/capabilities/jetbrains-capability.yaml
tags:
- Jetbrains
- API
tools:
- description: JetBrains List Users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusers
- description: JetBrains Get User
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: JetBrains List User Groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusergroups
- description: JetBrains List Projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojects
- description: JetBrains List Roles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listroles
- description: JetBrains List Permissions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpermissions
- description: JetBrains List Services
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listservices
- description: JetBrains List OAuth2 Clients
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listoauth2clients
---
