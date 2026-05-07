---
categories:
- security
consumed_apis: []
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
- list all users in the snowflake account
- create a new role
- create network policy
- revoke privilege
- grant management
- create a role
- account management
- list accounts
- create a network policy
- revoke a privilege from a role
- fetch user details
- delete a user
- create a database role
- list database roles
- list all users
- access control
- delete user
- grant a privilege
- list grants
- create database role
- sql
- list users
- create role
- administration
- list network policies
- snowflake
- network policy management
- list managed accounts
- data sharing
- data lakes
- database
- user management
- grant privilege
- data warehousing
- create a user
- create user
- create a new user
- list grants to a role
- fetch user
- list all roles
- list roles
- fetch user details by name
- security
- grant a privilege to a role
- list grants for a role
- role management
slug: security-and-access
source_filename: security-and-access.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Snowflake Security and Access\n  description: Unified workflow for managing users, roles, grants, database roles, network policies, and account administration.\n    Used by Platform Administrators and Security Engineers to govern access control and security posture.\n  tags:\n  - Snowflake\n  - Security\n  - Access Control\n  - Administration\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SNOWFLAKE_ACCOUNT_URL: SNOWFLAKE_ACCOUNT_URL\n    SNOWFLAKE_JWT_TOKEN: SNOWFLAKE_JWT_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: snowflake-user\n    baseUri: '{{SNOWFLAKE_ACCOUNT_URL}}'\n    description: Snowflake User API\n    authentication:\n      type: bearer\n      token: '{{SNOWFLAKE_JWT_TOKEN}}'\n    resources:\n    - name: users\n      path: /api/v2/users\n      description: User resources\n      operations:\n      - name: list-users\n        method: GET\n        description: List\
  \ users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: fetch-user\n        method: GET\n        description: Fetch a user by name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-user\n        method: DELETE\n        description: Delete a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: snowflake-role\n    baseUri: '{{SNOWFLAKE_ACCOUNT_URL}}'\n    description: Snowflake Role API\n    authentication:\n      type: bearer\n      token: '{{SNOWFLAKE_JWT_TOKEN}}'\n    resources:\n\
  \    - name: roles\n      path: /api/v2/roles\n      description: Role resources\n      operations:\n      - name: list-roles\n        method: GET\n        description: List roles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-role\n        method: POST\n        description: Create a role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: fetch-role\n        method: GET\n        description: Fetch a role by name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-role\n        method: DELETE\n        description: Delete a role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: snowflake-grant\n\
  \    baseUri: '{{SNOWFLAKE_ACCOUNT_URL}}'\n    description: Snowflake Grant API\n    authentication:\n      type: bearer\n      token: '{{SNOWFLAKE_JWT_TOKEN}}'\n    resources:\n    - name: grants\n      path: /api/v2/grants\n      description: Grant resources\n      operations:\n      - name: grant-privilege\n        method: POST\n        description: Grant a privilege\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: revoke-privilege\n        method: POST\n        description: Revoke a privilege\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-grants-to\n        method: GET\n        description: List grants to a role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: snowflake-database-role\n\
  \    baseUri: '{{SNOWFLAKE_ACCOUNT_URL}}'\n    description: Snowflake Database Role API\n    authentication:\n      type: bearer\n      token: '{{SNOWFLAKE_JWT_TOKEN}}'\n    resources:\n    - name: database-roles\n      path: /api/v2/databases/{database}/database-roles\n      description: Database role resources\n      operations:\n      - name: list-database-roles\n        method: GET\n        description: List database roles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-database-role\n        method: POST\n        description: Create a database role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: fetch-database-role\n        method: GET\n        description: Fetch a database role by name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: delete-database-role\n        method: DELETE\n        description: Delete a database role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: snowflake-network-policy\n    baseUri: '{{SNOWFLAKE_ACCOUNT_URL}}'\n    description: Snowflake Network Policy API\n    authentication:\n      type: bearer\n      token: '{{SNOWFLAKE_JWT_TOKEN}}'\n    resources:\n    - name: network-policies\n      path: /api/v2/network-policies\n      description: Network policy resources\n      operations:\n      - name: list-network-policies\n        method: GET\n        description: List network policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-network-policy\n        method: POST\n        description: Create a network policy\n        outputRawFormat: json\n     \
  \   outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: fetch-network-policy\n        method: GET\n        description: Fetch a network policy by name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-network-policy\n        method: DELETE\n        description: Delete a network policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: snowflake-account\n    baseUri: '{{SNOWFLAKE_ACCOUNT_URL}}'\n    description: Snowflake Account API\n    authentication:\n      type: bearer\n      token: '{{SNOWFLAKE_JWT_TOKEN}}'\n    resources:\n    - name: accounts\n      path: /api/v2/accounts\n      description: Account resources\n      operations:\n      - name: list-accounts\n        method: GET\n        description: List accessible accounts\n \
  \       inputParameters:\n        - name: like\n          in: query\n          type: string\n          required: false\n          description: Filter by name pattern\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-account\n        method: POST\n        description: Create a new account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: delete-account\n        method: DELETE\n        description: Delete an account\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Account name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: undrop-account\n\
  \        method: POST\n        description: Undrop a deleted account\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Account name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: snowflake-managed-account\n    baseUri: '{{SNOWFLAKE_ACCOUNT_URL}}'\n    description: Snowflake Managed Account API\n    authentication:\n      type: bearer\n      token: '{{SNOWFLAKE_JWT_TOKEN}}'\n    resources:\n    - name: managed-accounts\n      path: /api/v2/managed-accounts\n      description: Managed account resources\n      operations:\n      - name: list-managed-accounts\n        method: GET\n        description: List managed accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-managed-account\n  \
  \      method: POST\n        description: Create a managed account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-managed-account\n        method: DELETE\n        description: Delete a managed account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8083\n    namespace: snowflake-security-api\n    description: Unified REST API for Snowflake security and access management.\n    resources:\n    - path: /v1/users\n      name: users\n      description: User management\n      operations:\n      - method: GET\n        name: list-users\n        description: List users\n        inputParameters:\n        - name: like\n          in: query\n          type: string\n          required: false\n          description: Filter users by name pattern (SQL LIKE)\n          mapping: $.like\n\
  \        outputParameters:\n        - name: users\n          type: array\n          description: List of user records\n          mapping: $.result\n        call: snowflake-user.list-users\n      - method: POST\n        name: create-user\n        description: Create a user\n        inputParameters:\n        - name: name\n          in: body\n          type: string\n          required: true\n          description: User name (unique identifier)\n          mapping: $.name\n        - name: login_name\n          in: body\n          type: string\n          required: false\n          description: Login name for the user\n          mapping: $.login_name\n        - name: email\n          in: body\n          type: string\n          required: false\n          description: Email address of the user\n          mapping: $.email\n        - name: default_role\n          in: body\n          type: string\n          required: false\n          description: Default role assigned to the user\n          mapping:\
  \ $.default_role\n        outputParameters:\n        - name: user\n          type: object\n          description: Created user record\n          mapping: $.result\n        call: snowflake-user.create-user\n    - path: /v1/roles\n      name: roles\n      description: Role management\n      operations:\n      - method: GET\n        name: list-roles\n        description: List roles\n        inputParameters:\n        - name: like\n          in: query\n          type: string\n          required: false\n          description: Filter roles by name pattern\n          mapping: $.like\n        outputParameters:\n        - name: roles\n          type: array\n          description: List of role records\n          mapping: $.result\n        call: snowflake-role.list-roles\n      - method: POST\n        name: create-role\n        description: Create a role\n        inputParameters:\n        - name: name\n          in: body\n          type: string\n          required: true\n          description: Role\
  \ name\n          mapping: $.name\n        - name: comment\n          in: body\n          type: string\n          required: false\n          description: Descriptive comment for the role\n          mapping: $.comment\n        outputParameters:\n        - name: role\n          type: object\n          description: Created role record\n          mapping: $.result\n        call: snowflake-role.create-role\n    - path: /v1/grants\n      name: grants\n      description: Grant management\n      operations:\n      - method: POST\n        name: grant-privilege\n        description: Grant a privilege\n        inputParameters:\n        - name: role_name\n          in: body\n          type: string\n          required: true\n          description: Target role receiving the grant\n          mapping: $.role_name\n        - name: privilege\n          in: body\n          type: string\n          required: true\n          description: Privilege being granted (e.g. SELECT, USAGE)\n          mapping: $.privilege\n\
  \        - name: securable_type\n          in: body\n          type: string\n          required: true\n          description: Type of securable (DATABASE, SCHEMA, TABLE, etc.)\n          mapping: $.securable_type\n        - name: securable_name\n          in: body\n          type: string\n          required: true\n          description: Fully qualified name of the securable\n          mapping: $.securable_name\n        outputParameters:\n        - name: grant\n          type: object\n          description: Grant record\n          mapping: $.result\n        call: snowflake-grant.grant-privilege\n      - method: GET\n        name: list-grants\n        description: List grants\n        inputParameters:\n        - name: role_name\n          in: query\n          type: string\n          required: true\n          description: Role whose grants are being listed\n          mapping: $.role_name\n        outputParameters:\n        - name: grants\n          type: array\n          description: List\
  \ of grants held by the role\n          mapping: $.result\n        call: snowflake-grant.list-grants-to\n    - path: /v1/network-policies\n      name: network-policies\n      description: Network policy management\n      operations:\n      - method: GET\n        name: list-network-policies\n        description: List network policies\n        inputParameters:\n        - name: like\n          in: query\n          type: string\n          required: false\n          description: Filter policies by name pattern\n          mapping: $.like\n        outputParameters:\n        - name: policies\n          type: array\n          description: List of network policy records\n          mapping: $.result\n        call: snowflake-network-policy.list-network-policies\n      - method: POST\n        name: create-network-policy\n        description: Create a network policy\n        inputParameters:\n        - name: name\n          in: body\n          type: string\n          required: true\n          description:\
  \ Network policy name\n          mapping: $.name\n        - name: allowed_ip_list\n          in: body\n          type: array\n          required: false\n          description: Allowed IP CIDR blocks\n          mapping: $.allowed_ip_list\n        - name: blocked_ip_list\n          in: body\n          type: array\n          required: false\n          description: Blocked IP CIDR blocks\n          mapping: $.blocked_ip_list\n        outputParameters:\n        - name: policy\n          type: object\n          description: Created network policy record\n          mapping: $.result\n        call: snowflake-network-policy.create-network-policy\n    - path: /v1/accounts\n      name: accounts\n      description: Account management\n      operations:\n      - method: GET\n        name: list-accounts\n        description: List accounts\n        inputParameters:\n        - name: like\n          in: query\n          type: string\n          required: false\n          description: Filter accounts by\
  \ name pattern\n          mapping: $.like\n        outputParameters:\n        - name: accounts\n          type: array\n          description: List of account records\n          mapping: $.result\n        call: snowflake-account.list-accounts\n  - type: mcp\n    port: 9083\n    namespace: snowflake-security-mcp\n    transport: http\n    description: MCP server (Streaming HTTP transport) for AI-assisted Snowflake security and access management.\n    tools:\n    - name: list-users\n      description: List all users in the Snowflake account\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      inputParameters:\n      - name: like\n        type: string\n        required: false\n        description: Filter users by name pattern\n        mapping: $.like\n      outputParameters:\n      - name: users\n        type: array\n        description: List of user records\n        mapping: $.result\n      call: snowflake-user.list-users\n    - name: create-user\n\
  \      description: Create a new user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      inputParameters:\n      - name: name\n        type: string\n        required: true\n        description: User name\n        mapping: $.name\n      - name: login_name\n        type: string\n        required: false\n        description: Login name\n        mapping: $.login_name\n      - name: email\n        type: string\n        required: false\n        description: Email address\n        mapping: $.email\n      - name: default_role\n        type: string\n        required: false\n        description: Default role for the user\n        mapping: $.default_role\n      outputParameters:\n      - name: user\n        type: object\n        description: Created user record\n        mapping: $.result\n      call: snowflake-user.create-user\n    - name: fetch-user\n      description: Fetch user details by name\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      inputParameters:\n      - name: name\n        type: string\n        required: true\n        description: User name to fetch\n        mapping: $.name\n      outputParameters:\n      - name: user\n        type: object\n        description: User record\n        mapping: $.result\n      call: snowflake-user.fetch-user\n    - name: delete-user\n      description: Delete a user\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      inputParameters:\n      - name: name\n        type: string\n        required: true\n        description: User name to delete\n        mapping: $.name\n      outputParameters:\n      - name: result\n        type: object\n        description: Deletion result\n        mapping: $.result\n      call: snowflake-user.delete-user\n    - name: list-roles\n      description: List all roles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      inputParameters:\n\
  \      - name: like\n        type: string\n        required: false\n        description: Filter roles by name pattern\n        mapping: $.like\n      outputParameters:\n      - name: roles\n        type: array\n        description: List of role records\n        mapping: $.result\n      call: snowflake-role.list-roles\n    - name: create-role\n      description: Create a new role\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      inputParameters:\n      - name: name\n        type: string\n        required: true\n        description: Role name\n        mapping: $.name\n      - name: comment\n        type: string\n        required: false\n        description: Descriptive comment\n        mapping: $.comment\n      outputParameters:\n      - name: role\n        type: object\n        description: Created role record\n        mapping: $.result\n      call: snowflake-role.create-role\n    - name: grant-privilege\n      description: Grant a privilege\
  \ to a role\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      inputParameters:\n      - name: role_name\n        type: string\n        required: true\n        description: Target role\n        mapping: $.role_name\n      - name: privilege\n        type: string\n        required: true\n        description: Privilege to grant\n        mapping: $.privilege\n      - name: securable_type\n        type: string\n        required: true\n        description: Securable type\n        mapping: $.securable_type\n      - name: securable_name\n        type: string\n        required: true\n        description: Securable name\n        mapping: $.securable_name\n      outputParameters:\n      - name: grant\n        type: object\n        description: Grant record\n        mapping: $.result\n      call: snowflake-grant.grant-privilege\n    - name: revoke-privilege\n      description: Revoke a privilege from a role\n      hints:\n        readOnly: false\n \
  \       destructive: true\n        idempotent: true\n      inputParameters:\n      - name: role_name\n        type: string\n        required: true\n        description: Target role\n        mapping: $.role_name\n      - name: privilege\n        type: string\n        required: true\n        description: Privilege to revoke\n        mapping: $.privilege\n      - name: securable_type\n        type: string\n        required: true\n        description: Securable type\n        mapping: $.securable_type\n      - name: securable_name\n        type: string\n        required: true\n        description: Securable name\n        mapping: $.securable_name\n      outputParameters:\n      - name: result\n        type: object\n        description: Revocation result\n        mapping: $.result\n      call: snowflake-grant.revoke-privilege\n    - name: list-grants\n      description: List grants to a role\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      inputParameters:\n\
  \      - name: role_name\n        type: string\n        required: true\n        description: Role whose grants are being listed\n        mapping: $.role_name\n      outputParameters:\n      - name: grants\n        type: array\n        description: Grants held by the role\n        mapping: $.result\n      call: snowflake-grant.list-grants-to\n    - name: list-database-roles\n      description: List database roles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      inputParameters:\n      - name: database\n        type: string\n        required: true\n        description: Database name\n        mapping: $.database\n      outputParameters:\n      - name: database_roles\n        type: array\n        description: List of database role records\n        mapping: $.result\n      call: snowflake-database-role.list-database-roles\n    - name: create-database-role\n      description: Create a database role\n      hints:\n        readOnly: false\n   \
  \     destructive: false\n        idempotent: false\n      inputParameters:\n      - name: database\n        type: string\n        required: true\n        description: Database name\n        mapping: $.database\n      - name: name\n        type: string\n        required: true\n        description: Database role name\n        mapping: $.name\n      outputParameters:\n      - name: database_role\n        type: object\n        description: Created database role record\n        mapping: $.result\n      call: snowflake-database-role.create-database-role\n    - name: list-network-policies\n      description: List network policies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      inputParameters:\n      - name: like\n        type: string\n        required: false\n        description: Filter policies by name pattern\n        mapping: $.like\n      outputParameters:\n      - name: policies\n        type: array\n        description: List of network\
  \ policies\n        mapping: $.result\n      call: snowflake-network-policy.list-network-policies\n    - name: create-network-policy\n      description: Create a network policy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      inputParameters:\n      - name: name\n        type: string\n        required: true\n        description: Policy name\n        mapping: $.name\n      - name: allowed_ip_list\n        type: array\n        required: false\n        description: Allowed IP CIDR blocks\n        mapping: $.allowed_ip_list\n      - name: blocked_ip_list\n        type: array\n        required: false\n        description: Blocked IP CIDR blocks\n        mapping: $.blocked_ip_list\n      outputParameters:\n      - name: policy\n        type: object\n        description: Created network policy record\n        mapping: $.result\n      call: snowflake-network-policy.create-network-policy\n    - name: list-accounts\n      description: List accounts\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      inputParameters:\n      - name: like\n        type: string\n        required: false\n        description: Filter accounts by name pattern\n        mapping: $.like\n      outputParameters:\n      - name: accounts\n        type: array\n        description: List of account records\n        mapping: $.result\n      call: snowflake-account.list-accounts\n    - name: list-managed-accounts\n      description: List managed accounts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      outputParameters:\n      - name: managed_accounts\n        type: array\n        description: List of managed account records\n        mapping: $.result\n      call: snowflake-managed-account.list-managed-accounts\n  - type: mcp\n    namespace: snowflake-security-mcp-stdio\n    transport: stdio\n    description: MCP server (stdio transport) for local IDE and CLI agents managing\
  \ Snowflake security and access.\n    tools:\n    - name: list-users\n      description: List all users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      inputParameters:\n      - name: like\n        type: string\n        required: false\n        description: Filter users by name pattern\n        mapping: $.like\n      outputParameters:\n      - name: users\n        type: array\n        description: List of user records\n        mapping: $.result\n      call: snowflake-user.list-users\n    - name: fetch-user\n      description: Fetch user details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      inputParameters:\n      - name: name\n        type: string\n        required: true\n        description: User name\n        mapping: $.name\n      outputParameters:\n      - name: user\n        type: object\n        description: User record\n        mapping: $.result\n      call: snowflake-user.fetch-user\n\
  \    - name: list-roles\n      description: List all roles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      outputParameters:\n      - name: roles\n        type: array\n        description: List of role records\n        mapping: $.result\n      call: snowflake-role.list-roles\n    - name: list-grants\n      description: List grants for a role\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      inputParameters:\n      - name: role_name\n        type: string\n        required: true\n        description: Role name\n        mapping: $.role_name\n      outputParameters:\n      - name: grants\n        type: array\n        description: Grants held by the role\n        mapping: $.result\n      call: snowflake-grant.list-grants-to\n    - name: list-network-policies\n      description: List network policies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n\
  \      outputParameters:\n      - name: policies\n        type: array\n        description: Network policies\n        mapping: $.result\n      call: snowflake-network-policy.list-network-policies\n    - name: list-accounts\n      description: List accounts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      outputParameters:\n      - name: accounts\n        type: array\n        description: Account records\n        mapping: $.result\n      call: snowflake-account.list-accounts\n  - type: skill\n    namespace: snowflake-security-skill\n    description: Agent Skills exposure of Snowflake security and access operations for skill-compatible AI clients.\n    skills:\n    - name: list-users\n      description: List all users in the Snowflake account\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      inputParameters:\n      - name: like\n        type: string\n        required: false\n        description:\
  \ Filter users by name pattern\n        mapping: $.like\n      outputParameters:\n      - name: users\n        type: array\n        description: List of user records\n        mapping: $.result\n      call: snowflake-user.list-users\n    - name: fetch-user\n      description: Fetch a specific user by name\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      inputParameters:\n      - name: name\n        type: string\n        required: true\n        description: User name\n        mapping: $.name\n      outputParameters:\n      - name: user\n        type: object\n        description: User record\n        mapping: $.result\n      call: snowflake-user.fetch-user\n    - name: list-roles\n      description: List all roles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      outputParameters:\n      - name: roles\n        type: array\n        description: Role records\n        mapping: $.result\n      call:\
  \ snowflake-role.list-roles\n    - name: grant-privilege\n      description: Grant a privilege to a role\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      inputParameters:\n      - name: role_name\n        type: string\n        required: true\n        description: Target role\n        mapping: $.role_name\n      - name: privilege\n        type: string\n        required: true\n        description: Privilege to grant\n        mapping: $.privilege\n      - name: securable_type\n        type: string\n        required: true\n        description: Securable type\n        mapping: $.securable_type\n      - name: securable_name\n        type: string\n        required: true\n        description: Securable name\n        mapping: $.securable_name\n      outputParameters:\n      - name: grant\n        type: object\n        description: Grant record\n        mapping: $.result\n      call: snowflake-grant.grant-privilege\n    - name: list-grants\n   \
  \   description: List grants held by a role\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      inputParameters:\n      - name: role_name\n        type: string\n        required: true\n        description: Role name\n        mapping: $.role_name\n      outputParameters:\n      - name: grants\n        type: array\n        description: Grants held by the role\n        mapping: $.result\n      call: snowflake-grant.list-grants-to\n    - name: list-network-policies\n      description: List network policies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      outputParameters:\n      - name: policies\n        type: array\n        description: Network policies\n        mapping: $.result\n      call: snowflake-network-policy.list-network-policies\n    - name: list-accounts\n      description: List accessible accounts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      outputParameters:\n      - name: accounts\n        type: array\n        description: Account records\n        mapping: $.result\n      call: snowflake-account.list-accounts\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/capabilities/security-and-access.yaml
tags:
- Snowflake
- Security
- Access Control
- Administration
tools:
- description: List all users in the Snowflake account
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-users
- description: Create a new user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-user
- description: Fetch user details by name
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: fetch-user
- description: Delete a user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-user
- description: List all roles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-roles
- description: Create a new role
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-role
- description: Grant a privilege to a role
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: grant-privilege
- description: Revoke a privilege from a role
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: revoke-privilege
- description: List grants to a role
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-grants
- description: List database roles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-database-roles
- description: Create a database role
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-database-role
- description: List network policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-network-policies
- description: Create a network policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-network-policy
- description: List accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-accounts
- description: List managed accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-managed-accounts
- description: List all users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-users
- description: Fetch user details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: fetch-user
- description: List all roles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-roles
- description: List grants for a role
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-grants
- description: List network policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-network-policies
- description: List accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-accounts
---
