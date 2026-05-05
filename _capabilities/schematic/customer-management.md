---
categories: []
consumed_apis:
- schematic
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
- saas
- usage tracking
- finops
- list users
- list customer companies in schematic
- create event
- billing
- usage analytics
- get plan growth metrics
- usage event tracking
- get top features
- create or update a user
- track usage event
- get summary analytics across features, plans, and companies
- feature management
- create or update a company by external keys
- schematic
- metering
- get analytics summary
- list customer companies
- track a usage event
- feature flags
- customer company records
- customer users
- upsert user
- submit a usage event for metered feature consumption tracking
- get plan adoption and growth metrics
- upsert company
- list companies
- get top features by usage
- list users associated with companies
- create or update a company record using external identifiers (stripe id, salesforce id, etc.)
- create or update a user record
- entitlements
- get insights summary
- customer management
- pricing
- get the most-used product features by usage count
- get plan growth
slug: customer-management
source_filename: customer-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Schematic Customer Management\"\n  description: >-\n    Unified capability for managing customer companies, users, event tracking,\n    and billing integrations in Schematic. Enables SaaS teams to sync customers\n    from CRM and billing systems, track usage events for metering, and manage\n    company-level feature overrides.\n  tags:\n    - Billing\n    - Customer Management\n    - Metering\n    - SaaS\n    - Schematic\n    - Usage Tracking\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SCHEMATIC_API_KEY: SCHEMATIC_API_KEY\n\ncapability:\n  consumes:\n    - import: schematic\n      location: ./shared/schematic-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: customer-management-api\n      description: \"Unified REST API for Schematic customer and usage management.\"\n      resources:\n        - path: /v1/companies\n          name: companies\n\
  \          description: \"Customer company records\"\n          operations:\n            - method: GET\n              name: list-companies\n              description: \"List customer companies\"\n              call: \"schematic.list-companies\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: upsert-company\n              description: \"Create or update a company by external keys\"\n              call: \"schematic.upsert-company\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/users\n          name: users\n          description: \"Customer users\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List users\"\n              call: \"schematic.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\
  \n            - method: POST\n              name: upsert-user\n              description: \"Create or update a user\"\n              call: \"schematic.upsert-user\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/events\n          name: events\n          description: \"Usage event tracking\"\n          operations:\n            - method: POST\n              name: create-event\n              description: \"Track a usage event\"\n              call: \"schematic.create-event\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/insights\n          name: insights\n          description: \"Usage analytics\"\n          operations:\n            - method: GET\n              name: get-insights-summary\n              description: \"Get analytics summary\"\n              call: \"schematic.get-insights-summary\"\n              outputParameters:\n        \
  \        - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-plan-growth\n              description: \"Get plan growth metrics\"\n              call: \"schematic.get-plan-growth\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-top-features\n              description: \"Get top features by usage\"\n              call: \"schematic.get-top-features\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: customer-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted customer and usage management.\"\n      tools:\n        - name: list-companies\n          description: \"List customer companies in Schematic\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"schematic.list-companies\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: upsert-company\n          description: \"Create or update a company record using external identifiers (Stripe ID, Salesforce ID, etc.)\"\n          hints:\n            readOnly: false\n          call: \"schematic.upsert-company\"\n          with:\n            keys: \"tools.keys\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-users\n          description: \"List users associated with companies\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"schematic.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: upsert-user\n          description: \"Create or update a user record\"\n          hints:\n            readOnly: false\n          call: \"schematic.upsert-user\"\n       \
  \   outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: track-usage-event\n          description: \"Submit a usage event for metered feature consumption tracking\"\n          hints:\n            readOnly: false\n          call: \"schematic.create-event\"\n          with:\n            event_type: \"tools.event_type\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-insights-summary\n          description: \"Get summary analytics across features, plans, and companies\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"schematic.get-insights-summary\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-top-features\n          description: \"Get the most-used product features by usage count\"\n          hints:\n            readOnly: true\n           \
  \ openWorld: true\n          call: \"schematic.get-top-features\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-plan-growth\n          description: \"Get plan adoption and growth metrics\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"schematic.get-plan-growth\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
