---
api_specs:
- filename: user.yaml
  format: yaml
  label: snowflake-user
  slug: snowflake-user
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/user.yaml
- filename: role.yaml
  format: yaml
  label: snowflake-role
  slug: snowflake-role
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/role.yaml
- filename: grant.yaml
  format: yaml
  label: snowflake-grant
  slug: snowflake-grant
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/grant.yaml
- filename: database-role.yaml
  format: yaml
  label: snowflake-database-role
  slug: snowflake-database-role
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/database-role.yaml
- filename: network-policy.yaml
  format: yaml
  label: snowflake-network-policy
  slug: snowflake-network-policy
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/network-policy.yaml
- filename: account.yaml
  format: yaml
  label: snowflake-account
  slug: snowflake-account
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/account.yaml
- filename: managed-account.yaml
  format: yaml
  label: snowflake-managed-account
  slug: snowflake-managed-account
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/managed-account.yaml
categories:
- security
consumed_apis:
- snowflake-user
- snowflake-role
- snowflake-grant
- snowflake-database-role
- snowflake-network-policy
- snowflake-account
- snowflake-managed-account
description: Unified workflow for managing users, roles, grants, database roles, network policies, and account administration. Used by Platform Administrators and Security Engineers to govern access control and security posture.
layout: capability
name: Snowflake Security and Access
operations:
- description: List users
  method: GET
  name: list-users
  path: /v1/users
- description: Create a user
  method: POST
  name: create-user
  path: /v1/users
- description: List roles
  method: GET
  name: list-roles
  path: /v1/roles
- description: Create a role
  method: POST
  name: create-role
  path: /v1/roles
- description: Grant a privilege
  method: POST
  name: grant-privilege
  path: /v1/grants
- description: List grants
  method: GET
  name: list-grants
  path: /v1/grants
- description: List network policies
  method: GET
  name: list-network-policies
  path: /v1/network-policies
- description: Create a network policy
  method: POST
  name: create-network-policy
  path: /v1/network-policies
- description: List accounts
  method: GET
  name: list-accounts
  path: /v1/accounts
personas: []
provider_name: Snowflake
provider_slug: snowflake
search_terms:
- create a network policy
- create a new user
- delete a user
- list all roles
- sql
- list users
- administration
- fetch user details
- user management
- list roles
- delete user
- grant management
- list grants
- create database role
- grant a privilege to a role
- list grants to a role
- database
- create role
- revoke a privilege from a role
- grant privilege
- create network policy
- snowflake
- revoke privilege
- access control
- grant a privilege
- list accounts
- data sharing
- create a role
- list managed accounts
- create user
- account management
- list database roles
- create a database role
- security
- list network policies
- data lakes
- fetch user
- role management
- list all users
- create a new role
- data warehousing
- create a user
- network policy management
slug: security-and-access
source_filename: security-and-access.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Snowflake Security and Access\"\n  description: \"Unified workflow for managing users, roles, grants, database roles, network policies, and account administration. Used by Platform Administrators and Security Engineers to govern access control and security posture.\"\n  tags:\n    - Snowflake\n    - Security\n    - Access Control\n    - Administration\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      SNOWFLAKE_ACCOUNT_URL: SNOWFLAKE_ACCOUNT_URL\n      SNOWFLAKE_JWT_TOKEN: SNOWFLAKE_JWT_TOKEN\n\ncapability:\n  consumes:\n    - import: snowflake-user\n      location: ./shared/user.yaml\n    - import: snowflake-role\n      location: ./shared/role.yaml\n    - import: snowflake-grant\n      location: ./shared/grant.yaml\n    - import: snowflake-database-role\n      location: ./shared/database-role.yaml\n    - import: snowflake-network-policy\n      location: ./shared/network-policy.yaml\n\
  \    - import: snowflake-account\n      location: ./shared/account.yaml\n    - import: snowflake-managed-account\n      location: ./shared/managed-account.yaml\n\n  exposes:\n    - type: rest\n      port: 8083\n      namespace: snowflake-security-api\n      description: \"Unified REST API for Snowflake security and access management.\"\n      resources:\n        - path: /v1/users\n          name: users\n          description: \"User management\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List users\"\n              call: \"snowflake-user.list-users\"\n            - method: POST\n              name: create-user\n              description: \"Create a user\"\n              call: \"snowflake-user.create-user\"\n        - path: /v1/roles\n          name: roles\n          description: \"Role management\"\n          operations:\n            - method: GET\n              name: list-roles\n              description: \"List roles\"\
  \n              call: \"snowflake-role.list-roles\"\n            - method: POST\n              name: create-role\n              description: \"Create a role\"\n              call: \"snowflake-role.create-role\"\n        - path: /v1/grants\n          name: grants\n          description: \"Grant management\"\n          operations:\n            - method: POST\n              name: grant-privilege\n              description: \"Grant a privilege\"\n              call: \"snowflake-grant.grant-privilege\"\n            - method: GET\n              name: list-grants\n              description: \"List grants\"\n              call: \"snowflake-grant.list-grants-to\"\n        - path: /v1/network-policies\n          name: network-policies\n          description: \"Network policy management\"\n          operations:\n            - method: GET\n              name: list-network-policies\n              description: \"List network policies\"\n              call: \"snowflake-network-policy.list-network-policies\"\
  \n            - method: POST\n              name: create-network-policy\n              description: \"Create a network policy\"\n              call: \"snowflake-network-policy.create-network-policy\"\n        - path: /v1/accounts\n          name: accounts\n          description: \"Account management\"\n          operations:\n            - method: GET\n              name: list-accounts\n              description: \"List accounts\"\n              call: \"snowflake-account.list-accounts\"\n\n    - type: mcp\n      port: 9083\n      namespace: snowflake-security-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Snowflake security and access management.\"\n      tools:\n        - name: list-users\n          description: \"List all users\"\n          hints:\n            readOnly: true\n          call: \"snowflake-user.list-users\"\n        - name: create-user\n          description: \"Create a new user\"\n          hints:\n            readOnly: false\n          call:\
  \ \"snowflake-user.create-user\"\n        - name: fetch-user\n          description: \"Fetch user details\"\n          hints:\n            readOnly: true\n          call: \"snowflake-user.fetch-user\"\n        - name: delete-user\n          description: \"Delete a user\"\n          hints:\n            destructive: true\n          call: \"snowflake-user.delete-user\"\n        - name: list-roles\n          description: \"List all roles\"\n          hints:\n            readOnly: true\n          call: \"snowflake-role.list-roles\"\n        - name: create-role\n          description: \"Create a new role\"\n          hints:\n            readOnly: false\n          call: \"snowflake-role.create-role\"\n        - name: grant-privilege\n          description: \"Grant a privilege to a role\"\n          hints:\n            readOnly: false\n          call: \"snowflake-grant.grant-privilege\"\n        - name: revoke-privilege\n          description: \"Revoke a privilege from a role\"\n          hints:\n\
  \            readOnly: false\n          call: \"snowflake-grant.revoke-privilege\"\n        - name: list-grants\n          description: \"List grants to a role\"\n          hints:\n            readOnly: true\n          call: \"snowflake-grant.list-grants-to\"\n        - name: list-database-roles\n          description: \"List database roles\"\n          hints:\n            readOnly: true\n          call: \"snowflake-database-role.list-database-roles\"\n        - name: create-database-role\n          description: \"Create a database role\"\n          hints:\n            readOnly: false\n          call: \"snowflake-database-role.create-database-role\"\n        - name: list-network-policies\n          description: \"List network policies\"\n          hints:\n            readOnly: true\n          call: \"snowflake-network-policy.list-network-policies\"\n        - name: create-network-policy\n          description: \"Create a network policy\"\n          hints:\n            readOnly: false\n\
  \          call: \"snowflake-network-policy.create-network-policy\"\n        - name: list-accounts\n          description: \"List accounts\"\n          hints:\n            readOnly: true\n          call: \"snowflake-account.list-accounts\"\n        - name: list-managed-accounts\n          description: \"List managed accounts\"\n          hints:\n            readOnly: true\n          call: \"snowflake-managed-account.list-managed-accounts\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/capabilities/security-and-access.yaml
tags:
- Snowflake
- Security
- Access Control
- Administration
tools:
- description: List all users
  hints:
    readOnly: true
  name: list-users
- description: Create a new user
  hints:
    readOnly: false
  name: create-user
- description: Fetch user details
  hints:
    readOnly: true
  name: fetch-user
- description: Delete a user
  hints:
    destructive: true
  name: delete-user
- description: List all roles
  hints:
    readOnly: true
  name: list-roles
- description: Create a new role
  hints:
    readOnly: false
  name: create-role
- description: Grant a privilege to a role
  hints:
    readOnly: false
  name: grant-privilege
- description: Revoke a privilege from a role
  hints:
    readOnly: false
  name: revoke-privilege
- description: List grants to a role
  hints:
    readOnly: true
  name: list-grants
- description: List database roles
  hints:
    readOnly: true
  name: list-database-roles
- description: Create a database role
  hints:
    readOnly: false
  name: create-database-role
- description: List network policies
  hints:
    readOnly: true
  name: list-network-policies
- description: Create a network policy
  hints:
    readOnly: false
  name: create-network-policy
- description: List accounts
  hints:
    readOnly: true
  name: list-accounts
- description: List managed accounts
  hints:
    readOnly: true
  name: list-managed-accounts
---
