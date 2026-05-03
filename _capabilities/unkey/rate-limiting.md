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
description: Workflow capability for standalone rate limiting using the Unkey platform. Enables platform engineers, backend developers, and API teams to protect any endpoint from abuse with global rate limiting, per-identifier overrides, and multi-limit batch checks — without requiring API key management.
layout: capability
name: Unkey Rate Limiting
operations:
- description: Apply rate limiting check for a single identifier
  method: POST
  name: limit
  path: /v1/ratelimits
- description: Apply multiple rate limit checks in one request
  method: POST
  name: multi-limit
  path: /v1/ratelimits/multi
- description: List all rate limit overrides for a namespace
  method: GET
  name: list-overrides
  path: /v1/ratelimits/overrides
- description: Set a rate limit override for a specific identifier
  method: PUT
  name: set-override
  path: /v1/ratelimits/overrides
- description: Get rate limit override for an identifier
  method: GET
  name: get-override
  path: /v1/ratelimits/overrides/{identifier}
- description: Delete a rate limit override
  method: DELETE
  name: delete-override
  path: /v1/ratelimits/overrides/{identifier}
personas: []
provider_name: Unkey
provider_slug: unkey
search_terms:
- list overrides
- list all rate limit overrides for a namespace
- apply multi rate limit
- access control
- set a custom rate limit override for a specific identifier
- apply rate limiting to identifiers
- analytics
- api protection
- set rate limit override
- rate limiting
- apply multiple rate limit checks in one request
- delete a rate limit override
- remove a rate limit override for a specific identifier
- developer platform
- get override
- authentication
- get rate limit override for an identifier
- list rate limit overrides
- delete rate limit override
- rate limit override management
- apply rate limiting check for a single identifier
- unkey
- get the rate limit override configuration for a specific identifier
- delete override
- apply a rate limiting check for a user, ip, or custom identifier
- identity
- apply rate limit
- set a rate limit override for a specific identifier
- get rate limit override
- apply multiple rate limit checks simultaneously in a single request
- single override operations
- abuse prevention
- multi limit
- batch rate limit checks
- set override
- limit
- list all rate limit overrides configured for a namespace
- api keys
slug: rate-limiting
source_filename: rate-limiting.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Unkey Rate Limiting\n  description: >-\n    Workflow capability for standalone rate limiting using the Unkey platform.\n    Enables platform engineers, backend developers, and API teams to protect any\n    endpoint from abuse with global rate limiting, per-identifier overrides, and\n    multi-limit batch checks — without requiring API key management.\n  tags:\n    - Unkey\n    - Rate Limiting\n    - API Protection\n    - Developer Platform\n    - Abuse Prevention\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      UNKEY_ROOT_KEY: UNKEY_ROOT_KEY\n\ncapability:\n  consumes:\n    - import: unkey\n      location: ./shared/unkey.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: unkey-ratelimit-api\n      description: Unified REST API for Unkey rate limiting and override management.\n      resources:\n        - path: /v1/ratelimits\n          name: ratelimits\n \
  \         description: Apply rate limiting to identifiers\n          operations:\n            - method: POST\n              name: limit\n              description: Apply rate limiting check for a single identifier\n              call: \"unkey.limit\"\n              with:\n                namespace: \"rest.namespace\"\n                identifier: \"rest.identifier\"\n                limit: \"rest.limit\"\n                duration: \"rest.duration\"\n                cost: \"rest.cost\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/ratelimits/multi\n          name: multi-limit\n          description: Batch rate limit checks\n          operations:\n            - method: POST\n              name: multi-limit\n              description: Apply multiple rate limit checks in one request\n              call: \"unkey.multi-limit\"\n              with:\n                limits: \"rest.limits\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/ratelimits/overrides\n          name: ratelimit-overrides\n          description: Rate limit override management\n          operations:\n            - method: GET\n              name: list-overrides\n              description: List all rate limit overrides for a namespace\n              call: \"unkey.list-overrides\"\n              with:\n                namespaceId: \"rest.namespaceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: set-override\n              description: Set a rate limit override for a specific identifier\n              call: \"unkey.set-override\"\n              with:\n                identifier: \"rest.identifier\"\n                limit: \"rest.limit\"\n                duration: \"rest.duration\"\n              outputParameters:\n                - type: object\n             \
  \     mapping: \"$.\"\n\n        - path: /v1/ratelimits/overrides/{identifier}\n          name: ratelimit-override\n          description: Single override operations\n          operations:\n            - method: GET\n              name: get-override\n              description: Get rate limit override for an identifier\n              call: \"unkey.get-override\"\n              with:\n                identifier: \"rest.identifier\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-override\n              description: Delete a rate limit override\n              call: \"unkey.delete-override\"\n              with:\n                identifier: \"rest.identifier\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: unkey-ratelimit-mcp\n      transport: http\n      description: MCP server\
  \ for AI-assisted rate limit configuration and monitoring with Unkey.\n      tools:\n        - name: apply-rate-limit\n          description: Apply a rate limiting check for a user, IP, or custom identifier\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"unkey.limit\"\n          with:\n            namespace: \"tools.namespace\"\n            identifier: \"tools.identifier\"\n            limit: \"tools.limit\"\n            duration: \"tools.duration\"\n            cost: \"tools.cost\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: apply-multi-rate-limit\n          description: Apply multiple rate limit checks simultaneously in a single request\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"unkey.multi-limit\"\n          with:\n            limits: \"tools.limits\"\n     \
  \     outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: set-rate-limit-override\n          description: Set a custom rate limit override for a specific identifier\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"unkey.set-override\"\n          with:\n            identifier: \"tools.identifier\"\n            limit: \"tools.limit\"\n            duration: \"tools.duration\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-rate-limit-override\n          description: Get the rate limit override configuration for a specific identifier\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unkey.get-override\"\n          with:\n            identifier: \"tools.identifier\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name:\
  \ list-rate-limit-overrides\n          description: List all rate limit overrides configured for a namespace\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unkey.list-overrides\"\n          with:\n            namespaceId: \"tools.namespaceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-rate-limit-override\n          description: Remove a rate limit override for a specific identifier\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"unkey.delete-override\"\n          with:\n            identifier: \"tools.identifier\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/unkey/refs/heads/main/capabilities/rate-limiting.yaml
tags:
- Unkey
- Rate Limiting
- API Protection
- Developer Platform
- Abuse Prevention
tools:
- description: Apply a rate limiting check for a user, IP, or custom identifier
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: apply-rate-limit
- description: Apply multiple rate limit checks simultaneously in a single request
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: apply-multi-rate-limit
- description: Set a custom rate limit override for a specific identifier
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: set-rate-limit-override
- description: Get the rate limit override configuration for a specific identifier
  hints:
    openWorld: false
    readOnly: true
  name: get-rate-limit-override
- description: List all rate limit overrides configured for a namespace
  hints:
    openWorld: false
    readOnly: true
  name: list-rate-limit-overrides
- description: Remove a rate limit override for a specific identifier
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-rate-limit-override
---
