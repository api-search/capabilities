---
categories: []
consumed_apis: []
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
- list all roles
- update an api key's name, metadata, rate limits, or enabled status
- add permissions to a key
- role management
- reroll api key
- rate limiting
- add roles to a key
- list all permissions in the workspace
- identity
- developer platform
- keys within an api namespace
- key permission management
- single key operations
- update key settings
- delete an api key
- verify an api key and return its validity, permissions, rate limit status
- analytics
- create a new permission
- add key permissions
- list all api keys within an api namespace
- add roles to an existing api key
- get api
- create api namespace
- create a new api namespace
- api keys
- get key
- add permissions
- get api key
- create a new permission definition in the workspace
- list all roles in the workspace
- list permissions
- delete key
- verify an api key
- verify api key
- create api
- verify a key and return its validity and metadata
- reroll key
- rotate (reroll) a key to generate a new value
- list api keys
- create api key
- delete api key
- permission management
- create permission
- add permissions to an existing api key
- create a new role grouping multiple permissions
- create a new api key with optional prefix, name, roles, and rate limits
- get an api key by id
- get an api namespace by id
- authentication
- add roles
- create a new api key
- create a new role
- list all permissions
- permanently delete one or more api keys
- access control
- api namespace management
- retrieve full details of an api key by its id
- add key roles
- create a new api namespace in unkey for organizing keys
- update api key
- unkey
- create role
- list roles
- create key
- list all keys in an api namespace
- update key
- key role management
- list keys
- rotate an api key to generate a new key value while preserving settings
- rotate an api key
- verify key
slug: api-key-management
source_filename: api-key-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Unkey API Key Management\n  description: Workflow capability for managing the full lifecycle of API keys using the Unkey platform. Covers creating,\n    verifying, updating, rotating, and revoking keys, plus managing permissions and roles for fine-grained access control.\n    Used by platform engineers and API providers to issue and govern access to their APIs.\n  tags:\n  - Unkey\n  - API Keys\n  - Access Control\n  - Developer Platform\n  - Authentication\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    UNKEY_ROOT_KEY: UNKEY_ROOT_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: unkey\n    baseUri: https://api.unkey.com\n    description: Unkey platform API for key management, rate limiting, and identity operations\n    authentication:\n      type: bearer\n      token: '{{UNKEY_ROOT_KEY}}'\n    resources:\n    - name: analytics\n      path: /v2\n      description: Analytics query operations\
  \ for key verification data\n      operations:\n      - name: get-verifications\n        method: POST\n        description: Query Key Verification Data\n        inputParameters:\n        - name: query\n          in: body\n          type: string\n          required: true\n          description: SQL SELECT query against key verification analytics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n    - name: apis\n      path: /v2\n      description: API namespace management operations\n      operations:\n      - name: create-api\n        method: POST\n        description: Create API Namespace\n        inputParameters:\n        - name: name\n          in: body\n          type: string\n          required: true\n          description: Name for the API namespace\n        outputRawFormat: json\n        outputParameters:\n    \
  \    - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: delete-api\n        method: POST\n        description: Delete API Namespace\n        inputParameters:\n        - name: apiId\n          in: body\n          type: string\n          required: true\n          description: ID of the API namespace to delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            apiId: '{{tools.apiId}}'\n      - name: get-api\n        method: POST\n        description: Get API Namespace\n        inputParameters:\n        - name: apiId\n          in: body\n          type: string\n          required: true\n          description: ID of the API namespace to retrieve\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n        body:\n          type: json\n          data:\n            apiId: '{{tools.apiId}}'\n      - name: list-keys\n        method: POST\n        description: List API Keys\n        inputParameters:\n        - name: apiId\n          in: body\n          type: string\n          required: true\n          description: ID of the API namespace to list keys for\n        - name: cursor\n          in: body\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: limit\n          in: body\n          type: integer\n          required: false\n          description: Maximum number of keys to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            apiId: '{{tools.apiId}}'\n            cursor: '{{tools.cursor}}'\n            limit: '{{tools.limit}}'\n    - name: keys\n     \
  \ path: /v2\n      description: API key lifecycle management operations\n      operations:\n      - name: create-key\n        method: POST\n        description: Create API Key\n        inputParameters:\n        - name: apiId\n          in: body\n          type: string\n          required: true\n          description: ID of the API namespace\n        - name: prefix\n          in: body\n          type: string\n          required: false\n          description: Key prefix (e.g. sk, pk, test)\n        - name: name\n          in: body\n          type: string\n          required: false\n          description: Human-readable name for the key\n        - name: externalId\n          in: body\n          type: string\n          required: false\n          description: External user or organization identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n           \
  \ apiId: '{{tools.apiId}}'\n            prefix: '{{tools.prefix}}'\n            name: '{{tools.name}}'\n            externalId: '{{tools.externalId}}'\n      - name: verify-key\n        method: POST\n        description: Verify API Key\n        inputParameters:\n        - name: apiId\n          in: body\n          type: string\n          required: false\n          description: ID of the API namespace\n        - name: key\n          in: body\n          type: string\n          required: true\n          description: The API key to verify\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            apiId: '{{tools.apiId}}'\n            key: '{{tools.key}}'\n      - name: get-key\n        method: POST\n        description: Get API Key\n        inputParameters:\n        - name: keyId\n          in: body\n          type: string\n          required: true\n      \
  \    description: ID of the key to retrieve\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            keyId: '{{tools.keyId}}'\n      - name: delete-key\n        method: POST\n        description: Delete API Keys\n        inputParameters:\n        - name: keyIds\n          in: body\n          type: array\n          required: true\n          description: List of key IDs to delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            keyIds: '{{tools.keyIds}}'\n      - name: update-key\n        method: POST\n        description: Update Key Settings\n        inputParameters:\n        - name: keyId\n          in: body\n          type: string\n          required: true\n          description: ID of the key to update\n  \
  \      - name: name\n          in: body\n          type: string\n          required: false\n          description: New name for the key\n        - name: enabled\n          in: body\n          type: boolean\n          required: false\n          description: Whether the key is enabled\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            keyId: '{{tools.keyId}}'\n            name: '{{tools.name}}'\n            enabled: '{{tools.enabled}}'\n      - name: reroll-key\n        method: POST\n        description: Reroll Key\n        inputParameters:\n        - name: keyId\n          in: body\n          type: string\n          required: true\n          description: ID of the key to reroll\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n     \
  \     data:\n            keyId: '{{tools.keyId}}'\n      - name: add-permissions\n        method: POST\n        description: Add Key Permissions\n        inputParameters:\n        - name: keyId\n          in: body\n          type: string\n          required: true\n          description: ID of the key\n        - name: permissions\n          in: body\n          type: array\n          required: true\n          description: Permissions to add to the key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            keyId: '{{tools.keyId}}'\n            permissions: '{{tools.permissions}}'\n      - name: add-roles\n        method: POST\n        description: Add Key Roles\n        inputParameters:\n        - name: keyId\n          in: body\n          type: string\n          required: true\n          description: ID of the key\n        - name: roles\n          in:\
  \ body\n          type: array\n          required: true\n          description: Roles to add to the key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            keyId: '{{tools.keyId}}'\n            roles: '{{tools.roles}}'\n      - name: whoami\n        method: POST\n        description: Get API Key by Hash\n        inputParameters:\n        - name: hash\n          in: body\n          type: string\n          required: true\n          description: Hash of the key to look up\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            hash: '{{tools.hash}}'\n    - name: identities\n      path: /v2\n      description: Identity management for grouping keys by external user or organization\n      operations:\n      - name: create-identity\n\
  \        method: POST\n        description: Create Identity\n        inputParameters:\n        - name: externalId\n          in: body\n          type: string\n          required: true\n          description: External identifier for the identity\n        - name: meta\n          in: body\n          type: object\n          required: false\n          description: Metadata to associate with the identity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            externalId: '{{tools.externalId}}'\n            meta: '{{tools.meta}}'\n      - name: get-identity\n        method: POST\n        description: Get Identity\n        inputParameters:\n        - name: identityId\n          in: body\n          type: string\n          required: false\n          description: ID of the identity\n        - name: externalId\n          in: body\n          type: string\n      \
  \    required: false\n          description: External ID of the identity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            identityId: '{{tools.identityId}}'\n      - name: list-identities\n        method: POST\n        description: List Identities\n        inputParameters:\n        - name: cursor\n          in: body\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: limit\n          in: body\n          type: integer\n          required: false\n          description: Maximum number of identities to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            cursor: '{{tools.cursor}}'\n            limit: '{{tools.limit}}'\n      - name: update-identity\n\
  \        method: POST\n        description: Update Identity\n        inputParameters:\n        - name: identityId\n          in: body\n          type: string\n          required: true\n          description: ID of the identity to update\n        - name: meta\n          in: body\n          type: object\n          required: false\n          description: Updated metadata\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            identityId: '{{tools.identityId}}'\n            meta: '{{tools.meta}}'\n      - name: delete-identity\n        method: POST\n        description: Delete Identity\n        inputParameters:\n        - name: identityId\n          in: body\n          type: string\n          required: true\n          description: ID of the identity to delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n        body:\n          type: json\n          data:\n            identityId: '{{tools.identityId}}'\n    - name: ratelimit\n      path: /v2\n      description: Standalone rate limiting operations\n      operations:\n      - name: limit\n        method: POST\n        description: Apply Rate Limiting\n        inputParameters:\n        - name: namespace\n          in: body\n          type: string\n          required: true\n          description: Namespace grouping rate limit rules\n        - name: identifier\n          in: body\n          type: string\n          required: true\n          description: Unique identifier being rate limited (user ID, IP, etc.)\n        - name: limit\n          in: body\n          type: integer\n          required: true\n          description: Maximum number of requests in the window\n        - name: duration\n          in: body\n          type: integer\n          required: true\n          description: Window duration in milliseconds\n\
  \        - name: cost\n          in: body\n          type: integer\n          required: false\n          description: Cost of this request (default 1)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            namespace: '{{tools.namespace}}'\n            identifier: '{{tools.identifier}}'\n            limit: '{{tools.limit}}'\n            duration: '{{tools.duration}}'\n            cost: '{{tools.cost}}'\n      - name: multi-limit\n        method: POST\n        description: Apply Multiple Rate Limit Checks\n        inputParameters:\n        - name: limits\n          in: body\n          type: array\n          required: true\n          description: Array of rate limit checks to apply\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n       \
  \   data:\n            limits: '{{tools.limits}}'\n      - name: set-override\n        method: POST\n        description: Set Ratelimit Override\n        inputParameters:\n        - name: namespaceId\n          in: body\n          type: string\n          required: false\n          description: ID of the namespace\n        - name: namespaceName\n          in: body\n          type: string\n          required: false\n          description: Name of the namespace\n        - name: identifier\n          in: body\n          type: string\n          required: true\n          description: Identifier to override\n        - name: limit\n          in: body\n          type: integer\n          required: true\n          description: Override limit\n        - name: duration\n          in: body\n          type: integer\n          required: true\n          description: Override window duration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n        body:\n          type: json\n          data:\n            identifier: '{{tools.identifier}}'\n            limit: '{{tools.limit}}'\n            duration: '{{tools.duration}}'\n      - name: get-override\n        method: POST\n        description: Get Ratelimit Override\n        inputParameters:\n        - name: namespaceId\n          in: body\n          type: string\n          required: false\n          description: ID of the namespace\n        - name: identifier\n          in: body\n          type: string\n          required: true\n          description: Identifier to get override for\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            identifier: '{{tools.identifier}}'\n      - name: list-overrides\n        method: POST\n        description: List Ratelimit Overrides\n        inputParameters:\n        - name: namespaceId\n\
  \          in: body\n          type: string\n          required: false\n          description: ID of the namespace\n        - name: cursor\n          in: body\n          type: string\n          required: false\n          description: Pagination cursor\n        - name: limit\n          in: body\n          type: integer\n          required: false\n          description: Maximum results to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            namespaceId: '{{tools.namespaceId}}'\n      - name: delete-override\n        method: POST\n        description: Delete Ratelimit Override\n        inputParameters:\n        - name: namespaceId\n          in: body\n          type: string\n          required: false\n          description: ID of the namespace\n        - name: identifier\n          in: body\n          type: string\n          required: true\n \
  \         description: Identifier to delete override for\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            identifier: '{{tools.identifier}}'\n    - name: permissions\n      path: /v2\n      description: Permission and role management operations\n      operations:\n      - name: create-permission\n        method: POST\n        description: Create Permission\n        inputParameters:\n        - name: name\n          in: body\n          type: string\n          required: true\n          description: Name of the permission\n        - name: description\n          in: body\n          type: string\n          required: false\n          description: Description of what the permission grants\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n\
  \          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n      - name: get-permission\n        method: POST\n        description: Get Permission\n        inputParameters:\n        - name: permissionId\n          in: body\n          type: string\n          required: true\n          description: ID of the permission to retrieve\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            permissionId: '{{tools.permissionId}}'\n      - name: list-permissions\n        method: POST\n        description: List Permissions\n        inputParameters:\n        - name: cursor\n          in: body\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n       \
  \ body:\n          type: json\n          data:\n            cursor: '{{tools.cursor}}'\n      - name: delete-permission\n        method: POST\n        description: Delete Permission\n        inputParameters:\n        - name: permissionId\n          in: body\n          type: string\n          required: true\n          description: ID of the permission to delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            permissionId: '{{tools.permissionId}}'\n      - name: create-role\n        method: POST\n        description: Create Role\n        inputParameters:\n        - name: name\n          in: body\n          type: string\n          required: true\n          description: Name of the role\n        - name: description\n          in: body\n          type: string\n          required: false\n          description: Description of the role\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n      - name: get-role\n        method: POST\n        description: Get Role\n        inputParameters:\n        - name: roleId\n          in: body\n          type: string\n          required: true\n          description: ID of the role to retrieve\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            roleId: '{{tools.roleId}}'\n      - name: list-roles\n        method: POST\n        description: List Roles\n        inputParameters:\n        - name: cursor\n          in: body\n          type: string\n          required: false\n          description: Pagination cursor\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            cursor: '{{tools.cursor}}'\n      - name: delete-role\n        method: POST\n        description: Delete Role\n        inputParameters:\n        - name: roleId\n          in: body\n          type: string\n          required: true\n          description: ID of the role to delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            roleId: '{{tools.roleId}}'\n    - name: liveness\n      path: /v2\n      description: Health check operations\n      operations:\n      - name: liveness\n        method: GET\n        description: Health Check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace:\
  \ unkey-key-management-api\n    description: Unified REST API for Unkey API key lifecycle management.\n    resources:\n    - path: /v1/apis\n      name: apis\n      description: API namespace management\n      operations:\n      - method: POST\n        name: create-api\n        description: Create a new API namespace\n        call: unkey.create-api\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-api\n        description: Get an API namespace by ID\n        call: unkey.get-api\n        with:\n          apiId: rest.apiId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/apis/{apiId}/keys\n      name: api-keys\n      description: Keys within an API namespace\n      operations:\n      - method: GET\n        name: list-keys\n        description: List all keys in an API namespace\n        call: unkey.list-keys\n        with:\n          apiId: rest.apiId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-key\n        description: Create a new API key\n        call: unkey.create-key\n        with:\n          apiId: rest.apiId\n          name: rest.name\n          externalId: rest.externalId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/keys/{keyId}\n      name: key\n      description: Single key operations\n      operations:\n      - method: GET\n        name: get-key\n        description: Get an API key by ID\n        call: unkey.get-key\n        with:\n          keyId: rest.keyId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-key\n        description: Update key settings\n        call: unkey.update-key\n        with:\n          keyId: rest.keyId\n          name: rest.name\n          enabled: rest.enabled\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n      - method: DELETE\n        name: delete-key\n        description: Delete an API key\n        call: unkey.delete-key\n        with:\n          keyIds: rest.keyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/keys/{keyId}/verify\n      name: key-verify\n      description: Verify an API key\n      operations:\n      - method: POST\n        name: verify-key\n        description: Verify a key and return its validity and metadata\n        call: unkey.verify-key\n        with:\n          key: rest.key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/keys/{keyId}/reroll\n      name: key-reroll\n      description: Rotate an API key\n      operations:\n      - method: POST\n        name: reroll-key\n        description: Rotate (reroll) a key to generate a new value\n        call: unkey.reroll-key\n        with:\n          keyId: rest.keyId\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /v1/keys/{keyId}/permissions\n      name: key-permissions\n      description: Key permission management\n      operations:\n      - method: POST\n        name: add-permissions\n        description: Add permissions to a key\n        call: unkey.add-permissions\n        with:\n          keyId: rest.keyId\n          permissions: rest.permissions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/keys/{keyId}/roles\n      name: key-roles\n      description: Key role management\n      operations:\n      - method: POST\n        name: add-roles\n        description: Add roles to a key\n        call: unkey.add-roles\n        with:\n          keyId: rest.keyId\n          roles: rest.roles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/permissions\n      name: permissions\n      description: Permission management\n      operations:\n      - method: POST\n        name:\
  \ create-permission\n        description: Create a new permission\n        call: unkey.create-permission\n        with:\n          name: rest.name\n          description: rest.description\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-permissions\n        description: List all permissions\n        call: unkey.list-permissions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/roles\n      name: roles\n      description: Role management\n      operations:\n      - method: POST\n        name: create-role\n        description: Create a new role\n        call: unkey.create-role\n        with:\n          name: rest.name\n          description: rest.description\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-roles\n        description: List all roles\n        call: unkey.list-roles\n        outputParameters:\n        -\
  \ type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: unkey-key-management-mcp\n    transport: http\n    description: MCP server for AI-assisted API key lifecycle management with Unkey.\n    tools:\n    - name: create-api-namespace\n      description: Create a new API namespace in Unkey for organizing keys\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: unkey.create-api\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-api-keys\n      description: List all API keys within an API namespace\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unkey.list-keys\n      with:\n        apiId: tools.apiId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-api-key\n      description: Create a new API key with optional prefix, name, roles, and rate limits\n      hints:\n   \
  \     readOnly: false\n        destructive: false\n      call: unkey.create-key\n      with:\n        apiId: tools.apiId\n        prefix: tools.prefix\n        name: tools.name\n        externalId: tools.externalId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: verify-api-key\n      description: Verify an API key and return its validity, permissions, rate limit status\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unkey.verify-key\n      with:\n        key: tools.key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api-key\n      description: Retrieve full details of an API key by its ID\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unkey.get-key\n      with:\n        keyId: tools.keyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-api-key\n      description: Update an API key's name, metadata, rate limits, or enabled\
  \ status\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: unkey.update-key\n      with:\n        keyId: tools.keyId\n        name: tools.name\n        enabled: tools.enabled\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-api-key\n      description: Permanently delete one or more API keys\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: unkey.delete-key\n      with:\n        keyIds: tools.keyIds\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: reroll-api-key\n      description: Rotate an API key to generate a new key value while preserving settings\n      hints:\n        readOnly: false\n        destructive: false\n      call: unkey.reroll-key\n      with:\n        keyId: tools.keyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-key-permissions\n      description: Add\
  \ permissions to an existing API key\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: unkey.add-permissions\n      with:\n        keyId: tools.keyId\n        permissions: tools.permissions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-key-roles\n      description: Add roles to an existing API key\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: unkey.add-roles\n      with:\n        keyId: tools.keyId\n        roles: tools.roles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-permission\n      description: Create a new permission definition in the workspace\n      hints:\n        readOnly: false\n        destructive: false\n      call: unkey.create-permission\n      with:\n        name: tools.name\n        description: tools.description\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: list-permissions\n      description: List all permissions in the workspace\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unkey.list-permissions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-role\n      description: Create a new role grouping multiple permissions\n      hints:\n        readOnly: false\n        destructive: false\n      call: unkey.create-role\n      with:\n        name: tools.name\n        description: tools.description\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-roles\n      description: List all roles in the workspace\n      hints:\n        readOnly: true\n        openWorld: false\n      call: unkey.list-roles\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
