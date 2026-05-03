---
categories: []
consumed_apis:
- gems-api
- webhooks-api
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
- remove a specific ruby gem version from the rubygems.org index
- webhook subscriptions for gem push events
- add owner
- list all gems owned by the authenticated rubygems user
- add gem owner
- yank gem
- open source
- list gem owners
- list all webhook subscriptions for the authenticated user
- list all owners of a specific gem
- remove a gem owner
- remove a gem version from the index
- publishing
- create webhook
- package manager
- remove an owner from a ruby gem by email address
- rubygems
- yank a gem version
- list owners
- remove gem owner
- push gem
- list owned gems
- submit a built gem to rubygems.org
- developer tools
- list webhooks
- gems
- test webhook
- create a webhook
- add a new owner to a ruby gem by email address
- remove owner
- gem ownership management
- add a gem owner
- ruby
- register a webhook to receive notifications when a gem is pushed
- ci/cd
- gem publishing operations
- submit a built ruby gem (.gem file) to rubygems.org for publishing
- test fire a webhook to verify it is receiving notifications correctly
- publish gem
slug: gem-publishing
source_filename: gem-publishing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"RubyGems Gem Publishing\"\n  description: >-\n    Workflow capability for publishing and managing Ruby gems on RubyGems.org.\n    Combines gem publishing, yanking, ownership management, and webhook\n    notification setup. Serves gem maintainers and CI/CD pipelines that\n    automate gem releases and manage the gem lifecycle on RubyGems.org.\n  tags:\n    - Ruby\n    - Gems\n    - Publishing\n    - CI/CD\n    - Package Manager\n    - RubyGems\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      RUBYGEMS_API_KEY: RUBYGEMS_API_KEY\n\ncapability:\n  consumes:\n    - import: gems-api\n      location: ./shared/gems-api.yaml\n    - import: webhooks-api\n      location: ./shared/webhooks-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: gem-publishing-api\n      description: \"Unified REST API for Ruby gem publishing and lifecycle management.\"\n      resources:\n\
  \        - path: /v1/gems\n          name: gems\n          description: \"Gem publishing operations\"\n          operations:\n            - method: POST\n              name: publish-gem\n              description: \"Submit a built gem to RubyGems.org\"\n              call: \"gems-api.push-gem\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/gems/yank\n          name: yank-gem\n          description: \"Yank a gem version\"\n          operations:\n            - method: DELETE\n              name: yank-gem\n              description: \"Remove a gem version from the index\"\n              call: \"gems-api.yank-gem\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/gems/{gemName}/owners\n          name: gem-owners\n          description: \"Gem ownership management\"\n          operations:\n            - method: GET\n              name: list-owners\n\
  \              description: \"List gem owners\"\n              call: \"gems-api.list-gem-owners\"\n              with:\n                gemName: \"rest.gemName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: add-owner\n              description: \"Add a gem owner\"\n              call: \"gems-api.add-gem-owner\"\n              with:\n                gemName: \"rest.gemName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: remove-owner\n              description: \"Remove a gem owner\"\n              call: \"gems-api.remove-gem-owner\"\n              with:\n                gemName: \"rest.gemName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/webhooks\n          name: webhooks\n          description: \"Webhook\
  \ subscriptions for gem push events\"\n          operations:\n            - method: GET\n              name: list-webhooks\n              description: \"List webhooks\"\n              call: \"webhooks-api.list-webhooks\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-webhook\n              description: \"Create a webhook\"\n              call: \"webhooks-api.create-webhook\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: gem-publishing-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Ruby gem publishing and lifecycle management.\"\n      tools:\n        - name: push-gem\n          description: \"Submit a built Ruby gem (.gem file) to RubyGems.org for publishing\"\n          hints:\n            readOnly: false\n            destructive: false\n   \
  \         idempotent: false\n          call: \"gems-api.push-gem\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: yank-gem\n          description: \"Remove a specific Ruby gem version from the RubyGems.org index\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"gems-api.yank-gem\"\n          with:\n            gem_name: \"tools.gemName\"\n            version: \"tools.version\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-owned-gems\n          description: \"List all gems owned by the authenticated RubyGems user\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"gems-api.list-owned-gems\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-gem-owners\n          description: \"List all owners\
  \ of a specific gem\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"gems-api.list-gem-owners\"\n          with:\n            gemName: \"tools.gemName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-gem-owner\n          description: \"Add a new owner to a Ruby gem by email address\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"gems-api.add-gem-owner\"\n          with:\n            gemName: \"tools.gemName\"\n            email: \"tools.email\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: remove-gem-owner\n          description: \"Remove an owner from a Ruby gem by email address\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"gems-api.remove-gem-owner\"\n  \
  \        with:\n            gemName: \"tools.gemName\"\n            email: \"tools.email\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-webhook\n          description: \"Register a webhook to receive notifications when a gem is pushed\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"webhooks-api.create-webhook\"\n          with:\n            gem_name: \"tools.gemName\"\n            url: \"tools.url\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-webhooks\n          description: \"List all webhook subscriptions for the authenticated user\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"webhooks-api.list-webhooks\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: test-webhook\n\
  \          description: \"Test fire a webhook to verify it is receiving notifications correctly\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"webhooks-api.fire-webhook\"\n          with:\n            gem_name: \"tools.gemName\"\n            url: \"tools.url\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
