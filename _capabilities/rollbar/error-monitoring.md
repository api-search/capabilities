---
categories: []
consumed_apis: []
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
- list all notification rules
- mark an error item as resolved
- rollbar
- devops
- report a new error or exception to rollbar
- list tracked error items filtered by status, level, or environment
- error item management and triage
- incident response
- list errors
- list all teams in the rollbar account
- report error
- monitoring
- get a specific error occurrence with full stack trace
- report a new error or exception to rollbar for tracking
- list teams
- individual error occurrence retrieval
- application performance
- error tracking
- list projects
- list notification rules
- webhook notification configuration
- list all rollbar projects
- list all tracked error items with filtering by status and severity
- get detailed information about a specific error item
- update error status (resolve, mute, activate)
- get occurrence
- get notification config
- list individual error occurrences with full details and stack traces
- individual error item management
- get detailed information about a specific error item including stack trace and metadata
- get error
- debugging
- list occurrences
- resolve error
- list all individual error occurrences in the project
- rollbar project administration
- list all rollbar projects in the account
- get webhook notification configuration
- update error status
- get a specific error occurrence including full stack trace, request data, and context
- get current webhook notification configuration
slug: error-monitoring
source_filename: error-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Rollbar Error Monitoring\n  description: Unified workflow capability for error monitoring, incident triage, and deployment correlation using Rollbar\n    REST and RQL APIs. Enables engineering teams and on-call engineers to investigate errors, query occurrence data, correlate\n    issues with deployments, and manage error item lifecycle from detection through resolution.\n  tags:\n  - Error Tracking\n  - Monitoring\n  - Incident Response\n  - DevOps\n  - Rollbar\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ROLLBAR_ACCESS_TOKEN: ROLLBAR_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: rollbar\n    baseUri: https://api.rollbar.com/api/1\n    description: Rollbar REST API for error tracking and project management\n    authentication:\n      type: apikey\n      key: X-Rollbar-Access-Token\n      value: '{{ROLLBAR_ACCESS_TOKEN}}'\n      placement: header\n    resources:\n \
  \   - name: items\n      path: /items/\n      description: Manage error and message items tracked by Rollbar\n      operations:\n      - name: create-item\n        method: POST\n        description: Report an error or message to Rollbar\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            payload: '{{tools.payload}}'\n      - name: list-all-items\n        method: GET\n        description: Returns all items in the project ordered by most recent occurrence\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status (active, resolved, muted)\n        - name: level\n          in: query\n          type: string\n          required: false\n          description: Filter by level (debug, info, warning, error, critical)\n        - name: environment\n     \
  \     in: query\n          type: string\n          required: false\n          description: Filter by environment\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-item-by-id\n        method: GET\n        description: Get an item by its Rollbar item ID\n        inputParameters:\n        - name: itemId\n          in: path\n          type: integer\n          required: true\n          description: Rollbar item ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-item\n        method: PATCH\n        description: Update the status or assignee of an item\n        inputParameters:\n        - name: itemId\n          in: path\n          type: integer\n          required: true\n\
  \          description: Rollbar item ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            status: '{{tools.status}}'\n    - name: occurrences\n      path: /instances/\n      description: Retrieve individual occurrences of errors and messages\n      operations:\n      - name: list-project-occurrences\n        method: GET\n        description: List all occurrences in a project\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-occurrence\n        method: GET\n        description: Get a single occurrence\n        inputParameters:\n        - name: instanceId\n          in: path\n          type: integer\n\
  \          required: true\n          description: Occurrence instance ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects\n      path: /projects\n      description: Manage Rollbar projects\n      operations:\n      - name: list-all-projects\n        method: GET\n        description: Returns all projects in the account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-project\n        method: POST\n        description: Create a new Rollbar project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: get-project\n        method: GET\n        description: Get details of a specific project\n        inputParameters:\n \
  \       - name: projectId\n          in: path\n          type: integer\n          required: true\n          description: Rollbar project ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-project\n        method: DELETE\n        description: Delete a Rollbar project\n        inputParameters:\n        - name: projectId\n          in: path\n          type: integer\n          required: true\n          description: Rollbar project ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: teams\n      path: /teams\n      description: Manage teams and team membership\n      operations:\n      - name: list-all-teams\n        method: GET\n        description: Returns all teams in the account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: create-team\n        method: POST\n        description: Create a new team\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            access_level: '{{tools.access_level}}'\n      - name: assign-user-to-team\n        method: PUT\n        description: Add a user to a team\n        inputParameters:\n        - name: teamId\n          in: path\n          type: integer\n          required: true\n          description: Team ID\n        - name: userId\n          in: path\n          type: integer\n          required: true\n          description: User ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: notifications\n      path: /notifications/webhook\n      description: Manage webhook notification configuration\n    \
  \  operations:\n      - name: get-webhook-config\n        method: GET\n        description: Get webhook notification configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-webhook-rules\n        method: GET\n        description: List all webhook notification rules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: rollbar-error-monitoring-api\n    description: Unified REST API for Rollbar error monitoring and incident triage.\n    resources:\n    - path: /v1/errors\n      name: errors\n      description: Error item management and triage\n      operations:\n      - method: GET\n        name: list-errors\n        description: List all tracked error items with filtering by status and severity\n        call: rollbar.list-all-items\n        with:\n    \
  \      status: rest.status\n          level: rest.level\n          environment: rest.environment\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: report-error\n        description: Report a new error or exception to Rollbar\n        call: rollbar.create-item\n        with:\n          payload: rest.payload\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/errors/{itemId}\n      name: error-detail\n      description: Individual error item management\n      operations:\n      - method: GET\n        name: get-error\n        description: Get detailed information about a specific error item\n        call: rollbar.get-item-by-id\n        with:\n          itemId: rest.itemId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-error-status\n        description: Update error status (resolve, mute, activate)\n        call: rollbar.update-item\n\
  \        with:\n          itemId: rest.itemId\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/occurrences\n      name: occurrences\n      description: Individual error occurrence retrieval\n      operations:\n      - method: GET\n        name: list-occurrences\n        description: List all individual error occurrences in the project\n        call: rollbar.list-project-occurrences\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-occurrence\n        description: Get a specific error occurrence with full stack trace\n        call: rollbar.get-occurrence\n        with:\n          instanceId: rest.instanceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects\n      name: projects\n      description: Rollbar project administration\n      operations:\n      - method: GET\n        name: list-projects\n     \
  \   description: List all Rollbar projects\n        call: rollbar.list-all-projects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/notifications\n      name: notifications\n      description: Webhook notification configuration\n      operations:\n      - method: GET\n        name: get-notification-config\n        description: Get webhook notification configuration\n        call: rollbar.get-webhook-config\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-notification-rules\n        description: List all notification rules\n        call: rollbar.list-webhook-rules\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: rollbar-error-monitoring-mcp\n    transport: http\n    description: MCP server for AI-assisted error monitoring, triage, and incident response.\n    tools:\n    - name: list-errors\n      description:\
  \ List tracked error items filtered by status, level, or environment\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rollbar.list-all-items\n      with:\n        status: tools.status\n        level: tools.level\n        environment: tools.environment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-error\n      description: Get detailed information about a specific error item including stack trace and metadata\n      hints:\n        readOnly: true\n        openWorld: false\n      call: rollbar.get-item-by-id\n      with:\n        itemId: tools.itemId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: report-error\n      description: Report a new error or exception to Rollbar for tracking\n      hints:\n        readOnly: false\n        destructive: false\n      call: rollbar.create-item\n      with:\n        payload: tools.payload\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: resolve-error\n      description: Mark an error item as resolved\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: rollbar.update-item\n      with:\n        itemId: tools.itemId\n        status: resolved\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-occurrences\n      description: List individual error occurrences with full details and stack traces\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rollbar.list-project-occurrences\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-occurrence\n      description: Get a specific error occurrence including full stack trace, request data, and context\n      hints:\n        readOnly: true\n        openWorld: false\n      call: rollbar.get-occurrence\n      with:\n        instanceId: tools.instanceId\n      outputParameters:\n      - type: object\n        mapping: $.\n   \
  \ - name: list-projects\n      description: List all Rollbar projects in the account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rollbar.list-all-projects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-teams\n      description: List all teams in the Rollbar account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rollbar.list-all-teams\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-notification-config\n      description: Get current webhook notification configuration\n      hints:\n        readOnly: true\n        openWorld: false\n      call: rollbar.get-webhook-config\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
