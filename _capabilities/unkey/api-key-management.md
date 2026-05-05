---
api_specs:
- filename: unkey-openapi.yml
  format: yaml
  label: unkey
  slug: unkey
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/unkey/refs/heads/main/openapi/unkey-openapi.yml
categories: []
consumed_apis:
- unkey
description: Workflow capability for managing the full lifecycle of API keys using the Unkey platform. Covers creating, verifying, updating, rotating, and revoking keys, plus managing permissions and roles for fine-grained access control. Used by platform engineers and API providers to issue and govern access to their APIs.
layout: capability
name: Unkey API Key Management
operations:
- description: Create a new API namespace
  method: POST
  name: create-api
  path: /v1/apis
- description: Get an API namespace by ID
  method: GET
  name: get-api
  path: /v1/apis
- description: List all keys in an API namespace
  method: GET
  name: list-keys
  path: /v1/apis/{apiId}/keys
- description: Create a new API key
  method: POST
  name: create-key
  path: /v1/apis/{apiId}/keys
- description: Get an API key by ID
  method: GET
  name: get-key
  path: /v1/keys/{keyId}
- description: Update key settings
  method: PUT
  name: update-key
  path: /v1/keys/{keyId}
- description: Delete an API key
  method: DELETE
  name: delete-key
  path: /v1/keys/{keyId}
- description: Verify a key and return its validity and metadata
  method: POST
  name: verify-key
  path: /v1/keys/{keyId}/verify
- description: Rotate (reroll) a key to generate a new value
  method: POST
  name: reroll-key
  path: /v1/keys/{keyId}/reroll
- description: Add permissions to a key
  method: POST
  name: add-permissions
  path: /v1/keys/{keyId}/permissions
- description: Add roles to a key
  method: POST
  name: add-roles
  path: /v1/keys/{keyId}/roles
- description: Create a new permission
  method: POST
  name: create-permission
  path: /v1/permissions
- description: List all permissions
  method: GET
  name: list-permissions
  path: /v1/permissions
- description: Create a new role
  method: POST
  name: create-role
  path: /v1/roles
- description: List all roles
  method: GET
  name: list-roles
  path: /v1/roles
personas: []
provider_name: Unkey
provider_slug: unkey
search_terms:
- add permissions to a key
- update an api key's name, metadata, rate limits, or enabled status
- verify a key and return its validity and metadata
- create a new permission
- role management
- create role
- list keys
- verify an api key and return its validity, permissions, rate limit status
- reroll api key
- get api key
- retrieve full details of an api key by its id
- developer platform
- single key operations
- api keys
- update api key
- list all permissions
- rotate (reroll) a key to generate a new value
- rate limiting
- delete key
- create a new api key with optional prefix, name, roles, and rate limits
- analytics
- update key settings
- list roles
- key role management
- update key
- rotate an api key to generate a new key value while preserving settings
- keys within an api namespace
- create api
- create key
- add permissions
- api namespace management
- get an api namespace by id
- list all api keys within an api namespace
- create permission
- get api
- create a new role grouping multiple permissions
- reroll key
- permission management
- create api key
- list all keys in an api namespace
- list all roles
- list all roles in the workspace
- verify key
- add roles to an existing api key
- create api namespace
- access control
- add roles to a key
- create a new api key
- delete api key
- permanently delete one or more api keys
- get an api key by id
- add roles
- create a new api namespace
- create a new permission definition in the workspace
- verify an api key
- key permission management
- create a new api namespace in unkey for organizing keys
- add key permissions
- list permissions
- authentication
- add key roles
- get key
- verify api key
- list api keys
- unkey
- add permissions to an existing api key
- identity
- list all permissions in the workspace
- rotate an api key
- delete an api key
- create a new role
slug: api-key-management
source_filename: api-key-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Unkey API Key Management\n  description: >-\n    Workflow capability for managing the full lifecycle of API keys using the Unkey\n    platform. Covers creating, verifying, updating, rotating, and revoking keys, plus\n    managing permissions and roles for fine-grained access control. Used by platform\n    engineers and API providers to issue and govern access to their APIs.\n  tags:\n    - Unkey\n    - API Keys\n    - Access Control\n    - Developer Platform\n    - Authentication\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      UNKEY_ROOT_KEY: UNKEY_ROOT_KEY\n\ncapability:\n  consumes:\n    - import: unkey\n      location: ./shared/unkey.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: unkey-key-management-api\n      description: Unified REST API for Unkey API key lifecycle management.\n      resources:\n        - path: /v1/apis\n          name: apis\n\
  \          description: API namespace management\n          operations:\n            - method: POST\n              name: create-api\n              description: Create a new API namespace\n              call: \"unkey.create-api\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-api\n              description: Get an API namespace by ID\n              call: \"unkey.get-api\"\n              with:\n                apiId: \"rest.apiId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/apis/{apiId}/keys\n          name: api-keys\n          description: Keys within an API namespace\n          operations:\n            - method: GET\n              name: list-keys\n              description: List all keys in an API namespace\n              call: \"unkey.list-keys\"\
  \n              with:\n                apiId: \"rest.apiId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-key\n              description: Create a new API key\n              call: \"unkey.create-key\"\n              with:\n                apiId: \"rest.apiId\"\n                name: \"rest.name\"\n                externalId: \"rest.externalId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/keys/{keyId}\n          name: key\n          description: Single key operations\n          operations:\n            - method: GET\n              name: get-key\n              description: Get an API key by ID\n              call: \"unkey.get-key\"\n              with:\n                keyId: \"rest.keyId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n          \
  \  - method: PUT\n              name: update-key\n              description: Update key settings\n              call: \"unkey.update-key\"\n              with:\n                keyId: \"rest.keyId\"\n                name: \"rest.name\"\n                enabled: \"rest.enabled\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-key\n              description: Delete an API key\n              call: \"unkey.delete-key\"\n              with:\n                keyIds: \"rest.keyId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/keys/{keyId}/verify\n          name: key-verify\n          description: Verify an API key\n          operations:\n            - method: POST\n              name: verify-key\n              description: Verify a key and return its validity and metadata\n              call: \"unkey.verify-key\"\
  \n              with:\n                key: \"rest.key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/keys/{keyId}/reroll\n          name: key-reroll\n          description: Rotate an API key\n          operations:\n            - method: POST\n              name: reroll-key\n              description: Rotate (reroll) a key to generate a new value\n              call: \"unkey.reroll-key\"\n              with:\n                keyId: \"rest.keyId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/keys/{keyId}/permissions\n          name: key-permissions\n          description: Key permission management\n          operations:\n            - method: POST\n              name: add-permissions\n              description: Add permissions to a key\n              call: \"unkey.add-permissions\"\n              with:\n                keyId: \"rest.keyId\"\
  \n                permissions: \"rest.permissions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/keys/{keyId}/roles\n          name: key-roles\n          description: Key role management\n          operations:\n            - method: POST\n              name: add-roles\n              description: Add roles to a key\n              call: \"unkey.add-roles\"\n              with:\n                keyId: \"rest.keyId\"\n                roles: \"rest.roles\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/permissions\n          name: permissions\n          description: Permission management\n          operations:\n            - method: POST\n              name: create-permission\n              description: Create a new permission\n              call: \"unkey.create-permission\"\n              with:\n                name: \"rest.name\"\n     \
  \           description: \"rest.description\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-permissions\n              description: List all permissions\n              call: \"unkey.list-permissions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/roles\n          name: roles\n          description: Role management\n          operations:\n            - method: POST\n              name: create-role\n              description: Create a new role\n              call: \"unkey.create-role\"\n              with:\n                name: \"rest.name\"\n                description: \"rest.description\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-roles\n              description: List all roles\n              call:\
  \ \"unkey.list-roles\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: unkey-key-management-mcp\n      transport: http\n      description: MCP server for AI-assisted API key lifecycle management with Unkey.\n      tools:\n        - name: create-api-namespace\n          description: Create a new API namespace in Unkey for organizing keys\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"unkey.create-api\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-api-keys\n          description: List all API keys within an API namespace\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unkey.list-keys\"\n          with:\n            apiId: \"tools.apiId\"\n  \
  \        outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-api-key\n          description: Create a new API key with optional prefix, name, roles, and rate limits\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"unkey.create-key\"\n          with:\n            apiId: \"tools.apiId\"\n            prefix: \"tools.prefix\"\n            name: \"tools.name\"\n            externalId: \"tools.externalId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: verify-api-key\n          description: Verify an API key and return its validity, permissions, rate limit status\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unkey.verify-key\"\n          with:\n            key: \"tools.key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-api-key\n\
  \          description: Retrieve full details of an API key by its ID\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unkey.get-key\"\n          with:\n            keyId: \"tools.keyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-api-key\n          description: Update an API key's name, metadata, rate limits, or enabled status\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"unkey.update-key\"\n          with:\n            keyId: \"tools.keyId\"\n            name: \"tools.name\"\n            enabled: \"tools.enabled\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-api-key\n          description: Permanently delete one or more API keys\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent:\
  \ true\n          call: \"unkey.delete-key\"\n          with:\n            keyIds: \"tools.keyIds\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: reroll-api-key\n          description: Rotate an API key to generate a new key value while preserving settings\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"unkey.reroll-key\"\n          with:\n            keyId: \"tools.keyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-key-permissions\n          description: Add permissions to an existing API key\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"unkey.add-permissions\"\n          with:\n            keyId: \"tools.keyId\"\n            permissions: \"tools.permissions\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: add-key-roles\n          description: Add roles to an existing API key\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"unkey.add-roles\"\n          with:\n            keyId: \"tools.keyId\"\n            roles: \"tools.roles\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-permission\n          description: Create a new permission definition in the workspace\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"unkey.create-permission\"\n          with:\n            name: \"tools.name\"\n            description: \"tools.description\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-permissions\n          description: List all permissions in the workspace\n          hints:\n            readOnly: true\n            openWorld:\
  \ false\n          call: \"unkey.list-permissions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-role\n          description: Create a new role grouping multiple permissions\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"unkey.create-role\"\n          with:\n            name: \"tools.name\"\n            description: \"tools.description\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-roles\n          description: List all roles in the workspace\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unkey.list-roles\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/unkey/refs/heads/main/capabilities/api-key-management.yaml
tags:
- Unkey
- API Keys
- Access Control
- Developer Platform
- Authentication
tools:
- description: Create a new API namespace in Unkey for organizing keys
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-api-namespace
- description: List all API keys within an API namespace
  hints:
    openWorld: false
    readOnly: true
  name: list-api-keys
- description: Create a new API key with optional prefix, name, roles, and rate limits
  hints:
    destructive: false
    readOnly: false
  name: create-api-key
- description: Verify an API key and return its validity, permissions, rate limit status
  hints:
    openWorld: false
    readOnly: true
  name: verify-api-key
- description: Retrieve full details of an API key by its ID
  hints:
    openWorld: false
    readOnly: true
  name: get-api-key
- description: Update an API key's name, metadata, rate limits, or enabled status
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-api-key
- description: Permanently delete one or more API keys
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-api-key
- description: Rotate an API key to generate a new key value while preserving settings
  hints:
    destructive: false
    readOnly: false
  name: reroll-api-key
- description: Add permissions to an existing API key
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: add-key-permissions
- description: Add roles to an existing API key
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: add-key-roles
- description: Create a new permission definition in the workspace
  hints:
    destructive: false
    readOnly: false
  name: create-permission
- description: List all permissions in the workspace
  hints:
    openWorld: false
    readOnly: true
  name: list-permissions
- description: Create a new role grouping multiple permissions
  hints:
    destructive: false
    readOnly: false
  name: create-role
- description: List all roles in the workspace
  hints:
    openWorld: false
    readOnly: true
  name: list-roles
---
