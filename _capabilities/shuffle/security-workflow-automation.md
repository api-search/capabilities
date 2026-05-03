---
api_specs:
- filename: shuffle-openapi.yml
  format: yaml
  label: shuffle
  slug: shuffle
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/shuffle/refs/heads/main/openapi/shuffle-openapi.yml
categories: []
consumed_apis:
- shuffle
description: Workflow capability for security operations automation using the Shuffle SOAR platform. Enables SOC analysts and security engineers to manage automation workflows, trigger security playbooks, monitor execution status, integrate security tool apps, manage webhooks, and coordinate incident response automation across the security tool stack.
layout: capability
name: Shuffle Security Workflow Automation
operations:
- description: List all security automation workflows
  method: GET
  name: list-workflows
  path: /v1/workflows
- description: Create a new security automation workflow
  method: POST
  name: create-workflow
  path: /v1/workflows
- description: Get workflow details and configuration
  method: GET
  name: get-workflow
  path: /v1/workflows/{id}
- description: Delete a workflow
  method: DELETE
  name: delete-workflow
  path: /v1/workflows/{id}
- description: Execute a security automation workflow
  method: POST
  name: execute-workflow
  path: /v1/workflows/{id}/execute
- description: Get execution history for a workflow
  method: GET
  name: get-executions
  path: /v1/workflows/{id}/executions
- description: Stop a running workflow execution
  method: GET
  name: abort-execution
  path: /v1/workflows/{id}/executions/{exec_id}/abort
- description: Create a scheduled trigger for a workflow
  method: POST
  name: schedule-workflow
  path: /v1/workflows/{id}/schedule
- description: List all available security tool apps
  method: GET
  name: list-apps
  path: /v1/apps
- description: Search for security tool apps by name or category
  method: POST
  name: search-apps
  path: /v1/apps/search
- description: List all app authentication configurations
  method: GET
  name: list-authentications
  path: /v1/apps/authentications
- description: Create a webhook trigger to start a workflow from external systems
  method: POST
  name: create-webhook
  path: /v1/webhooks
- description: Remove a webhook trigger
  method: DELETE
  name: delete-webhook
  path: /v1/webhooks/{id}
- description: List all files in the organization
  method: GET
  name: list-files
  path: /v1/files
- description: List security notifications
  method: GET
  name: list-notifications
  path: /v1/notifications
- description: Create a security notification
  method: POST
  name: create-notification
  path: /v1/notifications
- description: List all users in the organization
  method: GET
  name: list-users
  path: /v1/users
- description: List all organizations
  method: GET
  name: list-organizations
  path: /v1/organizations
personas: []
provider_name: Shuffle
provider_slug: shuffle
search_terms:
- create a webhook trigger that will start a specified workflow when the webhook url receives an http request (e.g., from a siem alert).
- list apps
- security
- list security notifications
- create a security notification
- create a new security automation workflow
- schedule workflow
- individual workflow operations
- webhook trigger management
- trigger workflow execution with security event data
- stop a running workflow execution
- list all users in the shuffle organization.
- workflows
- list files
- create a scheduled trigger for a workflow
- list all app authentication configurations
- list authentications
- abort a running workflow execution
- list organizations
- list security notifications in the shuffle organization, filterable by status, type, and severity.
- execute a security automation workflow
- orchestration
- security tool app integrations
- list all users in the organization
- create a new security automation workflow in shuffle. the workflow starts as a draft and can be configured with actions and triggers.
- soar
- organization user management
- automation
- create a webhook trigger to start a workflow from external systems
- open source
- delete a workflow
- organization notifications for security events
- individual webhook operations
- get the execution history for a workflow, showing past runs with their status (executing, finished, aborted, failed) and timestamps.
- get executions
- search apps
- remove a webhook trigger from the organization.
- list all files in the organization
- get workflow executions
- list all files stored in the shuffle organization file store.
- list all security tool apps available in the shuffle organization, including built-in apps and custom integrations.
- get workflow details and configuration
- app credential configurations
- list all security automation workflows in the shuffle organization, including their names, descriptions, status, and tags.
- create a security notification in the shuffle platform.
- get execution history for a workflow
- list app authentications
- get workflow
- incident response
- abort a currently running workflow execution. use when a security automation is running incorrectly or needs to be stopped.
- delete workflow
- workflow execution history
- get the full configuration of a specific shuffle security automation workflow including all actions, triggers, and variables.
- trigger execution of a shuffle security automation workflow with optional input data (e.g., alert json, incident details). returns an execution id for status polling.
- delete webhook
- workflow file storage
- abort execution
- remove a webhook trigger
- organization management
- create webhook
- create workflow
- list workflows
- search for security tool apps by name or category
- list all configured app authentication credentials in the organization, showing which tools are connected to shuffle.
- execute workflow
- schedule workflows to run on a cron interval
- search the global app library
- search the shuffle global app library for security tool integrations by name or category (e.g., siem, edr, ticketing).
- list all organizations
- list notifications
- security automation workflow management
- list users
- create notification
- list all organizations accessible to the authenticated user.
- list all available security tool apps
- list all security automation workflows
- create a scheduled trigger to run a workflow automatically at a specified cron interval (e.g., every hour, daily at midnight).
slug: security-workflow-automation
source_filename: security-workflow-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Shuffle Security Workflow Automation\"\n  description: >-\n    Workflow capability for security operations automation using the Shuffle SOAR\n    platform. Enables SOC analysts and security engineers to manage automation\n    workflows, trigger security playbooks, monitor execution status, integrate\n    security tool apps, manage webhooks, and coordinate incident response\n    automation across the security tool stack.\n  tags:\n    - Security\n    - Automation\n    - SOAR\n    - Workflows\n    - Orchestration\n    - Incident Response\n    - Open Source\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SHUFFLE_API_KEY: SHUFFLE_API_KEY\n\ncapability:\n  consumes:\n    - import: shuffle\n      location: ./shared/shuffle.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: shuffle-security-automation-api\n      description: \"Unified REST API for Shuffle security\
  \ workflow automation management.\"\n      resources:\n        - path: /v1/workflows\n          name: workflows\n          description: Security automation workflow management\n          operations:\n            - method: GET\n              name: list-workflows\n              description: List all security automation workflows\n              call: \"shuffle.list-workflows\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-workflow\n              description: Create a new security automation workflow\n              call: \"shuffle.create-workflow\"\n              with:\n                name: \"rest.name\"\n                description: \"rest.description\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/workflows/{id}\n          name: workflow-detail\n          description: Individual workflow operations\n   \
  \       operations:\n            - method: GET\n              name: get-workflow\n              description: Get workflow details and configuration\n              call: \"shuffle.get-workflow\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-workflow\n              description: Delete a workflow\n              call: \"shuffle.delete-workflow\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/workflows/{id}/execute\n          name: workflow-execute\n          description: Trigger workflow execution with security event data\n          operations:\n            - method: POST\n              name: execute-workflow\n              description: Execute a security automation workflow\n              call: \"\
  shuffle.execute-workflow\"\n              with:\n                id: \"rest.id\"\n                execution_argument: \"rest.execution_argument\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/workflows/{id}/executions\n          name: workflow-executions\n          description: Workflow execution history\n          operations:\n            - method: GET\n              name: get-executions\n              description: Get execution history for a workflow\n              call: \"shuffle.get-workflow-executions\"\n              with:\n                id: \"rest.id\"\n                top: \"rest.top\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/workflows/{id}/executions/{exec_id}/abort\n          name: abort-execution\n          description: Abort a running workflow execution\n          operations:\n            - method: GET\n            \
  \  name: abort-execution\n              description: Stop a running workflow execution\n              call: \"shuffle.abort-execution\"\n              with:\n                id: \"rest.id\"\n                exec_id: \"rest.exec_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/workflows/{id}/schedule\n          name: workflow-schedule\n          description: Schedule workflows to run on a cron interval\n          operations:\n            - method: POST\n              name: schedule-workflow\n              description: Create a scheduled trigger for a workflow\n              call: \"shuffle.schedule-workflow\"\n              with:\n                id: \"rest.id\"\n                frequency: \"rest.frequency\"\n                execution_argument: \"rest.execution_argument\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/apps\n         \
  \ name: apps\n          description: Security tool app integrations\n          operations:\n            - method: GET\n              name: list-apps\n              description: List all available security tool apps\n              call: \"shuffle.list-apps\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/apps/search\n          name: apps-search\n          description: Search the global app library\n          operations:\n            - method: POST\n              name: search-apps\n              description: Search for security tool apps by name or category\n              call: \"shuffle.search-apps\"\n              with:\n                search: \"rest.search\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/apps/authentications\n          name: app-authentications\n          description: App credential configurations\n          operations:\n\
  \            - method: GET\n              name: list-authentications\n              description: List all app authentication configurations\n              call: \"shuffle.list-app-authentications\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/webhooks\n          name: webhooks\n          description: Webhook trigger management\n          operations:\n            - method: POST\n              name: create-webhook\n              description: Create a webhook trigger to start a workflow from external systems\n              call: \"shuffle.create-webhook\"\n              with:\n                name: \"rest.name\"\n                workflow_id: \"rest.workflow_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/webhooks/{id}\n          name: webhook-detail\n          description: Individual webhook operations\n          operations:\n       \
  \     - method: DELETE\n              name: delete-webhook\n              description: Remove a webhook trigger\n              call: \"shuffle.delete-webhook\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/files\n          name: files\n          description: Workflow file storage\n          operations:\n            - method: GET\n              name: list-files\n              description: List all files in the organization\n              call: \"shuffle.list-files\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/notifications\n          name: notifications\n          description: Organization notifications for security events\n          operations:\n            - method: GET\n              name: list-notifications\n              description: List security notifications\n             \
  \ call: \"shuffle.list-notifications\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-notification\n              description: Create a security notification\n              call: \"shuffle.create-notification\"\n              with:\n                title: \"rest.title\"\n                description: \"rest.description\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/users\n          name: users\n          description: Organization user management\n          operations:\n            - method: GET\n              name: list-users\n              description: List all users in the organization\n              call: \"shuffle.list-users\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/organizations\n          name: organizations\n       \
  \   description: Organization management\n          operations:\n            - method: GET\n              name: list-organizations\n              description: List all organizations\n              call: \"shuffle.list-organizations\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: shuffle-security-automation-mcp\n      transport: http\n      description: \"MCP server for AI-assisted security workflow automation and orchestration.\"\n      tools:\n        - name: list-workflows\n          description: >-\n            List all security automation workflows in the Shuffle organization,\n            including their names, descriptions, status, and tags.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"shuffle.list-workflows\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: get-workflow\n\
  \          description: >-\n            Get the full configuration of a specific Shuffle security automation\n            workflow including all actions, triggers, and variables.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"shuffle.get-workflow\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-workflow\n          description: >-\n            Create a new security automation workflow in Shuffle. The workflow\n            starts as a draft and can be configured with actions and triggers.\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"shuffle.create-workflow\"\n          with:\n            name: \"tools.name\"\n            description: \"tools.description\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n\
  \        - name: execute-workflow\n          description: >-\n            Trigger execution of a Shuffle security automation workflow with\n            optional input data (e.g., alert JSON, incident details). Returns\n            an execution ID for status polling.\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"shuffle.execute-workflow\"\n          with:\n            id: \"tools.id\"\n            execution_argument: \"tools.execution_argument\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-workflow-executions\n          description: >-\n            Get the execution history for a workflow, showing past runs with\n            their status (EXECUTING, FINISHED, ABORTED, FAILED) and timestamps.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"shuffle.get-workflow-executions\"\n          with:\n   \
  \         id: \"tools.id\"\n            top: \"tools.top\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: abort-execution\n          description: >-\n            Abort a currently running workflow execution. Use when a security\n            automation is running incorrectly or needs to be stopped.\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"shuffle.abort-execution\"\n          with:\n            id: \"tools.id\"\n            exec_id: \"tools.exec_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: schedule-workflow\n          description: >-\n            Create a scheduled trigger to run a workflow automatically at a\n            specified cron interval (e.g., every hour, daily at midnight).\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent:\
  \ false\n          call: \"shuffle.schedule-workflow\"\n          with:\n            id: \"tools.id\"\n            frequency: \"tools.frequency\"\n            execution_argument: \"tools.execution_argument\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-apps\n          description: >-\n            List all security tool apps available in the Shuffle organization,\n            including built-in apps and custom integrations.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"shuffle.list-apps\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: search-apps\n          description: >-\n            Search the Shuffle global app library for security tool integrations\n            by name or category (e.g., SIEM, EDR, ticketing).\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"shuffle.search-apps\"\
  \n          with:\n            search: \"tools.search\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: list-app-authentications\n          description: >-\n            List all configured app authentication credentials in the organization,\n            showing which tools are connected to Shuffle.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"shuffle.list-app-authentications\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: create-webhook\n          description: >-\n            Create a webhook trigger that will start a specified workflow when\n            the webhook URL receives an HTTP request (e.g., from a SIEM alert).\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"shuffle.create-webhook\"\n          with:\n            name: \"tools.name\"\
  \n            workflow_id: \"tools.workflow_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-webhook\n          description: Remove a webhook trigger from the organization.\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"shuffle.delete-webhook\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-notifications\n          description: >-\n            List security notifications in the Shuffle organization, filterable\n            by status, type, and severity.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"shuffle.list-notifications\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: create-notification\n          description: Create\
  \ a security notification in the Shuffle platform.\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"shuffle.create-notification\"\n          with:\n            title: \"tools.title\"\n            description: \"tools.description\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-users\n          description: List all users in the Shuffle organization.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"shuffle.list-users\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: list-files\n          description: List all files stored in the Shuffle organization file store.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"shuffle.list-files\"\n          outputParameters:\n            - type: array\n          \
  \    mapping: \"$.\"\n\n        - name: list-organizations\n          description: List all organizations accessible to the authenticated user.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"shuffle.list-organizations\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/shuffle/refs/heads/main/capabilities/security-workflow-automation.yaml
tags:
- Security
- Automation
- SOAR
- Workflows
- Orchestration
- Incident Response
- Open Source
tools:
- description: List all security automation workflows in the Shuffle organization, including their names, descriptions, status, and tags.
  hints:
    openWorld: false
    readOnly: true
  name: list-workflows
- description: Get the full configuration of a specific Shuffle security automation workflow including all actions, triggers, and variables.
  hints:
    openWorld: false
    readOnly: true
  name: get-workflow
- description: Create a new security automation workflow in Shuffle. The workflow starts as a draft and can be configured with actions and triggers.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-workflow
- description: Trigger execution of a Shuffle security automation workflow with optional input data (e.g., alert JSON, incident details). Returns an execution ID for status polling.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: execute-workflow
- description: Get the execution history for a workflow, showing past runs with their status (EXECUTING, FINISHED, ABORTED, FAILED) and timestamps.
  hints:
    openWorld: false
    readOnly: true
  name: get-workflow-executions
- description: Abort a currently running workflow execution. Use when a security automation is running incorrectly or needs to be stopped.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: abort-execution
- description: Create a scheduled trigger to run a workflow automatically at a specified cron interval (e.g., every hour, daily at midnight).
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: schedule-workflow
- description: List all security tool apps available in the Shuffle organization, including built-in apps and custom integrations.
  hints:
    openWorld: false
    readOnly: true
  name: list-apps
- description: Search the Shuffle global app library for security tool integrations by name or category (e.g., SIEM, EDR, ticketing).
  hints:
    openWorld: true
    readOnly: true
  name: search-apps
- description: List all configured app authentication credentials in the organization, showing which tools are connected to Shuffle.
  hints:
    openWorld: false
    readOnly: true
  name: list-app-authentications
- description: Create a webhook trigger that will start a specified workflow when the webhook URL receives an HTTP request (e.g., from a SIEM alert).
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-webhook
- description: Remove a webhook trigger from the organization.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-webhook
- description: List security notifications in the Shuffle organization, filterable by status, type, and severity.
  hints:
    openWorld: false
    readOnly: true
  name: list-notifications
- description: Create a security notification in the Shuffle platform.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-notification
- description: List all users in the Shuffle organization.
  hints:
    openWorld: false
    readOnly: true
  name: list-users
- description: List all files stored in the Shuffle organization file store.
  hints:
    openWorld: false
    readOnly: true
  name: list-files
- description: List all organizations accessible to the authenticated user.
  hints:
    openWorld: false
    readOnly: true
  name: list-organizations
---
