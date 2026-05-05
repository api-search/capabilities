---
api_specs:
- filename: trigger-dev-management-openapi.yml
  format: yaml
  label: trigger-dev
  slug: trigger-dev
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/trigger-dev/refs/heads/main/openapi/trigger-dev-management-openapi.yml
categories: []
consumed_apis:
- trigger-dev
description: Unified workflow automation capability combining task triggering, run monitoring, schedule management, queue control, and waitpoint orchestration. Powers AI agent pipelines, background job platforms, and human-in-the-loop approval workflows.
layout: capability
name: Trigger.dev Workflow Automation
operations:
- description: Trigger a task run with payload and options
  method: POST
  name: trigger-task
  path: /v1/tasks/{taskIdentifier}/trigger
- description: Trigger multiple tasks in a single batch
  method: POST
  name: batch-trigger-tasks
  path: /v1/tasks/batch
- description: List runs with filtering
  method: GET
  name: list-runs
  path: /v1/runs
- description: Get run details, status, and output
  method: GET
  name: get-run
  path: /v1/runs/{runId}
- description: Cancel a queued or executing run
  method: POST
  name: cancel-run
  path: /v1/runs/{runId}/cancel
- description: Replay a run with the same payload
  method: POST
  name: replay-run
  path: /v1/runs/{runId}/replay
- description: List all configured schedules
  method: GET
  name: list-schedules
  path: /v1/schedules
- description: Create a cron schedule
  method: POST
  name: create-schedule
  path: /v1/schedules
- description: List all task queues
  method: GET
  name: list-queues
  path: /v1/queues
- description: Pause a queue
  method: POST
  name: pause-queue
  path: /v1/queues/{queueName}/pause
- description: Resume a paused queue
  method: POST
  name: resume-queue
  path: /v1/queues/{queueName}/resume
- description: Create a waitpoint token for human-in-the-loop approval
  method: POST
  name: create-waitpoint-token
  path: /v1/waitpoints
- description: Complete a waitpoint to resume the waiting run
  method: POST
  name: complete-waitpoint-token
  path: /v1/waitpoints/{tokenId}/complete
personas: []
provider_name: Trigger.dev
provider_slug: trigger-dev
search_terms:
- pause a queue
- create schedule
- create a waitpoint token for a human-in-the-loop approval workflow
- complete a waitpoint to resume a paused run with approval data
- list runs with filtering
- workflow automation
- schedule management
- pause queue
- cancel a queued or currently executing run
- replay a run
- list schedules
- trigger multiple task runs in a single batch request
- list task runs, filterable by status, tags, or task identifier
- get run
- cancel run
- list all configured task schedules with their cron expressions
- open source
- list all task queues with their current depth and concurrency
- individual run details
- scheduling
- create a cron schedule
- task management
- complete a waitpoint to resume the waiting run
- trigger a background task with a payload
- pause a queue to prevent new runs from starting
- resume a paused queue to allow runs to execute
- developer-first
- background jobs
- trigger.dev
- list all task queues
- replay run
- queue resume control
- ai agents
- trigger a task run with payload and options
- create a new cron schedule to run a task automatically
- waitpoint token management
- get run details, status, and output
- cancel a run
- list runs
- trigger a background task
- list all configured schedules
- queue monitoring and control
- list queues
- create waitpoint token
- typescript
- batch trigger multiple task runs
- replay a run with the same payload
- complete waitpoint token
- trigger multiple tasks in a single batch
- resume queue
- get detailed status, output, and metadata for a specific run
- queue pause control
- replay a completed run with the original payload
- queue management
- create a waitpoint token for human-in-the-loop approval
- complete a waitpoint
- trigger task
- resume a paused queue
- run listing and monitoring
- batch trigger tasks
- cancel a queued or executing run
slug: workflow-automation
source_filename: workflow-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Trigger.dev Workflow Automation\"\n  description: >-\n    Unified workflow automation capability combining task triggering, run monitoring,\n    schedule management, queue control, and waitpoint orchestration. Powers AI agent\n    pipelines, background job platforms, and human-in-the-loop approval workflows.\n  tags:\n    - Trigger.dev\n    - Workflow Automation\n    - Background Jobs\n    - Task Management\n    - Scheduling\n    - Queue Management\n    - AI Agents\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TRIGGER_SECRET_KEY: TRIGGER_SECRET_KEY\n\ncapability:\n  consumes:\n    - import: trigger-dev\n      location: ./shared/trigger-dev-management.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: workflow-automation-api\n      description: \"Unified REST API for Trigger.dev workflow automation.\"\n      resources:\n        - path: /v1/tasks/{taskIdentifier}/trigger\n\
  \          name: task-trigger\n          description: Trigger a background task\n          operations:\n            - method: POST\n              name: trigger-task\n              description: Trigger a task run with payload and options\n              call: \"trigger-dev.trigger-task\"\n              with:\n                taskIdentifier: \"rest.taskIdentifier\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tasks/batch\n          name: batch-trigger\n          description: Batch trigger multiple task runs\n          operations:\n            - method: POST\n              name: batch-trigger-tasks\n              description: Trigger multiple tasks in a single batch\n              call: \"trigger-dev.batch-trigger-tasks\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/runs\n          name: runs\n          description: Run listing and monitoring\n\
  \          operations:\n            - method: GET\n              name: list-runs\n              description: List runs with filtering\n              call: \"trigger-dev.list-runs\"\n              with:\n                filter[status]: \"rest.status\"\n                filter[tag]: \"rest.tag\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/runs/{runId}\n          name: run-detail\n          description: Individual run details\n          operations:\n            - method: GET\n              name: get-run\n              description: Get run details, status, and output\n              call: \"trigger-dev.get-run\"\n              with:\n                runId: \"rest.runId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/runs/{runId}/cancel\n          name: run-cancel\n          description: Cancel a run\n          operations:\n            - method:\
  \ POST\n              name: cancel-run\n              description: Cancel a queued or executing run\n              call: \"trigger-dev.cancel-run\"\n              with:\n                runId: \"rest.runId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/runs/{runId}/replay\n          name: run-replay\n          description: Replay a run\n          operations:\n            - method: POST\n              name: replay-run\n              description: Replay a run with the same payload\n              call: \"trigger-dev.replay-run\"\n              with:\n                runId: \"rest.runId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/schedules\n          name: schedules\n          description: Schedule management\n          operations:\n            - method: GET\n              name: list-schedules\n              description: List all configured\
  \ schedules\n              call: \"trigger-dev.list-schedules\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-schedule\n              description: Create a cron schedule\n              call: \"trigger-dev.create-schedule\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/queues\n          name: queues\n          description: Queue monitoring and control\n          operations:\n            - method: GET\n              name: list-queues\n              description: List all task queues\n              call: \"trigger-dev.list-queues\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/queues/{queueName}/pause\n          name: queue-pause\n          description: Queue pause control\n          operations:\n            - method: POST\n     \
  \         name: pause-queue\n              description: Pause a queue\n              call: \"trigger-dev.pause-queue\"\n              with:\n                queueName: \"rest.queueName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/queues/{queueName}/resume\n          name: queue-resume\n          description: Queue resume control\n          operations:\n            - method: POST\n              name: resume-queue\n              description: Resume a paused queue\n              call: \"trigger-dev.resume-queue\"\n              with:\n                queueName: \"rest.queueName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/waitpoints\n          name: waitpoints\n          description: Waitpoint token management\n          operations:\n            - method: POST\n              name: create-waitpoint-token\n              description:\
  \ Create a waitpoint token for human-in-the-loop approval\n              call: \"trigger-dev.create-waitpoint-token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/waitpoints/{tokenId}/complete\n          name: waitpoint-complete\n          description: Complete a waitpoint\n          operations:\n            - method: POST\n              name: complete-waitpoint-token\n              description: Complete a waitpoint to resume the waiting run\n              call: \"trigger-dev.complete-waitpoint-token\"\n              with:\n                tokenId: \"rest.tokenId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: workflow-automation-mcp\n      transport: http\n      description: \"MCP server for AI-assisted workflow automation with Trigger.dev.\"\n      tools:\n        - name: trigger-task\n          description:\
  \ Trigger a background task with a payload\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"trigger-dev.trigger-task\"\n          with:\n            taskIdentifier: \"tools.taskIdentifier\"\n            payload: \"tools.payload\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: batch-trigger-tasks\n          description: Trigger multiple task runs in a single batch request\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"trigger-dev.batch-trigger-tasks\"\n          with:\n            items: \"tools.items\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-runs\n          description: List task runs, filterable by status, tags, or task identifier\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trigger-dev.list-runs\"\n          with:\n\
  \            filter[status]: \"tools.status\"\n            filter[tag]: \"tools.tag\"\n            filter[taskIdentifier]: \"tools.taskIdentifier\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-run\n          description: Get detailed status, output, and metadata for a specific run\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trigger-dev.get-run\"\n          with:\n            runId: \"tools.runId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: cancel-run\n          description: Cancel a queued or currently executing run\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"trigger-dev.cancel-run\"\n          with:\n            runId: \"tools.runId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n\
  \        - name: replay-run\n          description: Replay a completed run with the original payload\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"trigger-dev.replay-run\"\n          with:\n            runId: \"tools.runId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-schedules\n          description: List all configured task schedules with their cron expressions\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trigger-dev.list-schedules\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-schedule\n          description: Create a new cron schedule to run a task automatically\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"trigger-dev.create-schedule\"\n          with:\n            task: \"tools.task\"\n           \
  \ cron: \"tools.cron\"\n            deduplicationKey: \"tools.deduplicationKey\"\n            timezone: \"tools.timezone\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-queues\n          description: List all task queues with their current depth and concurrency\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trigger-dev.list-queues\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: pause-queue\n          description: Pause a queue to prevent new runs from starting\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"trigger-dev.pause-queue\"\n          with:\n            queueName: \"tools.queueName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: resume-queue\n          description: Resume a paused queue to allow runs\
  \ to execute\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"trigger-dev.resume-queue\"\n          with:\n            queueName: \"tools.queueName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-waitpoint-token\n          description: Create a waitpoint token for a human-in-the-loop approval workflow\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"trigger-dev.create-waitpoint-token\"\n          with:\n            ttl: \"tools.ttl\"\n            idempotencyKey: \"tools.idempotencyKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: complete-waitpoint-token\n          description: Complete a waitpoint to resume a paused run with approval data\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"trigger-dev.complete-waitpoint-token\"\
  \n          with:\n            tokenId: \"tools.tokenId\"\n            data: \"tools.data\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/trigger-dev/refs/heads/main/capabilities/workflow-automation.yaml
tags:
- Trigger.dev
- Workflow Automation
- Background Jobs
- Task Management
- Scheduling
- Queue Management
- AI Agents
tools:
- description: Trigger a background task with a payload
  hints:
    openWorld: false
    readOnly: false
  name: trigger-task
- description: Trigger multiple task runs in a single batch request
  hints:
    openWorld: false
    readOnly: false
  name: batch-trigger-tasks
- description: List task runs, filterable by status, tags, or task identifier
  hints:
    openWorld: false
    readOnly: true
  name: list-runs
- description: Get detailed status, output, and metadata for a specific run
  hints:
    openWorld: false
    readOnly: true
  name: get-run
- description: Cancel a queued or currently executing run
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-run
- description: Replay a completed run with the original payload
  hints:
    openWorld: false
    readOnly: false
  name: replay-run
- description: List all configured task schedules with their cron expressions
  hints:
    openWorld: false
    readOnly: true
  name: list-schedules
- description: Create a new cron schedule to run a task automatically
  hints:
    openWorld: false
    readOnly: false
  name: create-schedule
- description: List all task queues with their current depth and concurrency
  hints:
    openWorld: false
    readOnly: true
  name: list-queues
- description: Pause a queue to prevent new runs from starting
  hints:
    idempotent: true
    readOnly: false
  name: pause-queue
- description: Resume a paused queue to allow runs to execute
  hints:
    idempotent: true
    readOnly: false
  name: resume-queue
- description: Create a waitpoint token for a human-in-the-loop approval workflow
  hints:
    openWorld: false
    readOnly: false
  name: create-waitpoint-token
- description: Complete a waitpoint to resume a paused run with approval data
  hints:
    idempotent: true
    readOnly: false
  name: complete-waitpoint-token
---
