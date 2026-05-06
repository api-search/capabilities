---
categories: []
consumed_apis: []
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
- list flags
- add feature entitlement to a plan
- create a subscription plan
- add a feature entitlement to a subscription plan
- feature entitlements for plans
- feature management
- create a new product feature in schematic
- finops
- check a feature flag for a company/user
- create a new product feature
- check flag
- check flags bulk
- list feature flags
- create a feature flag
- create flag
- list subscription plans in schematic
- billing
- create plan entitlement
- check multiple feature flags at once for a company/user
- create a new subscription plan
- entitlements
- saas
- schematic
- list features
- metering
- list all product features defined in schematic
- plans
- list feature flags in schematic
- check whether a feature flag is enabled for a company and user context
- feature flag evaluation
- feature flags
- list plan entitlements
- bulk check multiple feature flags
- list subscription plans
- create plan
- list feature entitlements associated with plans
- pricing
- product feature definitions
- feature flags for runtime evaluation
- list all product features
- list plan feature entitlements
- subscription plan management
- create feature
- list plans
slug: feature-management
source_filename: feature-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Schematic Feature Management\n  description: Unified capability for managing product features, feature flags, and entitlements in Schematic. Enables product\n    and engineering teams to define features, create flags with rule-based evaluation, assign entitlements to subscription\n    plans, and evaluate flag values for customers at runtime.\n  tags:\n  - Entitlements\n  - Feature Flags\n  - Feature Management\n  - Plans\n  - SaaS\n  - Schematic\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SCHEMATIC_API_KEY: SCHEMATIC_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: schematic\n    baseUri: https://api.schematichq.com\n    description: Schematic feature and entitlement management API\n    authentication:\n      type: apikey\n      key: X-Schematic-Api-Key\n      value: '{{SCHEMATIC_API_KEY}}'\n      placement: header\n    resources:\n    - name: flags\n      path: /flags\n \
  \     description: Feature flags with rule-based evaluation\n      operations:\n      - name: list-flags\n        method: GET\n        description: List feature flags\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of flags to return\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Number of flags to skip\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-flag\n        method: POST\n        description: Create a new feature flag\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            defaultValue:\
  \ '{{tools.defaultValue}}'\n    - name: flag-check\n      path: /flags/check\n      description: Check feature flag values\n      operations:\n      - name: check-flag\n        method: POST\n        description: Check a feature flag for a company/user context\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            key: '{{tools.key}}'\n            company: '{{tools.company}}'\n            user: '{{tools.user}}'\n      - name: check-flags-bulk\n        method: POST\n        description: Check multiple feature flags in one request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            keys: '{{tools.keys}}'\n            company: '{{tools.company}}'\n            user: '{{tools.user}}'\n    - name: features\n      path:\
  \ /features\n      description: Product feature definitions\n      operations:\n      - name: list-features\n        method: GET\n        description: List product features\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-feature\n        method: POST\n        description: Create a product feature\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            featureType: '{{tools.featureType}}'\n            description: '{{tools.description}}'\n    - name: plans\n      path: /plans\n      description: Subscription plan management\n      operations:\n      - name: list-plans\n        method: GET\n      \
  \  description: List subscription plans\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-plan\n        method: POST\n        description: Create a subscription plan\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            planType: '{{tools.planType}}'\n            description: '{{tools.description}}'\n    - name: companies\n      path: /companies\n      description: Customer company management\n      operations:\n      - name: list-companies\n        method: GET\n        description: List customer companies\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n\
  \          required: false\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: upsert-company\n        method: POST\n        description: Create or update a company by external keys\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            keys: '{{tools.keys}}'\n            name: '{{tools.name}}'\n            traits: '{{tools.traits}}'\n    - name: users\n      path: /users\n      description: User management\n      operations:\n      - name: list-users\n        method: GET\n        description: List users\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: upsert-user\n        method: POST\n        description: Create or update a user by external keys\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            keys: '{{tools.keys}}'\n            name: '{{tools.name}}'\n            company: '{{tools.company}}'\n    - name: plan-entitlements\n      path: /plan-entitlements\n      description: Plan feature entitlements\n      operations:\n      - name: list-plan-entitlements\n        method: GET\n        description: List feature entitlements for plans\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-plan-entitlement\n        method: POST\n        description: Add a feature entitlement to a plan\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            featureId: '{{tools.featureId}}'\n            planId: '{{tools.planId}}'\n            valueType: '{{tools.valueType}}'\n            numericValue: '{{tools.numericValue}}'\n    - name: events\n      path: /events\n      description: Usage event tracking\n      operations:\n      - name: create-event\n        method: POST\n        description: Track a usage event for a company or user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            event_type: '{{tools.event_type}}'\n            name: '{{tools.name}}'\n            company: '{{tools.company}}'\n            user: '{{tools.user}}'\n            traits: '{{tools.traits}}'\n    - name: webhooks\n      path: /webhooks\n      description: Outbound\
  \ webhook configuration\n      operations:\n      - name: list-webhooks\n        method: GET\n        description: List configured webhooks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-webhook\n        method: POST\n        description: Create a webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            url: '{{tools.url}}'\n            eventTypes: '{{tools.eventTypes}}'\n    - name: insights\n      path: /insights\n      description: Usage analytics and reporting\n      operations:\n      - name: get-insights-summary\n        method: GET\n        description: Get summary analytics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-plan-growth\n    \
  \    method: GET\n        description: Get plan growth metrics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-top-features\n        method: GET\n        description: Get top features by usage\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: feature-management-api\n    description: Unified REST API for Schematic feature and entitlement management.\n    resources:\n    - path: /v1/features\n      name: features\n      description: Product feature definitions\n      operations:\n      - method: GET\n        name: list-features\n        description: List all product features\n        call: schematic.list-features\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-feature\n        description:\
  \ Create a new product feature\n        call: schematic.create-feature\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/flags\n      name: flags\n      description: Feature flags for runtime evaluation\n      operations:\n      - method: GET\n        name: list-flags\n        description: List feature flags\n        call: schematic.list-flags\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-flag\n        description: Create a feature flag\n        call: schematic.create-flag\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/flags/check\n      name: flag-check\n      description: Feature flag evaluation\n      operations:\n      - method: POST\n        name: check-flag\n        description: Check a feature flag for a company/user\n        call: schematic.check-flag\n        with:\n          key: rest.key\n        outputParameters:\n    \
  \    - type: object\n          mapping: $.\n      - method: POST\n        name: check-flags-bulk\n        description: Bulk check multiple feature flags\n        call: schematic.check-flags-bulk\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/plans\n      name: plans\n      description: Subscription plan management\n      operations:\n      - method: GET\n        name: list-plans\n        description: List subscription plans\n        call: schematic.list-plans\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-plan\n        description: Create a subscription plan\n        call: schematic.create-plan\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/entitlements\n      name: entitlements\n      description: Feature entitlements for plans\n      operations:\n      - method: GET\n        name: list-plan-entitlements\n        description: List\
  \ plan feature entitlements\n        call: schematic.list-plan-entitlements\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-plan-entitlement\n        description: Add feature entitlement to a plan\n        call: schematic.create-plan-entitlement\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: feature-management-mcp\n    transport: http\n    description: MCP server for AI-assisted feature and entitlement management.\n    tools:\n    - name: list-features\n      description: List all product features defined in Schematic\n      hints:\n        readOnly: true\n        openWorld: true\n      call: schematic.list-features\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-feature\n      description: Create a new product feature in Schematic\n      hints:\n        readOnly: false\n      call: schematic.create-feature\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-flags\n      description: List feature flags in Schematic\n      hints:\n        readOnly: true\n        openWorld: true\n      call: schematic.list-flags\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-flag\n      description: Check whether a feature flag is enabled for a company and user context\n      hints:\n        readOnly: true\n        openWorld: false\n      call: schematic.check-flag\n      with:\n        key: tools.key\n        company: tools.company\n        user: tools.user\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-flags-bulk\n      description: Check multiple feature flags at once for a company/user\n      hints:\n        readOnly: true\n        openWorld: false\n      call: schematic.check-flags-bulk\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-plans\n      description:\
  \ List subscription plans in Schematic\n      hints:\n        readOnly: true\n        openWorld: true\n      call: schematic.list-plans\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-plan\n      description: Create a new subscription plan\n      hints:\n        readOnly: false\n      call: schematic.create-plan\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-plan-entitlements\n      description: List feature entitlements associated with plans\n      hints:\n        readOnly: true\n        openWorld: true\n      call: schematic.list-plan-entitlements\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-plan-entitlement\n      description: Add a feature entitlement to a subscription plan\n      hints:\n        readOnly: false\n      call: schematic.create-plan-entitlement\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
