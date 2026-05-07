---
categories: []
consumed_apis: []
description: Unified capability for managing customer companies, users, event tracking, and billing integrations in Schematic. Enables SaaS teams to sync customers from CRM and billing systems, track usage events for metering, and manage company-level feature overrides.
layout: capability
name: Schematic Customer Management
operations:
- description: List customer companies
  method: GET
  name: list-companies
  path: /v1/companies
- description: Create or update a company by external keys
  method: POST
  name: upsert-company
  path: /v1/companies
- description: List users
  method: GET
  name: list-users
  path: /v1/users
- description: Create or update a user
  method: POST
  name: upsert-user
  path: /v1/users
- description: Track a usage event
  method: POST
  name: create-event
  path: /v1/events
- description: Get analytics summary
  method: GET
  name: get-insights-summary
  path: /v1/insights
- description: Get plan growth metrics
  method: GET
  name: get-plan-growth
  path: /v1/insights
- description: Get top features by usage
  method: GET
  name: get-top-features
  path: /v1/insights
personas: []
provider_name: Schematic
provider_slug: schematic
search_terms:
- feature flags
- get top features by usage
- entitlements
- upsert user
- get plan growth metrics
- customer company records
- billing
- list customer companies
- saas
- get plan adoption and growth metrics
- feature management
- list customer companies in schematic
- usage event tracking
- get plan growth
- customer users
- get summary analytics across features, plans, and companies
- create or update a company record using external identifiers (stripe id, salesforce id, etc.)
- usage tracking
- get analytics summary
- get top features
- get the most-used product features by usage count
- upsert company
- list users
- list users associated with companies
- schematic
- create or update a user
- create event
- pricing
- usage analytics
- metering
- create or update a company by external keys
- create or update a user record
- track usage event
- customer management
- list companies
- track a usage event
- submit a usage event for metered feature consumption tracking
- get insights summary
- finops
slug: customer-management
source_filename: customer-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Schematic Customer Management\n  description: Unified capability for managing customer companies, users, event tracking, and billing integrations in Schematic.\n    Enables SaaS teams to sync customers from CRM and billing systems, track usage events for metering, and manage company-level\n    feature overrides.\n  tags:\n  - Billing\n  - Customer Management\n  - Metering\n  - SaaS\n  - Schematic\n  - Usage Tracking\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SCHEMATIC_API_KEY: SCHEMATIC_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: schematic\n    baseUri: https://api.schematichq.com\n    description: Schematic feature and entitlement management API\n    authentication:\n      type: apikey\n      key: X-Schematic-Api-Key\n      value: '{{SCHEMATIC_API_KEY}}'\n      placement: header\n    resources:\n    - name: flags\n      path: /flags\n      description: Feature flags\
  \ with rule-based evaluation\n      operations:\n      - name: list-flags\n        method: GET\n        description: List feature flags\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of flags to return\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Number of flags to skip\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-flag\n        method: POST\n        description: Create a new feature flag\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            defaultValue: '{{tools.defaultValue}}'\n  \
  \  - name: flag-check\n      path: /flags/check\n      description: Check feature flag values\n      operations:\n      - name: check-flag\n        method: POST\n        description: Check a feature flag for a company/user context\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            key: '{{tools.key}}'\n            company: '{{tools.company}}'\n            user: '{{tools.user}}'\n      - name: check-flags-bulk\n        method: POST\n        description: Check multiple feature flags in one request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            keys: '{{tools.keys}}'\n            company: '{{tools.company}}'\n            user: '{{tools.user}}'\n    - name: features\n      path: /features\n      description:\
  \ Product feature definitions\n      operations:\n      - name: list-features\n        method: GET\n        description: List product features\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-feature\n        method: POST\n        description: Create a product feature\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            featureType: '{{tools.featureType}}'\n            description: '{{tools.description}}'\n    - name: plans\n      path: /plans\n      description: Subscription plan management\n      operations:\n      - name: list-plans\n        method: GET\n        description: List subscription\
  \ plans\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-plan\n        method: POST\n        description: Create a subscription plan\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            planType: '{{tools.planType}}'\n            description: '{{tools.description}}'\n    - name: companies\n      path: /companies\n      description: Customer company management\n      operations:\n      - name: list-companies\n        method: GET\n        description: List customer companies\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n\
  \        - name: offset\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: upsert-company\n        method: POST\n        description: Create or update a company by external keys\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            keys: '{{tools.keys}}'\n            name: '{{tools.name}}'\n            traits: '{{tools.traits}}'\n    - name: users\n      path: /users\n      description: User management\n      operations:\n      - name: list-users\n        method: GET\n        description: List users\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n      - name: upsert-user\n        method: POST\n        description: Create or update a user by external keys\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            keys: '{{tools.keys}}'\n            name: '{{tools.name}}'\n            company: '{{tools.company}}'\n    - name: plan-entitlements\n      path: /plan-entitlements\n      description: Plan feature entitlements\n      operations:\n      - name: list-plan-entitlements\n        method: GET\n        description: List feature entitlements for plans\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-plan-entitlement\n        method: POST\n        description: Add a feature entitlement to a plan\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            featureId: '{{tools.featureId}}'\n            planId: '{{tools.planId}}'\n            valueType: '{{tools.valueType}}'\n            numericValue: '{{tools.numericValue}}'\n    - name: events\n      path: /events\n      description: Usage event tracking\n      operations:\n      - name: create-event\n        method: POST\n        description: Track a usage event for a company or user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            event_type: '{{tools.event_type}}'\n            name: '{{tools.name}}'\n            company: '{{tools.company}}'\n            user: '{{tools.user}}'\n            traits: '{{tools.traits}}'\n    - name: webhooks\n      path: /webhooks\n      description: Outbound webhook configuration\n\
  \      operations:\n      - name: list-webhooks\n        method: GET\n        description: List configured webhooks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-webhook\n        method: POST\n        description: Create a webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            url: '{{tools.url}}'\n            eventTypes: '{{tools.eventTypes}}'\n    - name: insights\n      path: /insights\n      description: Usage analytics and reporting\n      operations:\n      - name: get-insights-summary\n        method: GET\n        description: Get summary analytics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-plan-growth\n        method: GET\n       \
  \ description: Get plan growth metrics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-top-features\n        method: GET\n        description: Get top features by usage\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: customer-management-api\n    description: Unified REST API for Schematic customer and usage management.\n    resources:\n    - path: /v1/companies\n      name: companies\n      description: Customer company records\n      operations:\n      - method: GET\n        name: list-companies\n        description: List customer companies\n        call: schematic.list-companies\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: upsert-company\n        description: Create or update a company\
  \ by external keys\n        call: schematic.upsert-company\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: Customer users\n      operations:\n      - method: GET\n        name: list-users\n        description: List users\n        call: schematic.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: upsert-user\n        description: Create or update a user\n        call: schematic.upsert-user\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events\n      name: events\n      description: Usage event tracking\n      operations:\n      - method: POST\n        name: create-event\n        description: Track a usage event\n        call: schematic.create-event\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/insights\n      name: insights\n      description:\
  \ Usage analytics\n      operations:\n      - method: GET\n        name: get-insights-summary\n        description: Get analytics summary\n        call: schematic.get-insights-summary\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-plan-growth\n        description: Get plan growth metrics\n        call: schematic.get-plan-growth\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-top-features\n        description: Get top features by usage\n        call: schematic.get-top-features\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: customer-management-mcp\n    transport: http\n    description: MCP server for AI-assisted customer and usage management.\n    tools:\n    - name: list-companies\n      description: List customer companies in Schematic\n      hints:\n        readOnly: true\n       \
  \ openWorld: true\n      call: schematic.list-companies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: upsert-company\n      description: Create or update a company record using external identifiers (Stripe ID, Salesforce ID, etc.)\n      hints:\n        readOnly: false\n      call: schematic.upsert-company\n      with:\n        keys: tools.keys\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-users\n      description: List users associated with companies\n      hints:\n        readOnly: true\n        openWorld: true\n      call: schematic.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: upsert-user\n      description: Create or update a user record\n      hints:\n        readOnly: false\n      call: schematic.upsert-user\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: track-usage-event\n      description: Submit a\
  \ usage event for metered feature consumption tracking\n      hints:\n        readOnly: false\n      call: schematic.create-event\n      with:\n        event_type: tools.event_type\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-insights-summary\n      description: Get summary analytics across features, plans, and companies\n      hints:\n        readOnly: true\n        openWorld: true\n      call: schematic.get-insights-summary\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-top-features\n      description: Get the most-used product features by usage count\n      hints:\n        readOnly: true\n        openWorld: true\n      call: schematic.get-top-features\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-plan-growth\n      description: Get plan adoption and growth metrics\n      hints:\n        readOnly: true\n        openWorld: true\n      call: schematic.get-plan-growth\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/schematic/refs/heads/main/capabilities/customer-management.yaml
tags:
- Billing
- Customer Management
- Metering
- SaaS
- Schematic
- Usage Tracking
tools:
- description: List customer companies in Schematic
  hints:
    openWorld: true
    readOnly: true
  name: list-companies
- description: Create or update a company record using external identifiers (Stripe ID, Salesforce ID, etc.)
  hints:
    readOnly: false
  name: upsert-company
- description: List users associated with companies
  hints:
    openWorld: true
    readOnly: true
  name: list-users
- description: Create or update a user record
  hints:
    readOnly: false
  name: upsert-user
- description: Submit a usage event for metered feature consumption tracking
  hints:
    readOnly: false
  name: track-usage-event
- description: Get summary analytics across features, plans, and companies
  hints:
    openWorld: true
    readOnly: true
  name: get-insights-summary
- description: Get the most-used product features by usage count
  hints:
    openWorld: true
    readOnly: true
  name: get-top-features
- description: Get plan adoption and growth metrics
  hints:
    openWorld: true
    readOnly: true
  name: get-plan-growth
---
