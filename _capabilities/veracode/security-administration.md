---
api_specs:
- filename: veracode-identity-openapi.yml
  format: yaml
  label: veracode-identity
  slug: veracode-identity
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/veracode/refs/heads/main/openapi/veracode-identity-openapi.yml
categories: []
consumed_apis:
- veracode-identity
description: Unified workflow capability for Veracode platform administration. Enables security administrators to manage users, API service accounts, teams, business units, and roles across the Veracode organization. Designed for platform admins responsible for access control, onboarding, and organizational structure.
layout: capability
name: Veracode Security Administration
operations:
- description: List all users in the organization
  method: GET
  name: list-users
  path: /v1/users
- description: Create a new user or API service account
  method: POST
  name: create-user
  path: /v1/users
- description: Search users by term or type
  method: GET
  name: search-users
  path: /v1/users/search
- description: List all teams
  method: GET
  name: list-teams
  path: /v1/teams
- description: Create a new team
  method: POST
  name: create-team
  path: /v1/teams
- description: List all available roles
  method: GET
  name: list-roles
  path: /v1/roles
personas: []
provider_name: Veracode
provider_slug: veracode
search_terms:
- search veracode users by name, email, role, or type
- security testing
- list all teams
- users
- identity management
- access control
- create user
- search users by term or type
- list all available roles
- application security
- sca
- administration
- devsecops
- veracode
- sast
- list roles
- create a new user or api service account in the veracode organization
- list all teams in the veracode organization
- team management
- user account management
- search users
- list teams
- list all users in the veracode organization
- dast
- user search
- list users
- list all available roles for role-based access control
- create a new user or api service account
- create a new team in the veracode organization
- list all users in the organization
- create a new team
- role management
- create team
slug: security-administration
source_filename: security-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Veracode Security Administration\"\n  description: >-\n    Unified workflow capability for Veracode platform administration. Enables\n    security administrators to manage users, API service accounts, teams, business\n    units, and roles across the Veracode organization. Designed for platform admins\n    responsible for access control, onboarding, and organizational structure.\n  tags:\n    - Veracode\n    - Identity Management\n    - Access Control\n    - Users\n    - Administration\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      VERACODE_API_ID: VERACODE_API_ID\n      VERACODE_API_KEY: VERACODE_API_KEY\n\ncapability:\n  consumes:\n    - import: veracode-identity\n      location: ./shared/veracode-identity.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: veracode-admin-api\n      description: \"Unified REST API for Veracode platform administration.\"\
  \n      resources:\n        - path: /v1/users\n          name: users\n          description: \"User account management\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List all users in the organization\"\n              call: \"veracode-identity.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-user\n              description: \"Create a new user or API service account\"\n              call: \"veracode-identity.create-user\"\n              with:\n                email_address: \"rest.email_address\"\n                first_name: \"rest.first_name\"\n                last_name: \"rest.last_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/users/search\n          name: user-search\n          description: \"User search\"\n        \
  \  operations:\n            - method: GET\n              name: search-users\n              description: \"Search users by term or type\"\n              call: \"veracode-identity.search-users\"\n              with:\n                search_term: \"rest.search_term\"\n                user_type: \"rest.user_type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/teams\n          name: teams\n          description: \"Team management\"\n          operations:\n            - method: GET\n              name: list-teams\n              description: \"List all teams\"\n              call: \"veracode-identity.list-teams\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-team\n              description: \"Create a new team\"\n              call: \"veracode-identity.create-team\"\n              with:\n                team_name:\
  \ \"rest.team_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/roles\n          name: roles\n          description: \"Role management\"\n          operations:\n            - method: GET\n              name: list-roles\n              description: \"List all available roles\"\n              call: \"veracode-identity.list-roles\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: veracode-admin-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Veracode platform administration.\"\n      tools:\n        - name: list-users\n          description: \"List all users in the Veracode organization\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"veracode-identity.list-users\"\n          outputParameters:\n            - type: object\n         \
  \     mapping: \"$.\"\n\n        - name: search-users\n          description: \"Search Veracode users by name, email, role, or type\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"veracode-identity.search-users\"\n          with:\n            search_term: \"tools.search_term\"\n            user_type: \"tools.user_type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-user\n          description: \"Create a new user or API service account in the Veracode organization\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"veracode-identity.create-user\"\n          with:\n            email_address: \"tools.email_address\"\n            first_name: \"tools.first_name\"\n            last_name: \"tools.last_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-teams\n     \
  \     description: \"List all teams in the Veracode organization\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"veracode-identity.list-teams\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-team\n          description: \"Create a new team in the Veracode organization\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"veracode-identity.create-team\"\n          with:\n            team_name: \"tools.team_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-roles\n          description: \"List all available roles for role-based access control\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"veracode-identity.list-roles\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/veracode/refs/heads/main/capabilities/security-administration.yaml
tags:
- Veracode
- Identity Management
- Access Control
- Users
- Administration
tools:
- description: List all users in the Veracode organization
  hints:
    idempotent: true
    readOnly: true
  name: list-users
- description: Search Veracode users by name, email, role, or type
  hints:
    openWorld: true
    readOnly: true
  name: search-users
- description: Create a new user or API service account in the Veracode organization
  hints:
    idempotent: false
    readOnly: false
  name: create-user
- description: List all teams in the Veracode organization
  hints:
    idempotent: true
    readOnly: true
  name: list-teams
- description: Create a new team in the Veracode organization
  hints:
    idempotent: false
    readOnly: false
  name: create-team
- description: List all available roles for role-based access control
  hints:
    idempotent: true
    readOnly: true
  name: list-roles
---
