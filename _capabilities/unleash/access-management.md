---
categories: []
consumed_apis:
- unleash-admin
description: Workflow capability for managing access control in Unleash, including user management, API token lifecycle, service accounts, and personal access tokens. Used by platform admins and security teams to govern who can access Unleash and with what permissions.
layout: capability
name: Unleash Access Management
operations:
- description: List all users
  method: GET
  name: list-users
  path: /v1/users
- description: Create a new user
  method: POST
  name: create-user
  path: /v1/users
- description: List all API tokens
  method: GET
  name: list-tokens
  path: /v1/tokens
- description: Create a new API token
  method: POST
  name: create-token
  path: /v1/tokens
personas: []
provider_name: Unleash
provider_slug: unleash
search_terms:
- list tokens
- users
- access control
- create user
- list all api tokens in the unleash instance
- feature management
- administration
- open source
- create token
- create a new unleash user with email and role assignment
- a/b testing
- list all users in the unleash instance
- create api token
- list users
- create a new user
- api tokens
- user management
- unleash
- developer tools
- create a new api token for an unleash sdk or integration
- progressive delivery
- feature flags
- api token management
- list all api tokens
- create a new api token
- list all users
- list api tokens
slug: access-management
source_filename: access-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Unleash Access Management\n  description: >-\n    Workflow capability for managing access control in Unleash, including user management,\n    API token lifecycle, service accounts, and personal access tokens. Used by platform\n    admins and security teams to govern who can access Unleash and with what permissions.\n  tags:\n    - Unleash\n    - Access Control\n    - Users\n    - API Tokens\n    - Administration\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      UNLEASH_API_TOKEN: UNLEASH_API_TOKEN\n      UNLEASH_BASE_URL: UNLEASH_BASE_URL\n\ncapability:\n  consumes:\n    - import: unleash-admin\n      location: ./shared/unleash-admin.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: unleash-access-api\n      description: Unified REST API for Unleash access and token management.\n      resources:\n        - path: /v1/users\n          name: users\n        \
  \  description: User management\n          operations:\n            - method: GET\n              name: list-users\n              description: List all users\n              call: \"unleash-admin.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-user\n              description: Create a new user\n              call: \"unleash-admin.create-user\"\n              with:\n                email: \"rest.email\"\n                name: \"rest.name\"\n                rootRole: \"rest.rootRole\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tokens\n          name: api-tokens\n          description: API token management\n          operations:\n            - method: GET\n              name: list-tokens\n              description: List all API tokens\n              call: \"unleash-admin.list-tokens\"\n      \
  \        outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-token\n              description: Create a new API token\n              call: \"unleash-admin.create-token\"\n              with:\n                username: \"rest.username\"\n                type: \"rest.type\"\n                environment: \"rest.environment\"\n                project: \"rest.project\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: unleash-access-mcp\n      transport: http\n      description: MCP server for AI-assisted Unleash access management.\n      tools:\n        - name: list-users\n          description: List all users in the Unleash instance\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unleash-admin.list-users\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: create-user\n          description: Create a new Unleash user with email and role assignment\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"unleash-admin.create-user\"\n          with:\n            email: \"tools.email\"\n            name: \"tools.name\"\n            rootRole: \"tools.rootRole\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-api-tokens\n          description: List all API tokens in the Unleash instance\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unleash-admin.list-tokens\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-api-token\n          description: Create a new API token for an Unleash SDK or integration\n          hints:\n            readOnly: false\n            destructive: false\n\
  \          call: \"unleash-admin.create-token\"\n          with:\n            username: \"tools.username\"\n            type: \"tools.type\"\n            environment: \"tools.environment\"\n            project: \"tools.project\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/unleash/refs/heads/main/capabilities/access-management.yaml
tags:
- Unleash
- Access Control
- Users
- API Tokens
- Administration
tools:
- description: List all users in the Unleash instance
  hints:
    openWorld: false
    readOnly: true
  name: list-users
- description: Create a new Unleash user with email and role assignment
  hints:
    destructive: false
    readOnly: false
  name: create-user
- description: List all API tokens in the Unleash instance
  hints:
    openWorld: false
    readOnly: true
  name: list-api-tokens
- description: Create a new API token for an Unleash SDK or integration
  hints:
    destructive: false
    readOnly: false
  name: create-api-token
---
