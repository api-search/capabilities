---
categories: []
consumed_apis:
- schematic
description: Unified capability for managing product features, feature flags, and entitlements in Schematic. Enables product and engineering teams to define features, create flags with rule-based evaluation, assign entitlements to subscription plans, and evaluate flag values for customers at runtime.
layout: capability
name: Schematic Feature Management
operations:
- description: List all product features
  method: GET
  name: list-features
  path: /v1/features
- description: Create a new product feature
  method: POST
  name: create-feature
  path: /v1/features
- description: List feature flags
  method: GET
  name: list-flags
  path: /v1/flags
- description: Create a feature flag
  method: POST
  name: create-flag
  path: /v1/flags
- description: Check a feature flag for a company/user
  method: POST
  name: check-flag
  path: /v1/flags/check
- description: Bulk check multiple feature flags
  method: POST
  name: check-flags-bulk
  path: /v1/flags/check
- description: List subscription plans
  method: GET
  name: list-plans
  path: /v1/plans
- description: Create a subscription plan
  method: POST
  name: create-plan
  path: /v1/plans
- description: List plan feature entitlements
  method: GET
  name: list-plan-entitlements
  path: /v1/entitlements
- description: Add feature entitlement to a plan
  method: POST
  name: create-plan-entitlement
  path: /v1/entitlements
personas: []
provider_name: Schematic
provider_slug: schematic
search_terms:
- finops
- feature flags
- list plan entitlements
- check whether a feature flag is enabled for a company and user context
- create a new product feature
- create flag
- list feature flags in schematic
- bulk check multiple feature flags
- saas
- subscription plan management
- create a feature flag
- check a feature flag for a company/user
- list all product features defined in schematic
- feature management
- add feature entitlement to a plan
- create a new subscription plan
- list feature entitlements associated with plans
- check multiple feature flags at once for a company/user
- check flag
- feature flags for runtime evaluation
- add a feature entitlement to a subscription plan
- feature entitlements for plans
- list plans
- create a subscription plan
- product feature definitions
- list features
- feature flag evaluation
- create a new product feature in schematic
- list plan feature entitlements
- plans
- list all product features
- entitlements
- create feature
- create plan
- list flags
- metering
- list feature flags
- schematic
- create plan entitlement
- check flags bulk
- pricing
- list subscription plans in schematic
- billing
- list subscription plans
slug: feature-management
source_filename: feature-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Schematic Feature Management\"\n  description: >-\n    Unified capability for managing product features, feature flags, and\n    entitlements in Schematic. Enables product and engineering teams to define\n    features, create flags with rule-based evaluation, assign entitlements to\n    subscription plans, and evaluate flag values for customers at runtime.\n  tags:\n    - Entitlements\n    - Feature Flags\n    - Feature Management\n    - Plans\n    - SaaS\n    - Schematic\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SCHEMATIC_API_KEY: SCHEMATIC_API_KEY\n\ncapability:\n  consumes:\n    - import: schematic\n      location: ./shared/schematic-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: feature-management-api\n      description: \"Unified REST API for Schematic feature and entitlement management.\"\n      resources:\n        - path: /v1/features\n\
  \          name: features\n          description: \"Product feature definitions\"\n          operations:\n            - method: GET\n              name: list-features\n              description: \"List all product features\"\n              call: \"schematic.list-features\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-feature\n              description: \"Create a new product feature\"\n              call: \"schematic.create-feature\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/flags\n          name: flags\n          description: \"Feature flags for runtime evaluation\"\n          operations:\n            - method: GET\n              name: list-flags\n              description: \"List feature flags\"\n              call: \"schematic.list-flags\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-flag\n              description: \"Create a feature flag\"\n              call: \"schematic.create-flag\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/flags/check\n          name: flag-check\n          description: \"Feature flag evaluation\"\n          operations:\n            - method: POST\n              name: check-flag\n              description: \"Check a feature flag for a company/user\"\n              call: \"schematic.check-flag\"\n              with:\n                key: \"rest.key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: check-flags-bulk\n              description: \"Bulk check multiple feature flags\"\n              call: \"schematic.check-flags-bulk\"\n              outputParameters:\n   \
  \             - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/plans\n          name: plans\n          description: \"Subscription plan management\"\n          operations:\n            - method: GET\n              name: list-plans\n              description: \"List subscription plans\"\n              call: \"schematic.list-plans\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-plan\n              description: \"Create a subscription plan\"\n              call: \"schematic.create-plan\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/entitlements\n          name: entitlements\n          description: \"Feature entitlements for plans\"\n          operations:\n            - method: GET\n              name: list-plan-entitlements\n              description: \"List plan feature entitlements\"\
  \n              call: \"schematic.list-plan-entitlements\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-plan-entitlement\n              description: \"Add feature entitlement to a plan\"\n              call: \"schematic.create-plan-entitlement\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: feature-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted feature and entitlement management.\"\n      tools:\n        - name: list-features\n          description: \"List all product features defined in Schematic\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"schematic.list-features\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-feature\n\
  \          description: \"Create a new product feature in Schematic\"\n          hints:\n            readOnly: false\n          call: \"schematic.create-feature\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-flags\n          description: \"List feature flags in Schematic\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"schematic.list-flags\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: check-flag\n          description: \"Check whether a feature flag is enabled for a company and user context\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"schematic.check-flag\"\n          with:\n            key: \"tools.key\"\n            company: \"tools.company\"\n            user: \"tools.user\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n\n        - name: check-flags-bulk\n          description: \"Check multiple feature flags at once for a company/user\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"schematic.check-flags-bulk\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-plans\n          description: \"List subscription plans in Schematic\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"schematic.list-plans\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-plan\n          description: \"Create a new subscription plan\"\n          hints:\n            readOnly: false\n          call: \"schematic.create-plan\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-plan-entitlements\n          description: \"List feature entitlements associated\
  \ with plans\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"schematic.list-plan-entitlements\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-plan-entitlement\n          description: \"Add a feature entitlement to a subscription plan\"\n          hints:\n            readOnly: false\n          call: \"schematic.create-plan-entitlement\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/schematic/refs/heads/main/capabilities/feature-management.yaml
tags:
- Entitlements
- Feature Flags
- Feature Management
- Plans
- SaaS
- Schematic
tools:
- description: List all product features defined in Schematic
  hints:
    openWorld: true
    readOnly: true
  name: list-features
- description: Create a new product feature in Schematic
  hints:
    readOnly: false
  name: create-feature
- description: List feature flags in Schematic
  hints:
    openWorld: true
    readOnly: true
  name: list-flags
- description: Check whether a feature flag is enabled for a company and user context
  hints:
    openWorld: false
    readOnly: true
  name: check-flag
- description: Check multiple feature flags at once for a company/user
  hints:
    openWorld: false
    readOnly: true
  name: check-flags-bulk
- description: List subscription plans in Schematic
  hints:
    openWorld: true
    readOnly: true
  name: list-plans
- description: Create a new subscription plan
  hints:
    readOnly: false
  name: create-plan
- description: List feature entitlements associated with plans
  hints:
    openWorld: true
    readOnly: true
  name: list-plan-entitlements
- description: Add a feature entitlement to a subscription plan
  hints:
    readOnly: false
  name: create-plan-entitlement
---
