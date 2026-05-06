---
categories: []
consumed_apis: []
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
- retrieve issue
- list releases for a sentry organization with optional filtering by project or version
- list all sentry organizations accessible to the authenticated token
- developer tools
- manage metric and issue alert rules
- list raw error events for a sentry issue including full stack traces. set full=true to get complete stack trace data for debugging.
- update issue status, priority, or assignee
- resolve issue
- list organizations
- retrieve a specific project
- list issues
- list all sentry organizations accessible to the api token
- site reliability engineering
- devops
- list error events bound to a specific issue
- list and inspect sentry organizations
- application performance management
- change the priority of a sentry issue (critical, high, medium, low)
- get full details, stats, and metadata for a specific sentry issue by id
- search and filter sentry issues. use the query parameter with sentry query syntax (e.g., 'is:unresolved assigned:me', 'level:error'). use statsperiod to control the time window (14d, 24h, 1h).
- list all metric and issue alert rules configured for a sentry organization
- create a new sentry release to track a deployment. associate commits for automatic issue attribution. upload source maps separately after release creation.
- list issue events
- retrieve or update a specific issue
- update issue priority
- list organization issues
- assign issue
- assign a sentry issue to a user or team. provide the username or team slug as the assignedto value.
- retrieve raw error events for a specific issue
- observability
- create release
- error monitoring
- update issue
- browse projects within an organization
- list projects
- get details for a specific project
- list releases for a sentry organization
- list all alert rules for a sentry organization
- mark a sentry issue as resolved. sets status to 'resolved'. use when a developer confirms the bug has been fixed and deployed.
- list and filter issues for an organization
- create a new release for deployment tracking
- get detailed information about a specific issue
- retrieve project
- list all projects in a sentry organization
- list releases
- debugging
- track releases and deployments
- get details for a specific sentry project by slug
- list alert rules
- browse and search issues within an organization
slug: error-monitoring
source_filename: error-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Sentry Error Monitoring\n  description: Unified capability for error monitoring, issue triage, release management, and alerting workflows using the\n    Sentry API. Enables DevOps engineers and SREs to investigate production errors, triage and assign issues, track releases,\n    and manage alert rules from a single interface.\n  tags:\n  - Error Monitoring\n  - Debugging\n  - Observability\n  - Application Performance Management\n  - DevOps\n  - Site Reliability Engineering\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SENTRY_AUTH_TOKEN: SENTRY_AUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: sentry-api\n    baseUri: https://sentry.io/api/0\n    description: Sentry REST API for error monitoring and project management\n    authentication:\n      type: bearer\n      token: '{{SENTRY_AUTH_TOKEN}}'\n    resources:\n    - name: organizations\n      path: /organizations/\n    \
  \  description: Organization-level resources and management\n      operations:\n      - name: list-organizations\n        method: GET\n        description: Returns a list of organizations available to the authenticated user\n        inputParameters:\n        - name: member\n          in: query\n          type: boolean\n          required: false\n          description: Restrict results to organizations where user is a member\n        - name: owner\n          in: query\n          type: boolean\n          required: false\n          description: Restrict results to organizations where user is an owner\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: retrieve-organization\n      path: /organizations/{organization_slug}/\n      description: Retrieve details for a specific organization\n      operations:\n      - name: retrieve-organization\n        method: GET\n        description: Returns details for\
  \ a specific organization\n        inputParameters:\n        - name: organization_slug\n          in: path\n          type: string\n          required: true\n          description: Organization slug\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: issues\n      path: /organizations/{organization_slug}/issues/\n      description: Issue management for an organization\n      operations:\n      - name: list-organization-issues\n        method: GET\n        description: Returns a list of issues for the organization\n        inputParameters:\n        - name: organization_slug\n          in: path\n          type: string\n          required: true\n          description: Organization slug\n        - name: query\n          in: query\n          type: string\n          required: false\n          description: Sentry query string (e.g., is:unresolved assigned:me)\n        - name: statsPeriod\n          in: query\n\
  \          type: string\n          required: false\n          description: Time range (e.g., 14d, 24h, 1h)\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results to return (max 100)\n        - name: cursor\n          in: query\n          type: string\n          required: false\n          description: Pagination cursor from previous response\n        - name: sort\n          in: query\n          type: string\n          required: false\n          description: 'Sort order: date, new, priority, freq, user'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: issue\n      path: /organizations/{organization_slug}/issues/{issue_id}/\n      description: Individual issue operations\n      operations:\n      - name: retrieve-issue\n        method: GET\n        description: Returns detailed stats and metadata for a specific issue\n\
  \        inputParameters:\n        - name: organization_slug\n          in: path\n          type: string\n          required: true\n          description: Organization slug\n        - name: issue_id\n          in: path\n          type: string\n          required: true\n          description: Issue ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-issue\n        method: PUT\n        description: Updates attributes of an issue such as status, assignee, or priority\n        inputParameters:\n        - name: organization_slug\n          in: path\n          type: string\n          required: true\n          description: Organization slug\n        - name: issue_id\n          in: path\n          type: string\n          required: true\n          description: Issue ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \        body:\n          type: json\n          data:\n            status: '{{tools.status}}'\n            assignedTo: '{{tools.assigned_to}}'\n            priority: '{{tools.priority}}'\n      - name: delete-issue\n        method: DELETE\n        description: Permanently removes an issue and all associated events\n        inputParameters:\n        - name: organization_slug\n          in: path\n          type: string\n          required: true\n          description: Organization slug\n        - name: issue_id\n          in: path\n          type: string\n          required: true\n          description: Issue ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: issue-events\n      path: /organizations/{organization_slug}/issues/{issue_id}/events/\n      description: Events bound to a specific issue\n      operations:\n      - name: list-issue-events\n        method: GET\n        description: Returns\
  \ a list of error events bound to an issue\n        inputParameters:\n        - name: organization_slug\n          in: path\n          type: string\n          required: true\n          description: Organization slug\n        - name: issue_id\n          in: path\n          type: string\n          required: true\n          description: Issue ID\n        - name: full\n          in: query\n          type: boolean\n          required: false\n          description: Return full event data including stack traces\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects\n      path: /organizations/{organization_slug}/projects/\n      description: Project listing for an organization\n      operations:\n      - name: list-projects\n        method: GET\n        description:\
  \ Returns a list of projects within an organization\n        inputParameters:\n        - name: organization_slug\n          in: path\n          type: string\n          required: true\n          description: Organization slug\n        - name: query\n          in: query\n          type: string\n          required: false\n          description: Filter projects by name\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: project\n      path: /projects/{organization_slug}/{project_slug}/\n      description: Individual project operations\n      operations:\n      - name: retrieve-project\n        method: GET\n        description: Returns details for a specific project\n        inputParameters:\n        - name: organization_slug\n          in: path\n          type:\
  \ string\n          required: true\n          description: Organization slug\n        - name: project_slug\n          in: path\n          type: string\n          required: true\n          description: Project slug\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: releases\n      path: /organizations/{organization_slug}/releases/\n      description: Release management for an organization\n      operations:\n      - name: list-releases\n        method: GET\n        description: Returns a list of releases associated with the organization\n        inputParameters:\n        - name: organization_slug\n          in: path\n          type: string\n          required: true\n          description: Organization slug\n        - name: query\n          in: query\n          type: string\n          required: false\n          description: Filter releases by version string\n        - name: project\n          in: query\n\
  \          type: integer\n          required: false\n          description: Filter by project ID\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-release\n        method: POST\n        description: Creates a new release for tracking deployments and source maps\n        inputParameters:\n        - name: organization_slug\n          in: path\n          type: string\n          required: true\n          description: Organization slug\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            version: '{{tools.version}}'\n            ref: '{{tools.ref}}'\n            url: '{{tools.url}}'\n            projects: '{{tools.projects}}'\n\
  \            dateReleased: '{{tools.date_released}}'\n    - name: alert-rules\n      path: /organizations/{organization_slug}/alert-rules/\n      description: Alert rule management for an organization\n      operations:\n      - name: list-alert-rules\n        method: GET\n        description: Returns all metric and issue alert rules for an organization\n        inputParameters:\n        - name: organization_slug\n          in: path\n          type: string\n          required: true\n          description: Organization slug\n        - name: project\n          in: query\n          type: integer\n          required: false\n          description: Filter by project ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sentry-error-monitoring-api\n    description: Unified REST API for Sentry error monitoring and issue triage workflows.\n    resources:\n    -\
  \ path: /v1/organizations\n      name: organizations\n      description: List and inspect Sentry organizations\n      operations:\n      - method: GET\n        name: list-organizations\n        description: List all Sentry organizations accessible to the API token\n        call: sentry-api.list-organizations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{organization_slug}/issues\n      name: issues\n      description: Browse and search issues within an organization\n      operations:\n      - method: GET\n        name: list-organization-issues\n        description: List and filter issues for an organization\n        call: sentry-api.list-organization-issues\n        with:\n          organization_slug: rest.organization_slug\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{organization_slug}/issues/{issue_id}\n      name: issue\n      description: Retrieve or update a specific\
  \ issue\n      operations:\n      - method: GET\n        name: retrieve-issue\n        description: Get detailed information about a specific issue\n        call: sentry-api.retrieve-issue\n        with:\n          organization_slug: rest.organization_slug\n          issue_id: rest.issue_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-issue\n        description: Update issue status, priority, or assignee\n        call: sentry-api.update-issue\n        with:\n          organization_slug: rest.organization_slug\n          issue_id: rest.issue_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{organization_slug}/issues/{issue_id}/events\n      name: issue-events\n      description: Retrieve raw error events for a specific issue\n      operations:\n      - method: GET\n        name: list-issue-events\n        description: List error events bound to a specific issue\n\
  \        call: sentry-api.list-issue-events\n        with:\n          organization_slug: rest.organization_slug\n          issue_id: rest.issue_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{organization_slug}/projects\n      name: projects\n      description: Browse projects within an organization\n      operations:\n      - method: GET\n        name: list-projects\n        description: List all projects in a Sentry organization\n        call: sentry-api.list-projects\n        with:\n          organization_slug: rest.organization_slug\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{organization_slug}/{project_slug}\n      name: project\n      description: Retrieve a specific project\n      operations:\n      - method: GET\n        name: retrieve-project\n        description: Get details for a specific project\n        call: sentry-api.retrieve-project\n        with:\n   \
  \       organization_slug: rest.organization_slug\n          project_slug: rest.project_slug\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{organization_slug}/releases\n      name: releases\n      description: Track releases and deployments\n      operations:\n      - method: GET\n        name: list-releases\n        description: List releases for a Sentry organization\n        call: sentry-api.list-releases\n        with:\n          organization_slug: rest.organization_slug\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-release\n        description: Create a new release for deployment tracking\n        call: sentry-api.create-release\n        with:\n          organization_slug: rest.organization_slug\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{organization_slug}/alert-rules\n      name: alert-rules\n\
  \      description: Manage metric and issue alert rules\n      operations:\n      - method: GET\n        name: list-alert-rules\n        description: List all alert rules for a Sentry organization\n        call: sentry-api.list-alert-rules\n        with:\n          organization_slug: rest.organization_slug\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: sentry-error-monitoring-mcp\n    transport: http\n    description: MCP server for AI-assisted error monitoring, issue triage, and release tracking with Sentry.\n    tools:\n    - name: list-organizations\n      description: List all Sentry organizations accessible to the authenticated token\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sentry-api.list-organizations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-issues\n      description: Search and filter Sentry issues. Use the query parameter with\
  \ Sentry query syntax (e.g., 'is:unresolved\n        assigned:me', 'level:error'). Use statsPeriod to control the time window (14d, 24h, 1h).\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sentry-api.list-organization-issues\n      with:\n        organization_slug: tools.organization_slug\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retrieve-issue\n      description: Get full details, stats, and metadata for a specific Sentry issue by ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sentry-api.retrieve-issue\n      with:\n        organization_slug: tools.organization_slug\n        issue_id: tools.issue_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: resolve-issue\n      description: Mark a Sentry issue as resolved. Sets status to 'resolved'. Use when a developer confirms the bug has been\n        fixed and deployed.\n      hints:\n        readOnly: false\n\
  \        idempotent: true\n      call: sentry-api.update-issue\n      with:\n        organization_slug: tools.organization_slug\n        issue_id: tools.issue_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: assign-issue\n      description: Assign a Sentry issue to a user or team. Provide the username or team slug as the assignedTo value.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: sentry-api.update-issue\n      with:\n        organization_slug: tools.organization_slug\n        issue_id: tools.issue_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-issue-priority\n      description: Change the priority of a Sentry issue (critical, high, medium, low)\n      hints:\n        readOnly: false\n        idempotent: true\n      call: sentry-api.update-issue\n      with:\n        organization_slug: tools.organization_slug\n        issue_id: tools.issue_id\n      outputParameters:\n    \
  \  - type: object\n        mapping: $.\n    - name: list-issue-events\n      description: List raw error events for a Sentry issue including full stack traces. Set full=true to get complete stack\n        trace data for debugging.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sentry-api.list-issue-events\n      with:\n        organization_slug: tools.organization_slug\n        issue_id: tools.issue_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-projects\n      description: List all projects in a Sentry organization\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sentry-api.list-projects\n      with:\n        organization_slug: tools.organization_slug\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retrieve-project\n      description: Get details for a specific Sentry project by slug\n      hints:\n        readOnly: true\n        idempotent: true\n     \
  \ call: sentry-api.retrieve-project\n      with:\n        organization_slug: tools.organization_slug\n        project_slug: tools.project_slug\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-releases\n      description: List releases for a Sentry organization with optional filtering by project or version\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sentry-api.list-releases\n      with:\n        organization_slug: tools.organization_slug\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-release\n      description: Create a new Sentry release to track a deployment. Associate commits for automatic issue attribution. Upload\n        source maps separately after release creation.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: sentry-api.create-release\n      with:\n        organization_slug: tools.organization_slug\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: list-alert-rules\n      description: List all metric and issue alert rules configured for a Sentry organization\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sentry-api.list-alert-rules\n      with:\n        organization_slug: tools.organization_slug\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
