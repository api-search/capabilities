---
categories: []
consumed_apis: []
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
- remove a webhook trigger from the organization.
- list all organizations
- create a new security automation workflow
- workflow file storage
- list apps
- create a webhook trigger that will start a specified workflow when the webhook url receives an http request (e.g., from a siem alert).
- trigger workflow execution with security event data
- list all security automation workflows
- schedule workflow
- list all available security tool apps
- list app authentications
- list organizations
- get execution history for a workflow
- search the global app library
- abort a running workflow execution
- list all organizations accessible to the authenticated user.
- organization user management
- individual webhook operations
- delete a workflow
- create a new security automation workflow in shuffle. the workflow starts as a draft and can be configured with actions and triggers.
- list all files stored in the shuffle organization file store.
- list all configured app authentication credentials in the organization, showing which tools are connected to shuffle.
- list users
- create notification
- list all users in the organization
- execute a security automation workflow
- get workflow executions
- delete workflow
- list all users in the shuffle organization.
- abort execution
- security automation workflow management
- workflows
- stop a running workflow execution
- trigger execution of a shuffle security automation workflow with optional input data (e.g., alert json, incident details). returns an execution id for status polling.
- security
- list all security tool apps available in the shuffle organization, including built-in apps and custom integrations.
- search for security tool apps by name or category
- create a security notification in the shuffle platform.
- get executions
- incident response
- list notifications
- automation
- list security notifications
- list authentications
- create a webhook trigger to start a workflow from external systems
- create webhook
- list all files in the organization
- get workflow
- execute workflow
- organization management
- create a security notification
- abort a currently running workflow execution. use when a security automation is running incorrectly or needs to be stopped.
- schedule workflows to run on a cron interval
- individual workflow operations
- remove a webhook trigger
- workflow execution history
- get workflow details and configuration
- organization notifications for security events
- delete webhook
- list workflows
- app credential configurations
- get the execution history for a workflow, showing past runs with their status (executing, finished, aborted, failed) and timestamps.
- security tool app integrations
- get the full configuration of a specific shuffle security automation workflow including all actions, triggers, and variables.
- search the shuffle global app library for security tool integrations by name or category (e.g., siem, edr, ticketing).
- open source
- list security notifications in the shuffle organization, filterable by status, type, and severity.
- list all app authentication configurations
- orchestration
- create workflow
- create a scheduled trigger to run a workflow automatically at a specified cron interval (e.g., every hour, daily at midnight).
- list all security automation workflows in the shuffle organization, including their names, descriptions, status, and tags.
- webhook trigger management
- search apps
- soar
- list files
- create a scheduled trigger for a workflow
slug: security-workflow-automation
source_filename: security-workflow-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Shuffle Security Workflow Automation\n  description: Workflow capability for security operations automation using the Shuffle SOAR platform. Enables SOC analysts\n    and security engineers to manage automation workflows, trigger security playbooks, monitor execution status, integrate\n    security tool apps, manage webhooks, and coordinate incident response automation across the security tool stack.\n  tags:\n  - Security\n  - Automation\n  - SOAR\n  - Workflows\n  - Orchestration\n  - Incident Response\n  - Open Source\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SHUFFLE_API_KEY: SHUFFLE_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: shuffle\n    baseUri: https://shuffler.io/api/v1\n    description: Shuffle security automation platform REST API\n    authentication:\n      type: bearer\n      token: '{{SHUFFLE_API_KEY}}'\n    resources:\n    - name: workflows\n      path:\
  \ /workflows\n      description: Security automation workflow management\n      operations:\n      - name: list-workflows\n        method: GET\n        description: List all workflows in the organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-workflow\n        method: POST\n        description: Create a new automation workflow\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n      - name: get-workflow\n        method: GET\n        description: Get workflow details by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Workflow ID\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: delete-workflow\n        method: DELETE\n        description: Delete a workflow by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Workflow ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: execute-workflow\n        method: POST\n        description: Trigger a workflow execution\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Workflow ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            execution_argument: '{{tools.execution_argument}}'\n      - name: get-workflow-executions\n        method:\
  \ GET\n        description: Get execution history for a workflow\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Workflow ID\n        - name: top\n          in: query\n          type: integer\n          required: false\n          description: Number of executions to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: abort-execution\n        method: GET\n        description: Abort a running workflow execution\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Workflow ID\n        - name: exec_id\n          in: path\n          type: string\n          required: true\n          description: Execution ID to abort\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: schedule-workflow\n        method: POST\n        description: Create a scheduled trigger for a workflow\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Workflow ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            frequency: '{{tools.frequency}}'\n            execution_argument: '{{tools.execution_argument}}'\n    - name: apps\n      path: /apps\n      description: Security tool app integrations\n      operations:\n      - name: list-apps\n        method: GET\n        description: List all available apps for the organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: search-apps\n        method: POST\n        description:\
  \ Search the global app library\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n        body:\n          type: json\n          data:\n            search: '{{tools.search}}'\n      - name: list-app-authentications\n        method: GET\n        description: List all app authentication configurations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: triggers\n      path: /hooks\n      description: Webhook triggers for workflow initiation\n      operations:\n      - name: create-webhook\n        method: POST\n        description: Create a webhook trigger for a workflow\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            type: webhook\n            workflow:\
  \ '{{tools.workflow_id}}'\n      - name: delete-webhook\n        method: DELETE\n        description: Remove a webhook trigger\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Webhook ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: files\n      path: /files\n      description: File storage for workflow data\n      operations:\n      - name: list-files\n        method: GET\n        description: List all files in the organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-file\n        method: POST\n        description: Create a file record\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n\
  \          data:\n            filename: '{{tools.filename}}'\n            org_id: '{{tools.org_id}}'\n    - name: notifications\n      path: /notifications\n      description: Organization notification management\n      operations:\n      - name: list-notifications\n        method: GET\n        description: List notifications for the organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-notification\n        method: POST\n        description: Create a notification\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            description: '{{tools.description}}'\n    - name: users\n      path: /users\n      description: User management\n      operations:\n      - name: list-users\n        method: GET\n        description:\
  \ List all users in the organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: organizations\n      path: /orgs\n      description: Organization management\n      operations:\n      - name: list-organizations\n        method: GET\n        description: List all organizations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: get-org-stats\n        method: GET\n        description: Get usage statistics for an organization\n        inputParameters:\n        - name: org_id\n          in: path\n          type: string\n          required: true\n          description: Organization ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: shuffle-security-automation-api\n    description:\
  \ Unified REST API for Shuffle security workflow automation management.\n    resources:\n    - path: /v1/workflows\n      name: workflows\n      description: Security automation workflow management\n      operations:\n      - method: GET\n        name: list-workflows\n        description: List all security automation workflows\n        call: shuffle.list-workflows\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: create-workflow\n        description: Create a new security automation workflow\n        call: shuffle.create-workflow\n        with:\n          name: rest.name\n          description: rest.description\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workflows/{id}\n      name: workflow-detail\n      description: Individual workflow operations\n      operations:\n      - method: GET\n        name: get-workflow\n        description: Get workflow details and configuration\n    \
  \    call: shuffle.get-workflow\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-workflow\n        description: Delete a workflow\n        call: shuffle.delete-workflow\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workflows/{id}/execute\n      name: workflow-execute\n      description: Trigger workflow execution with security event data\n      operations:\n      - method: POST\n        name: execute-workflow\n        description: Execute a security automation workflow\n        call: shuffle.execute-workflow\n        with:\n          id: rest.id\n          execution_argument: rest.execution_argument\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workflows/{id}/executions\n      name: workflow-executions\n      description: Workflow execution history\n  \
  \    operations:\n      - method: GET\n        name: get-executions\n        description: Get execution history for a workflow\n        call: shuffle.get-workflow-executions\n        with:\n          id: rest.id\n          top: rest.top\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/workflows/{id}/executions/{exec_id}/abort\n      name: abort-execution\n      description: Abort a running workflow execution\n      operations:\n      - method: GET\n        name: abort-execution\n        description: Stop a running workflow execution\n        call: shuffle.abort-execution\n        with:\n          id: rest.id\n          exec_id: rest.exec_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workflows/{id}/schedule\n      name: workflow-schedule\n      description: Schedule workflows to run on a cron interval\n      operations:\n      - method: POST\n        name: schedule-workflow\n        description: Create\
  \ a scheduled trigger for a workflow\n        call: shuffle.schedule-workflow\n        with:\n          id: rest.id\n          frequency: rest.frequency\n          execution_argument: rest.execution_argument\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/apps\n      name: apps\n      description: Security tool app integrations\n      operations:\n      - method: GET\n        name: list-apps\n        description: List all available security tool apps\n        call: shuffle.list-apps\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/apps/search\n      name: apps-search\n      description: Search the global app library\n      operations:\n      - method: POST\n        name: search-apps\n        description: Search for security tool apps by name or category\n        call: shuffle.search-apps\n        with:\n          search: rest.search\n        outputParameters:\n        - type: array\n          mapping: $.\n\
  \    - path: /v1/apps/authentications\n      name: app-authentications\n      description: App credential configurations\n      operations:\n      - method: GET\n        name: list-authentications\n        description: List all app authentication configurations\n        call: shuffle.list-app-authentications\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/webhooks\n      name: webhooks\n      description: Webhook trigger management\n      operations:\n      - method: POST\n        name: create-webhook\n        description: Create a webhook trigger to start a workflow from external systems\n        call: shuffle.create-webhook\n        with:\n          name: rest.name\n          workflow_id: rest.workflow_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/webhooks/{id}\n      name: webhook-detail\n      description: Individual webhook operations\n      operations:\n      - method: DELETE\n        name:\
  \ delete-webhook\n        description: Remove a webhook trigger\n        call: shuffle.delete-webhook\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/files\n      name: files\n      description: Workflow file storage\n      operations:\n      - method: GET\n        name: list-files\n        description: List all files in the organization\n        call: shuffle.list-files\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/notifications\n      name: notifications\n      description: Organization notifications for security events\n      operations:\n      - method: GET\n        name: list-notifications\n        description: List security notifications\n        call: shuffle.list-notifications\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: create-notification\n        description: Create a security notification\n\
  \        call: shuffle.create-notification\n        with:\n          title: rest.title\n          description: rest.description\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: Organization user management\n      operations:\n      - method: GET\n        name: list-users\n        description: List all users in the organization\n        call: shuffle.list-users\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/organizations\n      name: organizations\n      description: Organization management\n      operations:\n      - method: GET\n        name: list-organizations\n        description: List all organizations\n        call: shuffle.list-organizations\n        outputParameters:\n        - type: array\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: shuffle-security-automation-mcp\n    transport: http\n    description: MCP server for AI-assisted\
  \ security workflow automation and orchestration.\n    tools:\n    - name: list-workflows\n      description: List all security automation workflows in the Shuffle organization, including their names, descriptions,\n        status, and tags.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: shuffle.list-workflows\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-workflow\n      description: Get the full configuration of a specific Shuffle security automation workflow including all actions, triggers,\n        and variables.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: shuffle.get-workflow\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-workflow\n      description: Create a new security automation workflow in Shuffle. The workflow starts as a draft and can be configured\n        with actions and triggers.\n      hints:\n \
  \       readOnly: false\n        destructive: false\n        idempotent: false\n      call: shuffle.create-workflow\n      with:\n        name: tools.name\n        description: tools.description\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: execute-workflow\n      description: Trigger execution of a Shuffle security automation workflow with optional input data (e.g., alert JSON,\n        incident details). Returns an execution ID for status polling.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: shuffle.execute-workflow\n      with:\n        id: tools.id\n        execution_argument: tools.execution_argument\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-workflow-executions\n      description: Get the execution history for a workflow, showing past runs with their status (EXECUTING, FINISHED, ABORTED,\n        FAILED) and timestamps.\n      hints:\n       \
  \ readOnly: true\n        openWorld: false\n      call: shuffle.get-workflow-executions\n      with:\n        id: tools.id\n        top: tools.top\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: abort-execution\n      description: Abort a currently running workflow execution. Use when a security automation is running incorrectly or\n        needs to be stopped.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: shuffle.abort-execution\n      with:\n        id: tools.id\n        exec_id: tools.exec_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: schedule-workflow\n      description: Create a scheduled trigger to run a workflow automatically at a specified cron interval (e.g., every hour,\n        daily at midnight).\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: shuffle.schedule-workflow\n      with:\n     \
  \   id: tools.id\n        frequency: tools.frequency\n        execution_argument: tools.execution_argument\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-apps\n      description: List all security tool apps available in the Shuffle organization, including built-in apps and custom integrations.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: shuffle.list-apps\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: search-apps\n      description: Search the Shuffle global app library for security tool integrations by name or category (e.g., SIEM, EDR,\n        ticketing).\n      hints:\n        readOnly: true\n        openWorld: true\n      call: shuffle.search-apps\n      with:\n        search: tools.search\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: list-app-authentications\n      description: List all configured app authentication credentials in the organization,\
  \ showing which tools are connected\n        to Shuffle.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: shuffle.list-app-authentications\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: create-webhook\n      description: Create a webhook trigger that will start a specified workflow when the webhook URL receives an HTTP request\n        (e.g., from a SIEM alert).\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: shuffle.create-webhook\n      with:\n        name: tools.name\n        workflow_id: tools.workflow_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-webhook\n      description: Remove a webhook trigger from the organization.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: shuffle.delete-webhook\n      with:\n        id: tools.id\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: list-notifications\n      description: List security notifications in the Shuffle organization, filterable by status, type, and severity.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: shuffle.list-notifications\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: create-notification\n      description: Create a security notification in the Shuffle platform.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: shuffle.create-notification\n      with:\n        title: tools.title\n        description: tools.description\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-users\n      description: List all users in the Shuffle organization.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: shuffle.list-users\n      outputParameters:\n      - type: array\n        mapping: $.\n  \
  \  - name: list-files\n      description: List all files stored in the Shuffle organization file store.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: shuffle.list-files\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: list-organizations\n      description: List all organizations accessible to the authenticated user.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: shuffle.list-organizations\n      outputParameters:\n      - type: array\n        mapping: $.\n"
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
