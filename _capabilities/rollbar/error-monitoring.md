---
api_specs:
- filename: rollbar-rest-api-openapi.yml
  format: yaml
  label: rollbar
  slug: rollbar
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/rollbar/refs/heads/main/openapi/rollbar-rest-api-openapi.yml
categories: []
consumed_apis:
- rollbar
description: Unified workflow capability for error monitoring, incident triage, and deployment correlation using Rollbar REST and RQL APIs. Enables engineering teams and on-call engineers to investigate errors, query occurrence data, correlate issues with deployments, and manage error item lifecycle from detection through resolution.
layout: capability
name: Rollbar Error Monitoring
operations:
- description: List all tracked error items with filtering by status and severity
  method: GET
  name: list-errors
  path: /v1/errors
- description: Report a new error or exception to Rollbar
  method: POST
  name: report-error
  path: /v1/errors
- description: Get detailed information about a specific error item
  method: GET
  name: get-error
  path: /v1/errors/{itemId}
- description: Update error status (resolve, mute, activate)
  method: PATCH
  name: update-error-status
  path: /v1/errors/{itemId}
- description: List all individual error occurrences in the project
  method: GET
  name: list-occurrences
  path: /v1/occurrences
- description: Get a specific error occurrence with full stack trace
  method: GET
  name: get-occurrence
  path: /v1/occurrences
- description: List all Rollbar projects
  method: GET
  name: list-projects
  path: /v1/projects
- description: Get webhook notification configuration
  method: GET
  name: get-notification-config
  path: /v1/notifications
- description: List all notification rules
  method: GET
  name: list-notification-rules
  path: /v1/notifications
personas: []
provider_name: Rollbar
provider_slug: rollbar
search_terms:
- incident response
- list occurrences
- get a specific error occurrence with full stack trace
- rollbar
- application performance
- individual error occurrence retrieval
- list all notification rules
- get occurrence
- get detailed information about a specific error item
- debugging
- update error status (resolve, mute, activate)
- error item management and triage
- list all tracked error items with filtering by status and severity
- error tracking
- webhook notification configuration
- report error
- get a specific error occurrence including full stack trace, request data, and context
- get current webhook notification configuration
- rollbar project administration
- list projects
- individual error item management
- list tracked error items filtered by status, level, or environment
- devops
- resolve error
- list errors
- get detailed information about a specific error item including stack trace and metadata
- list individual error occurrences with full details and stack traces
- list all rollbar projects in the account
- update error status
- monitoring
- mark an error item as resolved
- list all teams in the rollbar account
- report a new error or exception to rollbar for tracking
- list teams
- list all rollbar projects
- get error
- get notification config
- list notification rules
- list all individual error occurrences in the project
- report a new error or exception to rollbar
- get webhook notification configuration
slug: error-monitoring
source_filename: error-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Rollbar Error Monitoring\"\n  description: >-\n    Unified workflow capability for error monitoring, incident triage, and\n    deployment correlation using Rollbar REST and RQL APIs. Enables engineering\n    teams and on-call engineers to investigate errors, query occurrence data,\n    correlate issues with deployments, and manage error item lifecycle from\n    detection through resolution.\n  tags:\n    - Error Tracking\n    - Monitoring\n    - Incident Response\n    - DevOps\n    - Rollbar\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      ROLLBAR_ACCESS_TOKEN: ROLLBAR_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: rollbar\n      location: ./shared/rollbar-rest-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: rollbar-error-monitoring-api\n      description: \"Unified REST API for Rollbar error monitoring and incident triage.\"\n      resources:\n\
  \        - path: /v1/errors\n          name: errors\n          description: \"Error item management and triage\"\n          operations:\n            - method: GET\n              name: list-errors\n              description: \"List all tracked error items with filtering by status and severity\"\n              call: \"rollbar.list-all-items\"\n              with:\n                status: \"rest.status\"\n                level: \"rest.level\"\n                environment: \"rest.environment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: POST\n              name: report-error\n              description: \"Report a new error or exception to Rollbar\"\n              call: \"rollbar.create-item\"\n              with:\n                payload: \"rest.payload\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/errors/{itemId}\n          name: error-detail\n\
  \          description: \"Individual error item management\"\n          operations:\n            - method: GET\n              name: get-error\n              description: \"Get detailed information about a specific error item\"\n              call: \"rollbar.get-item-by-id\"\n              with:\n                itemId: \"rest.itemId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: PATCH\n              name: update-error-status\n              description: \"Update error status (resolve, mute, activate)\"\n              call: \"rollbar.update-item\"\n              with:\n                itemId: \"rest.itemId\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/occurrences\n          name: occurrences\n          description: \"Individual error occurrence retrieval\"\n          operations:\n          \
  \  - method: GET\n              name: list-occurrences\n              description: \"List all individual error occurrences in the project\"\n              call: \"rollbar.list-project-occurrences\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: GET\n              name: get-occurrence\n              description: \"Get a specific error occurrence with full stack trace\"\n              call: \"rollbar.get-occurrence\"\n              with:\n                instanceId: \"rest.instanceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects\n          name: projects\n          description: \"Rollbar project administration\"\n          operations:\n            - method: GET\n              name: list-projects\n              description: \"List all Rollbar projects\"\n              call: \"rollbar.list-all-projects\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/notifications\n          name: notifications\n          description: \"Webhook notification configuration\"\n          operations:\n            - method: GET\n              name: get-notification-config\n              description: \"Get webhook notification configuration\"\n              call: \"rollbar.get-webhook-config\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: GET\n              name: list-notification-rules\n              description: \"List all notification rules\"\n              call: \"rollbar.list-webhook-rules\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: rollbar-error-monitoring-mcp\n      transport: http\n      description: \"MCP server for AI-assisted error monitoring, triage, and incident response.\"\
  \n      tools:\n        - name: list-errors\n          description: \"List tracked error items filtered by status, level, or environment\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rollbar.list-all-items\"\n          with:\n            status: \"tools.status\"\n            level: \"tools.level\"\n            environment: \"tools.environment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-error\n          description: \"Get detailed information about a specific error item including stack trace and metadata\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"rollbar.get-item-by-id\"\n          with:\n            itemId: \"tools.itemId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: report-error\n          description: \"Report a new error or exception to Rollbar for tracking\"\
  \n          hints:\n            readOnly: false\n            destructive: false\n          call: \"rollbar.create-item\"\n          with:\n            payload: \"tools.payload\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: resolve-error\n          description: \"Mark an error item as resolved\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"rollbar.update-item\"\n          with:\n            itemId: \"tools.itemId\"\n            status: \"resolved\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-occurrences\n          description: \"List individual error occurrences with full details and stack traces\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rollbar.list-project-occurrences\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n\n        - name: get-occurrence\n          description: \"Get a specific error occurrence including full stack trace, request data, and context\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"rollbar.get-occurrence\"\n          with:\n            instanceId: \"tools.instanceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-projects\n          description: \"List all Rollbar projects in the account\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rollbar.list-all-projects\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-teams\n          description: \"List all teams in the Rollbar account\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rollbar.list-all-teams\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: get-notification-config\n          description: \"Get current webhook notification configuration\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"rollbar.get-webhook-config\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/rollbar/refs/heads/main/capabilities/error-monitoring.yaml
tags:
- Error Tracking
- Monitoring
- Incident Response
- DevOps
- Rollbar
tools:
- description: List tracked error items filtered by status, level, or environment
  hints:
    openWorld: true
    readOnly: true
  name: list-errors
- description: Get detailed information about a specific error item including stack trace and metadata
  hints:
    openWorld: false
    readOnly: true
  name: get-error
- description: Report a new error or exception to Rollbar for tracking
  hints:
    destructive: false
    readOnly: false
  name: report-error
- description: Mark an error item as resolved
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: resolve-error
- description: List individual error occurrences with full details and stack traces
  hints:
    openWorld: true
    readOnly: true
  name: list-occurrences
- description: Get a specific error occurrence including full stack trace, request data, and context
  hints:
    openWorld: false
    readOnly: true
  name: get-occurrence
- description: List all Rollbar projects in the account
  hints:
    openWorld: true
    readOnly: true
  name: list-projects
- description: List all teams in the Rollbar account
  hints:
    openWorld: true
    readOnly: true
  name: list-teams
- description: Get current webhook notification configuration
  hints:
    openWorld: false
    readOnly: true
  name: get-notification-config
---
