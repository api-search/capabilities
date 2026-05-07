---
categories: []
consumed_apis: []
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
- list all configured schedules
- resume a paused queue
- ai agents
- task management
- get detailed status, output, and metadata for a specific run
- developer-first
- list task runs, filterable by status, tags, or task identifier
- workflow automation
- background jobs
- cancel a queued or executing run
- list all task queues with their current depth and concurrency
- resume a paused queue to allow runs to execute
- trigger a task run with payload and options
- replay a run with the same payload
- list queues
- list all task queues
- schedule management
- list runs with filtering
- batch trigger tasks
- replay a completed run with the original payload
- get run details, status, and output
- individual run details
- trigger a background task with a payload
- trigger.dev
- open source
- create a waitpoint token for human-in-the-loop approval
- queue pause control
- pause a queue
- trigger multiple task runs in a single batch request
- complete a waitpoint
- list runs
- pause a queue to prevent new runs from starting
- trigger a background task
- trigger multiple tasks in a single batch
- pause queue
- replay run
- cancel a queued or currently executing run
- list schedules
- complete a waitpoint to resume a paused run with approval data
- create waitpoint token
- create a new cron schedule to run a task automatically
- complete waitpoint token
- queue management
- resume queue
- typescript
- run listing and monitoring
- trigger task
- batch trigger multiple task runs
- list all configured task schedules with their cron expressions
- cancel run
- replay a run
- create a waitpoint token for a human-in-the-loop approval workflow
- cancel a run
- scheduling
- queue monitoring and control
- waitpoint token management
- get run
- complete a waitpoint to resume the waiting run
- queue resume control
- create a cron schedule
- create schedule
slug: workflow-automation
source_filename: workflow-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Trigger.dev Workflow Automation\n  description: Unified workflow automation capability combining task triggering, run monitoring, schedule management, queue\n    control, and waitpoint orchestration. Powers AI agent pipelines, background job platforms, and human-in-the-loop approval\n    workflows.\n  tags:\n  - Trigger.dev\n  - Workflow Automation\n  - Background Jobs\n  - Task Management\n  - Scheduling\n  - Queue Management\n  - AI Agents\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TRIGGER_SECRET_KEY: TRIGGER_SECRET_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: trigger-dev\n    baseUri: https://api.trigger.dev\n    description: Trigger.dev Management API for workflow orchestration\n    authentication:\n      type: bearer\n      token: '{{TRIGGER_SECRET_KEY}}'\n    resources:\n    - name: tasks\n      path: /api/v1/tasks\n      description: Task triggering operations\n  \
  \    operations:\n      - name: trigger-task\n        method: POST\n        description: Trigger a single task run\n        inputParameters:\n        - name: taskIdentifier\n          in: path\n          type: string\n          required: true\n          description: Task identifier\n        body:\n          type: json\n          data:\n            payload: '{{tools.payload}}'\n            options: '{{tools.options}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: batch-trigger-tasks\n        method: POST\n        description: Trigger multiple task runs in a batch\n        body:\n          type: json\n          data:\n            items: '{{tools.items}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: runs\n      path: /api/v1/runs\n      description: Run monitoring and management\n      operations:\n \
  \     - name: list-runs\n        method: GET\n        description: List runs with filtering and pagination\n        inputParameters:\n        - name: filter[status]\n          in: query\n          type: array\n          required: false\n          description: Filter by run status\n        - name: filter[taskIdentifier]\n          in: query\n          type: array\n          required: false\n          description: Filter by task identifiers\n        - name: filter[tag]\n          in: query\n          type: array\n          required: false\n          description: Filter by tags\n        - name: page[size]\n          in: query\n          type: integer\n          required: false\n          description: Page size\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-run\n        method: GET\n        description: Retrieve details for a specific run\n        inputParameters:\n        - name: runId\n   \
  \       in: path\n          type: string\n          required: true\n          description: Run identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cancel-run\n        method: POST\n        description: Cancel a queued or executing run\n        inputParameters:\n        - name: runId\n          in: path\n          type: string\n          required: true\n          description: Run identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: replay-run\n        method: POST\n        description: Replay a completed run with the same payload\n        inputParameters:\n        - name: runId\n          in: path\n          type: string\n          required: true\n          description: Run identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: schedules\n      path: /api/v1/schedules\n      description: Scheduled task management\n      operations:\n      - name: list-schedules\n        method: GET\n        description: List all configured schedules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-schedule\n        method: POST\n        description: Create a new cron schedule\n        body:\n          type: json\n          data:\n            task: '{{tools.task}}'\n            cron: '{{tools.cron}}'\n            deduplicationKey: '{{tools.deduplicationKey}}'\n            timezone: '{{tools.timezone}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-schedule\n        method: DELETE\n        description: Delete a schedule\n        inputParameters:\n        - name: scheduleId\n          in: path\n\
  \          type: string\n          required: true\n          description: Schedule identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: queues\n      path: /api/v1/queues\n      description: Queue management and concurrency control\n      operations:\n      - name: list-queues\n        method: GET\n        description: List all task queues\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: pause-queue\n        method: POST\n        description: Pause a queue\n        inputParameters:\n        - name: queueName\n          in: path\n          type: string\n          required: true\n          description: Queue name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: resume-queue\n        method: POST\n        description:\
  \ Resume a paused queue\n        inputParameters:\n        - name: queueName\n          in: path\n          type: string\n          required: true\n          description: Queue name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: waitpoints\n      path: /api/v1/waitpoints\n      description: Waitpoint token management for human-in-the-loop workflows\n      operations:\n      - name: create-waitpoint-token\n        method: POST\n        description: Create a waitpoint token to pause a run\n        body:\n          type: json\n          data:\n            idempotencyKey: '{{tools.idempotencyKey}}'\n            ttl: '{{tools.ttl}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: complete-waitpoint-token\n        method: POST\n        description: Complete a waitpoint to resume the paused run\n        inputParameters:\n\
  \        - name: tokenId\n          in: path\n          type: string\n          required: true\n          description: Waitpoint token identifier\n        body:\n          type: json\n          data:\n            data: '{{tools.data}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: workflow-automation-api\n    description: Unified REST API for Trigger.dev workflow automation.\n    resources:\n    - path: /v1/tasks/{taskIdentifier}/trigger\n      name: task-trigger\n      description: Trigger a background task\n      operations:\n      - method: POST\n        name: trigger-task\n        description: Trigger a task run with payload and options\n        call: trigger-dev.trigger-task\n        with:\n          taskIdentifier: rest.taskIdentifier\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tasks/batch\n   \
  \   name: batch-trigger\n      description: Batch trigger multiple task runs\n      operations:\n      - method: POST\n        name: batch-trigger-tasks\n        description: Trigger multiple tasks in a single batch\n        call: trigger-dev.batch-trigger-tasks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/runs\n      name: runs\n      description: Run listing and monitoring\n      operations:\n      - method: GET\n        name: list-runs\n        description: List runs with filtering\n        call: trigger-dev.list-runs\n        with:\n          filter[status]: rest.status\n          filter[tag]: rest.tag\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/runs/{runId}\n      name: run-detail\n      description: Individual run details\n      operations:\n      - method: GET\n        name: get-run\n        description: Get run details, status, and output\n        call: trigger-dev.get-run\n        with:\n\
  \          runId: rest.runId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/runs/{runId}/cancel\n      name: run-cancel\n      description: Cancel a run\n      operations:\n      - method: POST\n        name: cancel-run\n        description: Cancel a queued or executing run\n        call: trigger-dev.cancel-run\n        with:\n          runId: rest.runId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/runs/{runId}/replay\n      name: run-replay\n      description: Replay a run\n      operations:\n      - method: POST\n        name: replay-run\n        description: Replay a run with the same payload\n        call: trigger-dev.replay-run\n        with:\n          runId: rest.runId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/schedules\n      name: schedules\n      description: Schedule management\n      operations:\n      - method: GET\n        name: list-schedules\n\
  \        description: List all configured schedules\n        call: trigger-dev.list-schedules\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-schedule\n        description: Create a cron schedule\n        call: trigger-dev.create-schedule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/queues\n      name: queues\n      description: Queue monitoring and control\n      operations:\n      - method: GET\n        name: list-queues\n        description: List all task queues\n        call: trigger-dev.list-queues\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/queues/{queueName}/pause\n      name: queue-pause\n      description: Queue pause control\n      operations:\n      - method: POST\n        name: pause-queue\n        description: Pause a queue\n        call: trigger-dev.pause-queue\n        with:\n          queueName: rest.queueName\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/queues/{queueName}/resume\n      name: queue-resume\n      description: Queue resume control\n      operations:\n      - method: POST\n        name: resume-queue\n        description: Resume a paused queue\n        call: trigger-dev.resume-queue\n        with:\n          queueName: rest.queueName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/waitpoints\n      name: waitpoints\n      description: Waitpoint token management\n      operations:\n      - method: POST\n        name: create-waitpoint-token\n        description: Create a waitpoint token for human-in-the-loop approval\n        call: trigger-dev.create-waitpoint-token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/waitpoints/{tokenId}/complete\n      name: waitpoint-complete\n      description: Complete a waitpoint\n      operations:\n      - method: POST\n\
  \        name: complete-waitpoint-token\n        description: Complete a waitpoint to resume the waiting run\n        call: trigger-dev.complete-waitpoint-token\n        with:\n          tokenId: rest.tokenId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: workflow-automation-mcp\n    transport: http\n    description: MCP server for AI-assisted workflow automation with Trigger.dev.\n    tools:\n    - name: trigger-task\n      description: Trigger a background task with a payload\n      hints:\n        readOnly: false\n        openWorld: false\n      call: trigger-dev.trigger-task\n      with:\n        taskIdentifier: tools.taskIdentifier\n        payload: tools.payload\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: batch-trigger-tasks\n      description: Trigger multiple task runs in a single batch request\n      hints:\n        readOnly: false\n        openWorld: false\n      call:\
  \ trigger-dev.batch-trigger-tasks\n      with:\n        items: tools.items\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-runs\n      description: List task runs, filterable by status, tags, or task identifier\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trigger-dev.list-runs\n      with:\n        filter[status]: tools.status\n        filter[tag]: tools.tag\n        filter[taskIdentifier]: tools.taskIdentifier\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-run\n      description: Get detailed status, output, and metadata for a specific run\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trigger-dev.get-run\n      with:\n        runId: tools.runId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-run\n      description: Cancel a queued or currently executing run\n      hints:\n        readOnly: false\n        destructive:\
  \ true\n        idempotent: true\n      call: trigger-dev.cancel-run\n      with:\n        runId: tools.runId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: replay-run\n      description: Replay a completed run with the original payload\n      hints:\n        readOnly: false\n        openWorld: false\n      call: trigger-dev.replay-run\n      with:\n        runId: tools.runId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-schedules\n      description: List all configured task schedules with their cron expressions\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trigger-dev.list-schedules\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-schedule\n      description: Create a new cron schedule to run a task automatically\n      hints:\n        readOnly: false\n        openWorld: false\n      call: trigger-dev.create-schedule\n      with:\n        task:\
  \ tools.task\n        cron: tools.cron\n        deduplicationKey: tools.deduplicationKey\n        timezone: tools.timezone\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-queues\n      description: List all task queues with their current depth and concurrency\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trigger-dev.list-queues\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pause-queue\n      description: Pause a queue to prevent new runs from starting\n      hints:\n        readOnly: false\n        idempotent: true\n      call: trigger-dev.pause-queue\n      with:\n        queueName: tools.queueName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: resume-queue\n      description: Resume a paused queue to allow runs to execute\n      hints:\n        readOnly: false\n        idempotent: true\n      call: trigger-dev.resume-queue\n      with:\n        queueName:\
  \ tools.queueName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-waitpoint-token\n      description: Create a waitpoint token for a human-in-the-loop approval workflow\n      hints:\n        readOnly: false\n        openWorld: false\n      call: trigger-dev.create-waitpoint-token\n      with:\n        ttl: tools.ttl\n        idempotencyKey: tools.idempotencyKey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: complete-waitpoint-token\n      description: Complete a waitpoint to resume a paused run with approval data\n      hints:\n        readOnly: false\n        idempotent: true\n      call: trigger-dev.complete-waitpoint-token\n      with:\n        tokenId: tools.tokenId\n        data: tools.data\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
