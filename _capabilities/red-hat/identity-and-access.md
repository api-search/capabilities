---
categories:
- identity-access
consumed_apis: []
description: Identity and access management workflow using Keycloak for managing realms, users, clients, roles, groups, and identity federation. Used by platform admins and security teams.
layout: capability
name: Red Hat Identity and Access
operations:
- description: List all realms.
  method: GET
  name: list-realms
  path: /v1/realms
- description: Get realm details.
  method: GET
  name: get-realm
  path: /v1/realms/{realm}
- description: List users.
  method: GET
  name: list-users
  path: /v1/realms/{realm}/users
- description: Create a user.
  method: POST
  name: create-user
  path: /v1/realms/{realm}/users
- description: List clients.
  method: GET
  name: list-clients
  path: /v1/realms/{realm}/clients
- description: List roles.
  method: GET
  name: list-roles
  path: /v1/realms/{realm}/roles
- description: List groups.
  method: GET
  name: list-groups
  path: /v1/realms/{realm}/groups
- description: List identity providers.
  method: GET
  name: list-identity-providers
  path: /v1/realms/{realm}/identity-providers
personas: []
provider_name: Red Hat
provider_slug: red-hat
search_terms:
- list roles in a realm.
- list clients.
- list groups in a realm.
- list identity providers
- identity
- delete session
- keycloak
- list realm roles
- red hat
- hybrid cloud
- create a user.
- realm clients.
- terminate a user session.
- create user
- list identity providers.
- get realm configuration details.
- get user details.
- cloud
- realm users.
- containers
- enterprise
- list clients
- kubernetes
- linux
- get realm details.
- register a new client application.
- open source
- delete user
- list client applications in a realm.
- list roles.
- list external identity providers.
- list all realms.
- realm roles.
- realm groups.
- list all keycloak realms.
- list realms
- specific realm.
- get realm
- keycloak realms.
- list users.
- access management
- list users in a realm.
- get user
- list users
- list groups.
- list groups
- identity providers.
- create client
- create a new user in a realm.
- delete a user from a realm.
- list roles
slug: identity-and-access
source_filename: identity-and-access.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Red Hat Identity and Access\n  description: Identity and access management workflow using Keycloak for managing realms, users, clients, roles, groups,\n    and identity federation. Used by platform admins and security teams.\n  tags:\n  - Red Hat\n  - Keycloak\n  - Identity\n  - Access Management\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    KEYCLOAK_BEARER_TOKEN: KEYCLOAK_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: keycloak-admin\n    baseUri: https://keycloak.example.com\n    description: Keycloak Admin REST API for identity and access management.\n    authentication:\n      type: bearer\n      token: '{{KEYCLOAK_BEARER_TOKEN}}'\n    resources:\n    - name: realms\n      path: /admin/realms\n      description: Manage Keycloak realms.\n      operations:\n      - name: list-realms\n        method: GET\n        description: List all realms.\n        inputParameters:\
  \ []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-realm\n        method: GET\n        description: Get a specific realm.\n        inputParameters:\n        - name: realm\n          in: path\n          type: string\n          required: true\n          description: Realm name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-realm\n        method: PUT\n        description: Update a realm configuration.\n        inputParameters:\n        - name: realm\n          in: path\n          type: string\n          required: true\n          description: Realm name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            displayName: '{{tools.displayName}}'\n    - name:\
  \ users\n      path: /admin/realms/{realm}/users\n      description: Manage users within a realm.\n      operations:\n      - name: list-users\n        method: GET\n        description: List all users in a realm.\n        inputParameters:\n        - name: realm\n          in: path\n          type: string\n          required: true\n          description: Realm name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create a new user in a realm.\n        inputParameters:\n        - name: realm\n          in: path\n          type: string\n          required: true\n          description: Realm name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            username: '{{tools.username}}'\n            email: '{{tools.email}}'\n\
  \            enabled: '{{tools.enabled}}'\n      - name: get-user\n        method: GET\n        description: Get a specific user.\n        inputParameters:\n        - name: realm\n          in: path\n          type: string\n          required: true\n          description: Realm name\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: User ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-user\n        method: PUT\n        description: Update a user.\n        inputParameters:\n        - name: realm\n          in: path\n          type: string\n          required: true\n          description: Realm name\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: User ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n        body:\n          type: json\n          data:\n            email: '{{tools.email}}'\n      - name: delete-user\n        method: DELETE\n        description: Delete a user.\n        inputParameters:\n        - name: realm\n          in: path\n          type: string\n          required: true\n          description: Realm name\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: User ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clients\n      path: /admin/realms/{realm}/clients\n      description: Manage client applications.\n      operations:\n      - name: list-clients\n        method: GET\n        description: List all clients in a realm.\n        inputParameters:\n        - name: realm\n          in: path\n          type: string\n          required: true\n          description: Realm name\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-client\n        method: POST\n        description: Register a new client application.\n        inputParameters:\n        - name: realm\n          in: path\n          type: string\n          required: true\n          description: Realm name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            clientId: '{{tools.clientId}}'\n            protocol: '{{tools.protocol}}'\n    - name: roles\n      path: /admin/realms/{realm}/roles\n      description: Manage realm-level roles.\n      operations:\n      - name: list-realm-roles\n        method: GET\n        description: List all realm roles.\n        inputParameters:\n        - name: realm\n          in: path\n          type: string\n          required: true\n\
  \          description: Realm name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-realm-role\n        method: POST\n        description: Create a new realm role.\n        inputParameters:\n        - name: realm\n          in: path\n          type: string\n          required: true\n          description: Realm name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n    - name: groups\n      path: /admin/realms/{realm}/groups\n      description: Manage user groups.\n      operations:\n      - name: list-groups\n        method: GET\n        description: List all groups in a realm.\n        inputParameters:\n        - name: realm\n          in: path\n          type: string\n          required: true\n          description: Realm\
  \ name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: identity-providers\n      path: /admin/realms/{realm}/identity-provider/instances\n      description: Manage external identity providers.\n      operations:\n      - name: list-identity-providers\n        method: GET\n        description: List all identity providers.\n        inputParameters:\n        - name: realm\n          in: path\n          type: string\n          required: true\n          description: Realm name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sessions\n      path: /admin/realms/{realm}/sessions\n      description: Manage active user sessions.\n      operations:\n      - name: delete-session\n        method: DELETE\n        description: Delete a specific session.\n        inputParameters:\n        - name: realm\n          in: path\n\
  \          type: string\n          required: true\n          description: Realm name\n        - name: session_id\n          in: path\n          type: string\n          required: true\n          description: Session ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: identity-and-access-api\n    description: Unified REST API for identity and access management.\n    resources:\n    - path: /v1/realms\n      name: realms\n      description: Keycloak realms.\n      operations:\n      - method: GET\n        name: list-realms\n        description: List all realms.\n        call: keycloak-admin.list-realms\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/realms/{realm}\n      name: realm-detail\n      description: Specific realm.\n      operations:\n      - method: GET\n        name: get-realm\n        description:\
  \ Get realm details.\n        call: keycloak-admin.get-realm\n        with:\n          realm: rest.realm\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/realms/{realm}/users\n      name: users\n      description: Realm users.\n      operations:\n      - method: GET\n        name: list-users\n        description: List users.\n        call: keycloak-admin.list-users\n        with:\n          realm: rest.realm\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-user\n        description: Create a user.\n        call: keycloak-admin.create-user\n        with:\n          realm: rest.realm\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/realms/{realm}/clients\n      name: clients\n      description: Realm clients.\n      operations:\n      - method: GET\n        name: list-clients\n        description: List clients.\n        call: keycloak-admin.list-clients\n\
  \        with:\n          realm: rest.realm\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/realms/{realm}/roles\n      name: roles\n      description: Realm roles.\n      operations:\n      - method: GET\n        name: list-roles\n        description: List roles.\n        call: keycloak-admin.list-realm-roles\n        with:\n          realm: rest.realm\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/realms/{realm}/groups\n      name: groups\n      description: Realm groups.\n      operations:\n      - method: GET\n        name: list-groups\n        description: List groups.\n        call: keycloak-admin.list-groups\n        with:\n          realm: rest.realm\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/realms/{realm}/identity-providers\n      name: identity-providers\n      description: Identity providers.\n      operations:\n      - method: GET\n       \
  \ name: list-identity-providers\n        description: List identity providers.\n        call: keycloak-admin.list-identity-providers\n        with:\n          realm: rest.realm\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9082\n    namespace: identity-and-access-mcp\n    transport: http\n    description: MCP server for AI-assisted identity and access management.\n    tools:\n    - name: list-realms\n      description: List all Keycloak realms.\n      hints:\n        readOnly: true\n      call: keycloak-admin.list-realms\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-realm\n      description: Get realm configuration details.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: keycloak-admin.get-realm\n      with:\n        realm: tools.realm\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-users\n      description: List users in a realm.\n\
  \      hints:\n        readOnly: true\n      call: keycloak-admin.list-users\n      with:\n        realm: tools.realm\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-user\n      description: Create a new user in a realm.\n      hints:\n        readOnly: false\n      call: keycloak-admin.create-user\n      with:\n        realm: tools.realm\n        username: tools.username\n        email: tools.email\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user\n      description: Get user details.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: keycloak-admin.get-user\n      with:\n        realm: tools.realm\n        user_id: tools.user_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-user\n      description: Delete a user from a realm.\n      hints:\n        readOnly: false\n        destructive: true\n      call: keycloak-admin.delete-user\n      with:\n\
  \        realm: tools.realm\n        user_id: tools.user_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-clients\n      description: List client applications in a realm.\n      hints:\n        readOnly: true\n      call: keycloak-admin.list-clients\n      with:\n        realm: tools.realm\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-client\n      description: Register a new client application.\n      hints:\n        readOnly: false\n      call: keycloak-admin.create-client\n      with:\n        realm: tools.realm\n        clientId: tools.clientId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-realm-roles\n      description: List roles in a realm.\n      hints:\n        readOnly: true\n      call: keycloak-admin.list-realm-roles\n      with:\n        realm: tools.realm\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-groups\n   \
  \   description: List groups in a realm.\n      hints:\n        readOnly: true\n      call: keycloak-admin.list-groups\n      with:\n        realm: tools.realm\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-identity-providers\n      description: List external identity providers.\n      hints:\n        readOnly: true\n      call: keycloak-admin.list-identity-providers\n      with:\n        realm: tools.realm\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-session\n      description: Terminate a user session.\n      hints:\n        readOnly: false\n        destructive: true\n      call: keycloak-admin.delete-session\n      with:\n        realm: tools.realm\n        session_id: tools.session_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/red-hat/refs/heads/main/capabilities/identity-and-access.yaml
tags:
- Red Hat
- Keycloak
- Identity
- Access Management
tools:
- description: List all Keycloak realms.
  hints:
    readOnly: true
  name: list-realms
- description: Get realm configuration details.
  hints:
    idempotent: true
    readOnly: true
  name: get-realm
- description: List users in a realm.
  hints:
    readOnly: true
  name: list-users
- description: Create a new user in a realm.
  hints:
    readOnly: false
  name: create-user
- description: Get user details.
  hints:
    idempotent: true
    readOnly: true
  name: get-user
- description: Delete a user from a realm.
  hints:
    destructive: true
    readOnly: false
  name: delete-user
- description: List client applications in a realm.
  hints:
    readOnly: true
  name: list-clients
- description: Register a new client application.
  hints:
    readOnly: false
  name: create-client
- description: List roles in a realm.
  hints:
    readOnly: true
  name: list-realm-roles
- description: List groups in a realm.
  hints:
    readOnly: true
  name: list-groups
- description: List external identity providers.
  hints:
    readOnly: true
  name: list-identity-providers
- description: Terminate a user session.
  hints:
    destructive: true
    readOnly: false
  name: delete-session
---
