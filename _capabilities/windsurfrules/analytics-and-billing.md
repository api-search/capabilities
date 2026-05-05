---
api_specs:
- filename: windsurf-enterprise-openapi.yml
  format: yaml
  label: windsurf
  slug: windsurf
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/windsurfrules/refs/heads/main/openapi/windsurf-enterprise-openapi.yml
categories: []
consumed_apis:
- windsurf
description: Analytics and billing management capability for Windsurf Enterprise. Enables platform administrators to query AI code completion usage, monitor Cascade agent activity, review per-user analytics, manage billing configurations, and track team credit consumption. Designed for engineering leaders, DevOps teams, and finance teams managing AI coding tool usage.
layout: capability
name: Windsurf Analytics and Billing
operations:
- description: Query code completion usage analytics
  method: POST
  name: query-completion-analytics
  path: /v1/analytics/completions
- description: Get user-level analytics and acceptance rates
  method: POST
  name: query-user-analytics
  path: /v1/analytics/users
- description: Get Cascade AI usage analytics
  method: POST
  name: query-cascade-analytics
  path: /v1/analytics/cascade
- description: Get team credit balance
  method: POST
  name: get-credit-balance
  path: /v1/billing/credits
- description: Get usage configuration settings
  method: POST
  name: get-usage-config
  path: /v1/billing/config
- description: Update usage configuration settings
  method: PUT
  name: update-usage-config
  path: /v1/billing/config
personas: []
provider_name: Windsurf
provider_slug: windsurfrules
search_terms:
- get credit balance
- update usage configuration, model access controls, and feature flags
- query code completion usage analytics
- query windsurf code completion usage analytics for the team
- billing
- enterprise
- get per-user code completion analytics and acceptance rates
- cascade ai agent analytics
- query user analytics
- analytics
- get usage configuration settings
- get cascade analytics
- teams
- get usage config
- get cascade ai usage analytics
- get user analytics
- update usage config
- ide
- ai agents
- get current usage configuration and feature flags for the team
- windsurf
- update usage configuration settings
- credit balance management
- coding standards
- usage configuration
- query cascade analytics
- query completion analytics
- get team credit balance
- code completion analytics
- per-user analytics
- ai coding
- get user-level analytics and acceptance rates
- developer workflow
- check current team credit balance and usage for windsurf enterprise
- ai copilot
- get cascade ai agent usage metrics including lines generated
slug: analytics-and-billing
source_filename: analytics-and-billing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Windsurf Analytics and Billing\"\n  description: >-\n    Analytics and billing management capability for Windsurf Enterprise. Enables\n    platform administrators to query AI code completion usage, monitor Cascade agent\n    activity, review per-user analytics, manage billing configurations, and track\n    team credit consumption. Designed for engineering leaders, DevOps teams, and\n    finance teams managing AI coding tool usage.\n  tags:\n    - Windsurf\n    - Analytics\n    - Billing\n    - Enterprise\n    - AI Coding\n    - Teams\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WINDSURF_SERVICE_KEY: WINDSURF_SERVICE_KEY\n\ncapability:\n  consumes:\n    - import: windsurf\n      location: ./shared/windsurf-enterprise.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: windsurf-analytics-api\n      description: \"Unified REST API for Windsurf Analytics\
  \ and Billing management.\"\n      resources:\n        - path: /v1/analytics/completions\n          name: completion-analytics\n          description: \"Code completion analytics\"\n          operations:\n            - method: POST\n              name: query-completion-analytics\n              description: \"Query code completion usage analytics\"\n              call: \"windsurf.get-custom-analytics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/analytics/users\n          name: user-analytics\n          description: \"Per-user analytics\"\n          operations:\n            - method: POST\n              name: query-user-analytics\n              description: \"Get user-level analytics and acceptance rates\"\n              call: \"windsurf.get-user-analytics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/analytics/cascade\n          name:\
  \ cascade-analytics\n          description: \"Cascade AI agent analytics\"\n          operations:\n            - method: POST\n              name: query-cascade-analytics\n              description: \"Get Cascade AI usage analytics\"\n              call: \"windsurf.get-cascade-analytics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/billing/credits\n          name: credit-balance\n          description: \"Credit balance management\"\n          operations:\n            - method: POST\n              name: get-credit-balance\n              description: \"Get team credit balance\"\n              call: \"windsurf.get-credit-balance\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/billing/config\n          name: usage-config\n          description: \"Usage configuration\"\n          operations:\n            - method: POST\n              name:\
  \ get-usage-config\n              description: \"Get usage configuration settings\"\n              call: \"windsurf.get-usage-config\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-usage-config\n              description: \"Update usage configuration settings\"\n              call: \"windsurf.set-usage-config\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: windsurf-analytics-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Windsurf Analytics and Billing management.\"\n      tools:\n        - name: query-completion-analytics\n          description: \"Query Windsurf code completion usage analytics for the team\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"windsurf.get-custom-analytics\"\n         \
  \ with:\n            start_timestamp: \"tools.start_timestamp\"\n            end_timestamp: \"tools.end_timestamp\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-user-analytics\n          description: \"Get per-user code completion analytics and acceptance rates\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"windsurf.get-user-analytics\"\n          with:\n            emails: \"tools.emails\"\n            start_timestamp: \"tools.start_timestamp\"\n            end_timestamp: \"tools.end_timestamp\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-cascade-analytics\n          description: \"Get Cascade AI agent usage metrics including lines generated\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"windsurf.get-cascade-analytics\"\n          with:\n            emails:\
  \ \"tools.emails\"\n            start_timestamp: \"tools.start_timestamp\"\n            end_timestamp: \"tools.end_timestamp\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-credit-balance\n          description: \"Check current team credit balance and usage for Windsurf Enterprise\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"windsurf.get-credit-balance\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-usage-config\n          description: \"Get current usage configuration and feature flags for the team\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"windsurf.get-usage-config\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-usage-config\n          description: \"Update usage configuration, model access\
  \ controls, and feature flags\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"windsurf.set-usage-config\"\n          with:\n            model_access: \"tools.model_access\"\n            feature_flags: \"tools.feature_flags\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/windsurfrules/refs/heads/main/capabilities/analytics-and-billing.yaml
tags:
- Windsurf
- Analytics
- Billing
- Enterprise
- AI Coding
- Teams
tools:
- description: Query Windsurf code completion usage analytics for the team
  hints:
    openWorld: true
    readOnly: true
  name: query-completion-analytics
- description: Get per-user code completion analytics and acceptance rates
  hints:
    openWorld: true
    readOnly: true
  name: get-user-analytics
- description: Get Cascade AI agent usage metrics including lines generated
  hints:
    openWorld: true
    readOnly: true
  name: get-cascade-analytics
- description: Check current team credit balance and usage for Windsurf Enterprise
  hints:
    openWorld: false
    readOnly: true
  name: get-credit-balance
- description: Get current usage configuration and feature flags for the team
  hints:
    openWorld: false
    readOnly: true
  name: get-usage-config
- description: Update usage configuration, model access controls, and feature flags
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-usage-config
---
