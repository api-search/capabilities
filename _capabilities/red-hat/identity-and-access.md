---
categories:
- identity-access
consumed_apis:
- keycloak-admin
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
- get user
- list client applications in a realm.
- terminate a user session.
- realm groups.
- list realms
- list all keycloak realms.
- list users in a realm.
- linux
- list groups.
- kubernetes
- list all realms.
- create client
- realm users.
- realm clients.
- keycloak
- delete session
- list users.
- register a new client application.
- list realm roles
- list roles in a realm.
- get realm details.
- get realm
- enterprise
- list roles.
- list clients
- list groups in a realm.
- create user
- identity providers.
- get user details.
- delete user
- delete a user from a realm.
- list external identity providers.
- keycloak realms.
- create a user.
- identity
- create a new user in a realm.
- containers
- list groups
- red hat
- list identity providers
- access management
- cloud
- realm roles.
- open source
- list identity providers.
- specific realm.
- list clients.
- get realm configuration details.
- list users
- hybrid cloud
- list roles
slug: identity-and-access
source_filename: identity-and-access.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Red Hat Identity and Access\"\n  description: \"Identity and access management workflow using Keycloak for managing realms, users, clients, roles, groups, and identity federation. Used by platform admins and security teams.\"\n  tags:\n    - Red Hat\n    - Keycloak\n    - Identity\n    - Access Management\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      KEYCLOAK_BEARER_TOKEN: KEYCLOAK_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: keycloak-admin\n      location: ./shared/keycloak-admin.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: identity-and-access-api\n      description: \"Unified REST API for identity and access management.\"\n      resources:\n        - path: /v1/realms\n          name: realms\n          description: \"Keycloak realms.\"\n          operations:\n            - method: GET\n              name: list-realms\n             \
  \ description: \"List all realms.\"\n              call: \"keycloak-admin.list-realms\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/realms/{realm}\n          name: realm-detail\n          description: \"Specific realm.\"\n          operations:\n            - method: GET\n              name: get-realm\n              description: \"Get realm details.\"\n              call: \"keycloak-admin.get-realm\"\n              with:\n                realm: \"rest.realm\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/realms/{realm}/users\n          name: users\n          description: \"Realm users.\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List users.\"\n              call: \"keycloak-admin.list-users\"\n              with:\n                realm: \"rest.realm\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-user\n              description: \"Create a user.\"\n              call: \"keycloak-admin.create-user\"\n              with:\n                realm: \"rest.realm\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/realms/{realm}/clients\n          name: clients\n          description: \"Realm clients.\"\n          operations:\n            - method: GET\n              name: list-clients\n              description: \"List clients.\"\n              call: \"keycloak-admin.list-clients\"\n              with:\n                realm: \"rest.realm\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/realms/{realm}/roles\n          name: roles\n          description: \"Realm roles.\"\n          operations:\n            - method: GET\n\
  \              name: list-roles\n              description: \"List roles.\"\n              call: \"keycloak-admin.list-realm-roles\"\n              with:\n                realm: \"rest.realm\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/realms/{realm}/groups\n          name: groups\n          description: \"Realm groups.\"\n          operations:\n            - method: GET\n              name: list-groups\n              description: \"List groups.\"\n              call: \"keycloak-admin.list-groups\"\n              with:\n                realm: \"rest.realm\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/realms/{realm}/identity-providers\n          name: identity-providers\n          description: \"Identity providers.\"\n          operations:\n            - method: GET\n              name: list-identity-providers\n              description:\
  \ \"List identity providers.\"\n              call: \"keycloak-admin.list-identity-providers\"\n              with:\n                realm: \"rest.realm\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9082\n      namespace: identity-and-access-mcp\n      transport: http\n      description: \"MCP server for AI-assisted identity and access management.\"\n      tools:\n        - name: list-realms\n          description: \"List all Keycloak realms.\"\n          hints:\n            readOnly: true\n          call: \"keycloak-admin.list-realms\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-realm\n          description: \"Get realm configuration details.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"keycloak-admin.get-realm\"\n          with:\n            realm: \"tools.realm\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: list-users\n          description: \"List users in a realm.\"\n          hints:\n            readOnly: true\n          call: \"keycloak-admin.list-users\"\n          with:\n            realm: \"tools.realm\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-user\n          description: \"Create a new user in a realm.\"\n          hints:\n            readOnly: false\n          call: \"keycloak-admin.create-user\"\n          with:\n            realm: \"tools.realm\"\n            username: \"tools.username\"\n            email: \"tools.email\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-user\n          description: \"Get user details.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"keycloak-admin.get-user\"\n          with:\n            realm:\
  \ \"tools.realm\"\n            user_id: \"tools.user_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-user\n          description: \"Delete a user from a realm.\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"keycloak-admin.delete-user\"\n          with:\n            realm: \"tools.realm\"\n            user_id: \"tools.user_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-clients\n          description: \"List client applications in a realm.\"\n          hints:\n            readOnly: true\n          call: \"keycloak-admin.list-clients\"\n          with:\n            realm: \"tools.realm\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-client\n          description: \"Register a new client application.\"\n          hints:\n            readOnly:\
  \ false\n          call: \"keycloak-admin.create-client\"\n          with:\n            realm: \"tools.realm\"\n            clientId: \"tools.clientId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-realm-roles\n          description: \"List roles in a realm.\"\n          hints:\n            readOnly: true\n          call: \"keycloak-admin.list-realm-roles\"\n          with:\n            realm: \"tools.realm\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-groups\n          description: \"List groups in a realm.\"\n          hints:\n            readOnly: true\n          call: \"keycloak-admin.list-groups\"\n          with:\n            realm: \"tools.realm\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-identity-providers\n          description: \"List external identity providers.\"\n          hints:\n\
  \            readOnly: true\n          call: \"keycloak-admin.list-identity-providers\"\n          with:\n            realm: \"tools.realm\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-session\n          description: \"Terminate a user session.\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"keycloak-admin.delete-session\"\n          with:\n            realm: \"tools.realm\"\n            session_id: \"tools.session_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
