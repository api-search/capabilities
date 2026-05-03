---
api_specs:
- filename: sentry-api-openapi.yml
  format: yaml
  label: sentry-api
  slug: sentry-api
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/sentry/refs/heads/main/openapi/sentry-api-openapi.yml
categories: []
consumed_apis:
- sentry-api
description: Unified capability for error monitoring, issue triage, release management, and alerting workflows using the Sentry API. Enables DevOps engineers and SREs to investigate production errors, triage and assign issues, track releases, and manage alert rules from a single interface.
layout: capability
name: Sentry Error Monitoring
operations:
- description: List all Sentry organizations accessible to the API token
  method: GET
  name: list-organizations
  path: /v1/organizations
- description: List and filter issues for an organization
  method: GET
  name: list-organization-issues
  path: /v1/organizations/{organization_slug}/issues
- description: Get detailed information about a specific issue
  method: GET
  name: retrieve-issue
  path: /v1/organizations/{organization_slug}/issues/{issue_id}
- description: Update issue status, priority, or assignee
  method: PUT
  name: update-issue
  path: /v1/organizations/{organization_slug}/issues/{issue_id}
- description: List error events bound to a specific issue
  method: GET
  name: list-issue-events
  path: /v1/organizations/{organization_slug}/issues/{issue_id}/events
- description: List all projects in a Sentry organization
  method: GET
  name: list-projects
  path: /v1/organizations/{organization_slug}/projects
- description: Get details for a specific project
  method: GET
  name: retrieve-project
  path: /v1/projects/{organization_slug}/{project_slug}
- description: List releases for a Sentry organization
  method: GET
  name: list-releases
  path: /v1/organizations/{organization_slug}/releases
- description: Create a new release for deployment tracking
  method: POST
  name: create-release
  path: /v1/organizations/{organization_slug}/releases
- description: List all alert rules for a Sentry organization
  method: GET
  name: list-alert-rules
  path: /v1/organizations/{organization_slug}/alert-rules
personas: []
provider_name: Sentry
provider_slug: sentry
search_terms:
- search and filter sentry issues. use the query parameter with sentry query syntax (e.g., 'is:unresolved assigned:me', 'level:error'). use statsperiod to control the time window (14d, 24h, 1h).
- list alert rules
- site reliability engineering
- mark a sentry issue as resolved. sets status to 'resolved'. use when a developer confirms the bug has been fixed and deployed.
- browse projects within an organization
- list projects
- list and inspect sentry organizations
- update issue status, priority, or assignee
- list all projects in a sentry organization
- list releases for a sentry organization with optional filtering by project or version
- debugging
- track releases and deployments
- manage metric and issue alert rules
- retrieve a specific project
- create a new sentry release to track a deployment. associate commits for automatic issue attribution. upload source maps separately after release creation.
- list and filter issues for an organization
- get full details, stats, and metadata for a specific sentry issue by id
- retrieve raw error events for a specific issue
- update issue
- assign issue
- list raw error events for a sentry issue including full stack traces. set full=true to get complete stack trace data for debugging.
- get detailed information about a specific issue
- list error events bound to a specific issue
- get details for a specific project
- list releases
- developer tools
- retrieve or update a specific issue
- list all sentry organizations accessible to the authenticated token
- resolve issue
- assign a sentry issue to a user or team. provide the username or team slug as the assignedto value.
- create release
- update issue priority
- list organizations
- get details for a specific sentry project by slug
- retrieve issue
- retrieve project
- application performance management
- observability
- list issue events
- error monitoring
- change the priority of a sentry issue (critical, high, medium, low)
- create a new release for deployment tracking
- list all metric and issue alert rules configured for a sentry organization
- list all sentry organizations accessible to the api token
- browse and search issues within an organization
- list releases for a sentry organization
- devops
- list all alert rules for a sentry organization
- list organization issues
- list issues
slug: error-monitoring
source_filename: error-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Sentry Error Monitoring\"\n  description: >-\n    Unified capability for error monitoring, issue triage, release management,\n    and alerting workflows using the Sentry API. Enables DevOps engineers and\n    SREs to investigate production errors, triage and assign issues, track\n    releases, and manage alert rules from a single interface.\n  tags:\n    - Error Monitoring\n    - Debugging\n    - Observability\n    - Application Performance Management\n    - DevOps\n    - Site Reliability Engineering\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SENTRY_AUTH_TOKEN: SENTRY_AUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: sentry-api\n      location: ./shared/sentry-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sentry-error-monitoring-api\n      description: \"Unified REST API for Sentry error monitoring and issue triage workflows.\"\n    \
  \  resources:\n        - path: /v1/organizations\n          name: organizations\n          description: \"List and inspect Sentry organizations\"\n          operations:\n            - method: GET\n              name: list-organizations\n              description: \"List all Sentry organizations accessible to the API token\"\n              call: \"sentry-api.list-organizations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/organizations/{organization_slug}/issues\n          name: issues\n          description: \"Browse and search issues within an organization\"\n          operations:\n            - method: GET\n              name: list-organization-issues\n              description: \"List and filter issues for an organization\"\n              call: \"sentry-api.list-organization-issues\"\n              with:\n                organization_slug: \"rest.organization_slug\"\n              outputParameters:\n    \
  \            - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/organizations/{organization_slug}/issues/{issue_id}\n          name: issue\n          description: \"Retrieve or update a specific issue\"\n          operations:\n            - method: GET\n              name: retrieve-issue\n              description: \"Get detailed information about a specific issue\"\n              call: \"sentry-api.retrieve-issue\"\n              with:\n                organization_slug: \"rest.organization_slug\"\n                issue_id: \"rest.issue_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-issue\n              description: \"Update issue status, priority, or assignee\"\n              call: \"sentry-api.update-issue\"\n              with:\n                organization_slug: \"rest.organization_slug\"\n                issue_id: \"rest.issue_id\"\n             \
  \ outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/organizations/{organization_slug}/issues/{issue_id}/events\n          name: issue-events\n          description: \"Retrieve raw error events for a specific issue\"\n          operations:\n            - method: GET\n              name: list-issue-events\n              description: \"List error events bound to a specific issue\"\n              call: \"sentry-api.list-issue-events\"\n              with:\n                organization_slug: \"rest.organization_slug\"\n                issue_id: \"rest.issue_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/organizations/{organization_slug}/projects\n          name: projects\n          description: \"Browse projects within an organization\"\n          operations:\n            - method: GET\n              name: list-projects\n              description: \"List\
  \ all projects in a Sentry organization\"\n              call: \"sentry-api.list-projects\"\n              with:\n                organization_slug: \"rest.organization_slug\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{organization_slug}/{project_slug}\n          name: project\n          description: \"Retrieve a specific project\"\n          operations:\n            - method: GET\n              name: retrieve-project\n              description: \"Get details for a specific project\"\n              call: \"sentry-api.retrieve-project\"\n              with:\n                organization_slug: \"rest.organization_slug\"\n                project_slug: \"rest.project_slug\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/organizations/{organization_slug}/releases\n          name: releases\n          description: \"Track releases\
  \ and deployments\"\n          operations:\n            - method: GET\n              name: list-releases\n              description: \"List releases for a Sentry organization\"\n              call: \"sentry-api.list-releases\"\n              with:\n                organization_slug: \"rest.organization_slug\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-release\n              description: \"Create a new release for deployment tracking\"\n              call: \"sentry-api.create-release\"\n              with:\n                organization_slug: \"rest.organization_slug\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/organizations/{organization_slug}/alert-rules\n          name: alert-rules\n          description: \"Manage metric and issue alert rules\"\n          operations:\n            - method: GET\n\
  \              name: list-alert-rules\n              description: \"List all alert rules for a Sentry organization\"\n              call: \"sentry-api.list-alert-rules\"\n              with:\n                organization_slug: \"rest.organization_slug\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: sentry-error-monitoring-mcp\n      transport: http\n      description: \"MCP server for AI-assisted error monitoring, issue triage, and release tracking with Sentry.\"\n      tools:\n        - name: list-organizations\n          description: \"List all Sentry organizations accessible to the authenticated token\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sentry-api.list-organizations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-issues\n          description: >-\n  \
  \          Search and filter Sentry issues. Use the query parameter with Sentry\n            query syntax (e.g., 'is:unresolved assigned:me', 'level:error'). Use\n            statsPeriod to control the time window (14d, 24h, 1h).\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sentry-api.list-organization-issues\"\n          with:\n            organization_slug: \"tools.organization_slug\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: retrieve-issue\n          description: \"Get full details, stats, and metadata for a specific Sentry issue by ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sentry-api.retrieve-issue\"\n          with:\n            organization_slug: \"tools.organization_slug\"\n            issue_id: \"tools.issue_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n    \
  \    - name: resolve-issue\n          description: >-\n            Mark a Sentry issue as resolved. Sets status to 'resolved'. Use when\n            a developer confirms the bug has been fixed and deployed.\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"sentry-api.update-issue\"\n          with:\n            organization_slug: \"tools.organization_slug\"\n            issue_id: \"tools.issue_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: assign-issue\n          description: >-\n            Assign a Sentry issue to a user or team. Provide the username or team\n            slug as the assignedTo value.\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"sentry-api.update-issue\"\n          with:\n            organization_slug: \"tools.organization_slug\"\n            issue_id: \"tools.issue_id\"\n          outputParameters:\n       \
  \     - type: object\n              mapping: \"$.\"\n\n        - name: update-issue-priority\n          description: \"Change the priority of a Sentry issue (critical, high, medium, low)\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"sentry-api.update-issue\"\n          with:\n            organization_slug: \"tools.organization_slug\"\n            issue_id: \"tools.issue_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-issue-events\n          description: >-\n            List raw error events for a Sentry issue including full stack traces.\n            Set full=true to get complete stack trace data for debugging.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sentry-api.list-issue-events\"\n          with:\n            organization_slug: \"tools.organization_slug\"\n            issue_id: \"tools.issue_id\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: list-projects\n          description: \"List all projects in a Sentry organization\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sentry-api.list-projects\"\n          with:\n            organization_slug: \"tools.organization_slug\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: retrieve-project\n          description: \"Get details for a specific Sentry project by slug\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sentry-api.retrieve-project\"\n          with:\n            organization_slug: \"tools.organization_slug\"\n            project_slug: \"tools.project_slug\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-releases\n          description: \"List releases for a Sentry organization\
  \ with optional filtering by project or version\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sentry-api.list-releases\"\n          with:\n            organization_slug: \"tools.organization_slug\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-release\n          description: >-\n            Create a new Sentry release to track a deployment. Associate commits\n            for automatic issue attribution. Upload source maps separately after\n            release creation.\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"sentry-api.create-release\"\n          with:\n            organization_slug: \"tools.organization_slug\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-alert-rules\n          description: \"List all metric and issue alert rules configured for a\
  \ Sentry organization\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sentry-api.list-alert-rules\"\n          with:\n            organization_slug: \"tools.organization_slug\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sentry/refs/heads/main/capabilities/error-monitoring.yaml
tags:
- Error Monitoring
- Debugging
- Observability
- Application Performance Management
- DevOps
- Site Reliability Engineering
tools:
- description: List all Sentry organizations accessible to the authenticated token
  hints:
    idempotent: true
    readOnly: true
  name: list-organizations
- description: Search and filter Sentry issues. Use the query parameter with Sentry query syntax (e.g., 'is:unresolved assigned:me', 'level:error'). Use statsPeriod to control the time window (14d, 24h, 1h).
  hints:
    idempotent: true
    readOnly: true
  name: list-issues
- description: Get full details, stats, and metadata for a specific Sentry issue by ID
  hints:
    idempotent: true
    readOnly: true
  name: retrieve-issue
- description: Mark a Sentry issue as resolved. Sets status to 'resolved'. Use when a developer confirms the bug has been fixed and deployed.
  hints:
    idempotent: true
    readOnly: false
  name: resolve-issue
- description: Assign a Sentry issue to a user or team. Provide the username or team slug as the assignedTo value.
  hints:
    idempotent: true
    readOnly: false
  name: assign-issue
- description: Change the priority of a Sentry issue (critical, high, medium, low)
  hints:
    idempotent: true
    readOnly: false
  name: update-issue-priority
- description: List raw error events for a Sentry issue including full stack traces. Set full=true to get complete stack trace data for debugging.
  hints:
    idempotent: true
    readOnly: true
  name: list-issue-events
- description: List all projects in a Sentry organization
  hints:
    idempotent: true
    readOnly: true
  name: list-projects
- description: Get details for a specific Sentry project by slug
  hints:
    idempotent: true
    readOnly: true
  name: retrieve-project
- description: List releases for a Sentry organization with optional filtering by project or version
  hints:
    idempotent: true
    readOnly: true
  name: list-releases
- description: Create a new Sentry release to track a deployment. Associate commits for automatic issue attribution. Upload source maps separately after release creation.
  hints:
    idempotent: false
    readOnly: false
  name: create-release
- description: List all metric and issue alert rules configured for a Sentry organization
  hints:
    idempotent: true
    readOnly: true
  name: list-alert-rules
---
