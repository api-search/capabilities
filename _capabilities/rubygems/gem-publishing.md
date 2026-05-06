---
categories: []
consumed_apis: []
description: Workflow capability for publishing and managing Ruby gems on RubyGems.org. Combines gem publishing, yanking, ownership management, and webhook notification setup. Serves gem maintainers and CI/CD pipelines that automate gem releases and manage the gem lifecycle on RubyGems.org.
layout: capability
name: RubyGems Gem Publishing
operations:
- description: Submit a built gem to RubyGems.org
  method: POST
  name: publish-gem
  path: /v1/gems
- description: Remove a gem version from the index
  method: DELETE
  name: yank-gem
  path: /v1/gems/yank
- description: List gem owners
  method: GET
  name: list-owners
  path: /v1/gems/{gemName}/owners
- description: Add a gem owner
  method: POST
  name: add-owner
  path: /v1/gems/{gemName}/owners
- description: Remove a gem owner
  method: DELETE
  name: remove-owner
  path: /v1/gems/{gemName}/owners
- description: List webhooks
  method: GET
  name: list-webhooks
  path: /v1/webhooks
- description: Create a webhook
  method: POST
  name: create-webhook
  path: /v1/webhooks
personas: []
provider_name: RubyGems
provider_slug: rubygems
search_terms:
- ruby
- list all owners of a specific gem
- remove owner
- developer tools
- test fire a webhook to verify it is receiving notifications correctly
- add a new owner to a ruby gem by email address
- gems
- publishing
- register a webhook to receive notifications when a gem is pushed
- create webhook
- yank gem
- rubygems
- list all webhook subscriptions for the authenticated user
- create a webhook
- submit a built ruby gem (.gem file) to rubygems.org for publishing
- package manager
- open source
- ci/cd
- test webhook
- list all gems owned by the authenticated rubygems user
- yank a gem version
- list gem owners
- remove a specific ruby gem version from the rubygems.org index
- remove an owner from a ruby gem by email address
- publish gem
- gem ownership management
- add gem owner
- add owner
- remove a gem owner
- webhook subscriptions for gem push events
- gem publishing operations
- add a gem owner
- list owners
- push gem
- remove gem owner
- remove a gem version from the index
- list webhooks
- submit a built gem to rubygems.org
- list owned gems
slug: gem-publishing
source_filename: gem-publishing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: RubyGems Gem Publishing\n  description: Workflow capability for publishing and managing Ruby gems on RubyGems.org. Combines gem publishing, yanking,\n    ownership management, and webhook notification setup. Serves gem maintainers and CI/CD pipelines that automate gem releases\n    and manage the gem lifecycle on RubyGems.org.\n  tags:\n  - Ruby\n  - Gems\n  - Publishing\n  - CI/CD\n  - Package Manager\n  - RubyGems\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RUBYGEMS_API_KEY: RUBYGEMS_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: gems-api\n    baseUri: https://rubygems.org/api/v1\n    description: RubyGems Gems API v1 for gem metadata, ownership, and publishing\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{RUBYGEMS_API_KEY}}'\n      placement: header\n    resources:\n    - name: gems\n      path: /gems\n      description: Gem metadata\
  \ and publishing operations\n      operations:\n      - name: get-gem-info\n        method: GET\n        description: Get detailed information about a specific gem by name\n        inputParameters:\n        - name: gemName\n          in: path\n          type: string\n          required: true\n          description: Gem name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-owned-gems\n        method: GET\n        description: List gems owned by the authenticated user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: push-gem\n        method: POST\n        description: Submit a built gem to RubyGems.org\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: yank-gem\n        method: DELETE\n        description: Remove\
  \ a specific gem version from RubyGems.org\n        inputParameters:\n        - name: gem_name\n          in: query\n          type: string\n          required: true\n          description: Gem name to yank\n        - name: version\n          in: query\n          type: string\n          required: true\n          description: Version to yank\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-reverse-dependencies\n        method: GET\n        description: Get list of gems that depend on a specific gem\n        inputParameters:\n        - name: gemName\n          in: path\n          type: string\n          required: true\n          description: Gem name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: versions\n      path: /versions\n      description: Gem version querying\n      operations:\n      - name:\
  \ get-gem-versions\n        method: GET\n        description: Get all versions for a specific gem\n        inputParameters:\n        - name: gemName\n          in: path\n          type: string\n          required: true\n          description: Gem name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-latest-gem-version\n        method: GET\n        description: Get the latest version of a gem\n        inputParameters:\n        - name: gemName\n          in: path\n          type: string\n          required: true\n          description: Gem name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-timeframe-versions\n        method: GET\n        description: Get gem versions released within a timeframe\n        inputParameters:\n        - name: from\n          in: query\n          type: string\n      \
  \    required: true\n          description: Start of timeframe (ISO 8601)\n        - name: to\n          in: query\n          type: string\n          required: false\n          description: End of timeframe (ISO 8601)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: owners\n      path: /gems\n      description: Gem ownership management\n      operations:\n      - name: list-gem-owners\n        method: GET\n        description: List owners of a specific gem\n        inputParameters:\n        - name: gemName\n          in: path\n          type: string\n          required: true\n          description: Gem name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-gem-owner\n        method: POST\n        description: Add an owner to a gem\n        inputParameters:\n        - name: gemName\n          in: path\n\
  \          type: string\n          required: true\n          description: Gem name\n        - name: email\n          in: body\n          type: string\n          required: true\n          description: Email of new owner\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: remove-gem-owner\n        method: DELETE\n        description: Remove an owner from a gem\n        inputParameters:\n        - name: gemName\n          in: path\n          type: string\n          required: true\n          description: Gem name\n        - name: email\n          in: body\n          type: string\n          required: true\n          description: Email of owner to remove\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: profiles\n      path: /profiles\n      description: User profile retrieval\n      operations:\n      - name: get-user-profile\n\
  \        method: GET\n        description: Get profile information for a user\n        inputParameters:\n        - name: userHandle\n          in: path\n          type: string\n          required: true\n          description: User handle or ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: webhooks-api\n    baseUri: https://rubygems.org/api/v1\n    description: RubyGems Webhooks API for event subscription management\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{RUBYGEMS_API_KEY}}'\n      placement: header\n    resources:\n    - name: webhooks\n      path: /web_hooks\n      description: Webhook subscription management\n      operations:\n      - name: list-webhooks\n        method: GET\n        description: List all webhooks registered for the authenticated user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: create-webhook\n        method: POST\n        description: Register a new webhook for gem push events\n        inputParameters:\n        - name: gem_name\n          in: body\n          type: string\n          required: true\n          description: Gem name or * for all gems\n        - name: url\n          in: body\n          type: string\n          required: true\n          description: Webhook delivery URL\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: remove-webhook\n        method: DELETE\n        description: Remove an existing webhook subscription\n        inputParameters:\n        - name: gem_name\n          in: body\n          type: string\n          required: true\n          description: Gem name or * for global webhook\n        - name: url\n          in: body\n          type: string\n          required: true\n          description:\
  \ Webhook URL to remove\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: fire-webhook\n        method: POST\n        description: Test fire an existing webhook\n        inputParameters:\n        - name: gem_name\n          in: body\n          type: string\n          required: true\n          description: Gem name or * for global webhook\n        - name: url\n          in: body\n          type: string\n          required: true\n          description: Webhook URL to test\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: gem-publishing-api\n    description: Unified REST API for Ruby gem publishing and lifecycle management.\n    resources:\n    - path: /v1/gems\n      name: gems\n      description: Gem publishing operations\n      operations:\n      - method: POST\n\
  \        name: publish-gem\n        description: Submit a built gem to RubyGems.org\n        call: gems-api.push-gem\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/gems/yank\n      name: yank-gem\n      description: Yank a gem version\n      operations:\n      - method: DELETE\n        name: yank-gem\n        description: Remove a gem version from the index\n        call: gems-api.yank-gem\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/gems/{gemName}/owners\n      name: gem-owners\n      description: Gem ownership management\n      operations:\n      - method: GET\n        name: list-owners\n        description: List gem owners\n        call: gems-api.list-gem-owners\n        with:\n          gemName: rest.gemName\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: add-owner\n        description: Add a gem owner\n        call: gems-api.add-gem-owner\n\
  \        with:\n          gemName: rest.gemName\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: remove-owner\n        description: Remove a gem owner\n        call: gems-api.remove-gem-owner\n        with:\n          gemName: rest.gemName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/webhooks\n      name: webhooks\n      description: Webhook subscriptions for gem push events\n      operations:\n      - method: GET\n        name: list-webhooks\n        description: List webhooks\n        call: webhooks-api.list-webhooks\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-webhook\n        description: Create a webhook\n        call: webhooks-api.create-webhook\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: gem-publishing-mcp\n    transport: http\n\
  \    description: MCP server for AI-assisted Ruby gem publishing and lifecycle management.\n    tools:\n    - name: push-gem\n      description: Submit a built Ruby gem (.gem file) to RubyGems.org for publishing\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: gems-api.push-gem\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: yank-gem\n      description: Remove a specific Ruby gem version from the RubyGems.org index\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: gems-api.yank-gem\n      with:\n        gem_name: tools.gemName\n        version: tools.version\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-owned-gems\n      description: List all gems owned by the authenticated RubyGems user\n      hints:\n        readOnly: true\n        openWorld: false\n      call: gems-api.list-owned-gems\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-gem-owners\n      description: List all owners of a specific gem\n      hints:\n        readOnly: true\n        openWorld: false\n      call: gems-api.list-gem-owners\n      with:\n        gemName: tools.gemName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-gem-owner\n      description: Add a new owner to a Ruby gem by email address\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: gems-api.add-gem-owner\n      with:\n        gemName: tools.gemName\n        email: tools.email\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: remove-gem-owner\n      description: Remove an owner from a Ruby gem by email address\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: gems-api.remove-gem-owner\n      with:\n        gemName: tools.gemName\n        email: tools.email\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-webhook\n      description: Register a webhook to receive notifications when a gem is pushed\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: webhooks-api.create-webhook\n      with:\n        gem_name: tools.gemName\n        url: tools.url\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-webhooks\n      description: List all webhook subscriptions for the authenticated user\n      hints:\n        readOnly: true\n        openWorld: false\n      call: webhooks-api.list-webhooks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: test-webhook\n      description: Test fire a webhook to verify it is receiving notifications correctly\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: webhooks-api.fire-webhook\n      with:\n     \
  \   gem_name: tools.gemName\n        url: tools.url\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/rubygems/refs/heads/main/capabilities/gem-publishing.yaml
tags:
- Ruby
- Gems
- Publishing
- CI/CD
- Package Manager
- RubyGems
tools:
- description: Submit a built Ruby gem (.gem file) to RubyGems.org for publishing
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: push-gem
- description: Remove a specific Ruby gem version from the RubyGems.org index
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: yank-gem
- description: List all gems owned by the authenticated RubyGems user
  hints:
    openWorld: false
    readOnly: true
  name: list-owned-gems
- description: List all owners of a specific gem
  hints:
    openWorld: false
    readOnly: true
  name: list-gem-owners
- description: Add a new owner to a Ruby gem by email address
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: add-gem-owner
- description: Remove an owner from a Ruby gem by email address
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: remove-gem-owner
- description: Register a webhook to receive notifications when a gem is pushed
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-webhook
- description: List all webhook subscriptions for the authenticated user
  hints:
    openWorld: false
    readOnly: true
  name: list-webhooks
- description: Test fire a webhook to verify it is receiving notifications correctly
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: test-webhook
---
