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
description: Workflow capability for managing identities in the Unkey platform. Identities group multiple API keys under a single external user or organization ID, enabling shared rate limits and analytics across all keys belonging to the same identity. Used by multi-tenant API providers and SaaS platforms.
layout: capability
name: Unkey Identity Management
operations:
- description: Create a new identity for grouping API keys
  method: POST
  name: create-identity
  path: /v1/identities
- description: List all identities
  method: GET
  name: list-identities
  path: /v1/identities
- description: Get an identity by ID
  method: GET
  name: get-identity
  path: /v1/identities/{identityId}
- description: Update identity metadata
  method: PUT
  name: update-identity
  path: /v1/identities/{identityId}
- description: Delete an identity
  method: DELETE
  name: delete-identity
  path: /v1/identities/{identityId}
personas: []
provider_name: Unkey
provider_slug: unkey
search_terms:
- access control
- identity collection operations
- single identity operations
- retrieve an identity by its id or external id
- create identity
- analytics
- rate limiting
- developer platform
- delete an identity
- get an identity by id
- authentication
- list identities
- delete an identity and disassociate its grouped keys
- unkey
- identity
- update metadata for an existing identity
- delete identity
- create a new identity to group api keys under a single external user or organization
- get identity
- list all identities in the workspace with pagination
- identities
- list all identities
- update identity metadata
- update identity
- multi-tenant
- create a new identity for grouping api keys
- api keys
slug: identity-management
source_filename: identity-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Unkey Identity Management\n  description: >-\n    Workflow capability for managing identities in the Unkey platform. Identities\n    group multiple API keys under a single external user or organization ID, enabling\n    shared rate limits and analytics across all keys belonging to the same identity.\n    Used by multi-tenant API providers and SaaS platforms.\n  tags:\n    - Unkey\n    - Identities\n    - Multi-Tenant\n    - Developer Platform\n    - Access Control\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      UNKEY_ROOT_KEY: UNKEY_ROOT_KEY\n\ncapability:\n  consumes:\n    - import: unkey\n      location: ./shared/unkey.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: unkey-identity-api\n      description: Unified REST API for Unkey identity lifecycle management.\n      resources:\n        - path: /v1/identities\n          name: identities\n         \
  \ description: Identity collection operations\n          operations:\n            - method: POST\n              name: create-identity\n              description: Create a new identity for grouping API keys\n              call: \"unkey.create-identity\"\n              with:\n                externalId: \"rest.externalId\"\n                meta: \"rest.meta\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-identities\n              description: List all identities\n              call: \"unkey.list-identities\"\n              with:\n                cursor: \"rest.cursor\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/identities/{identityId}\n          name: identity\n          description: Single identity operations\n          operations:\n            - method: GET\n    \
  \          name: get-identity\n              description: Get an identity by ID\n              call: \"unkey.get-identity\"\n              with:\n                identityId: \"rest.identityId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-identity\n              description: Update identity metadata\n              call: \"unkey.update-identity\"\n              with:\n                identityId: \"rest.identityId\"\n                meta: \"rest.meta\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-identity\n              description: Delete an identity\n              call: \"unkey.delete-identity\"\n              with:\n                identityId: \"rest.identityId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n\
  \    - type: mcp\n      port: 9092\n      namespace: unkey-identity-mcp\n      transport: http\n      description: MCP server for AI-assisted identity and multi-tenant API key management.\n      tools:\n        - name: create-identity\n          description: Create a new identity to group API keys under a single external user or organization\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"unkey.create-identity\"\n          with:\n            externalId: \"tools.externalId\"\n            meta: \"tools.meta\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-identity\n          description: Retrieve an identity by its ID or external ID\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unkey.get-identity\"\n          with:\n            identityId: \"tools.identityId\"\n          outputParameters:\n            - type: object\n           \
  \   mapping: \"$.\"\n        - name: list-identities\n          description: List all identities in the workspace with pagination\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unkey.list-identities\"\n          with:\n            cursor: \"tools.cursor\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-identity\n          description: Update metadata for an existing identity\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"unkey.update-identity\"\n          with:\n            identityId: \"tools.identityId\"\n            meta: \"tools.meta\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-identity\n          description: Delete an identity and disassociate its grouped keys\n          hints:\n       \
  \     readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"unkey.delete-identity\"\n          with:\n            identityId: \"tools.identityId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/unkey/refs/heads/main/capabilities/identity-management.yaml
tags:
- Unkey
- Identities
- Multi-Tenant
- Developer Platform
- Access Control
tools:
- description: Create a new identity to group API keys under a single external user or organization
  hints:
    destructive: false
    readOnly: false
  name: create-identity
- description: Retrieve an identity by its ID or external ID
  hints:
    openWorld: false
    readOnly: true
  name: get-identity
- description: List all identities in the workspace with pagination
  hints:
    openWorld: false
    readOnly: true
  name: list-identities
- description: Update metadata for an existing identity
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-identity
- description: Delete an identity and disassociate its grouped keys
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-identity
---
