---
categories: []
consumed_apis: []
description: Workflow orchestration capabilities using AWS Step Functions for building, deploying, and monitoring state machine-based distributed applications. Covers the full lifecycle from state machine creation and versioning through execution management and activity worker coordination.
layout: capability
name: AWS Step Functions Workflow Orchestration
operations:
- description: List all state machines in the account
  method: GET
  name: list-state-machines
  path: /v1/state-machines
- description: Create a new state machine with ASL definition
  method: POST
  name: create-state-machine
  path: /v1/state-machines
- description: Describe a specific state machine
  method: GET
  name: describe-state-machine
  path: /v1/state-machines/{arn}/describe
- description: Validate an Amazon States Language definition
  method: POST
  name: validate-state-machine-definition
  path: /v1/state-machines/{arn}/validate
- description: List published versions
  method: GET
  name: list-state-machine-versions
  path: /v1/state-machines/{arn}/versions
- description: Publish a new immutable version
  method: POST
  name: publish-version
  path: /v1/state-machines/{arn}/versions
- description: List all aliases for a state machine
  method: GET
  name: list-aliases
  path: /v1/state-machines/{arn}/aliases
- description: Create a routing alias (e.g., PROD, STAGING)
  method: POST
  name: create-alias
  path: /v1/state-machines/{arn}/aliases
- description: Start a new asynchronous execution
  method: POST
  name: start-execution
  path: /v1/executions
- description: List executions for a state machine
  method: GET
  name: list-executions
  path: /v1/executions
- description: Get execution status and I/O
  method: GET
  name: describe-execution
  path: /v1/executions/{arn}/describe
- description: Retrieve the execution event log
  method: GET
  name: get-execution-history
  path: /v1/executions/{arn}/history
- description: Stop a running execution
  method: POST
  name: stop-execution
  path: /v1/executions/{arn}/stop
- description: Start and wait for Express workflow result
  method: POST
  name: start-sync-execution
  path: /v1/sync-executions
- description: List all activity resources
  method: GET
  name: list-activities
  path: /v1/activities
- description: Create an activity for worker-based task processing
  method: POST
  name: create-activity
  path: /v1/activities
- description: Poll for a task from an activity queue
  method: POST
  name: get-activity-task
  path: /v1/activities/tasks
personas: []
provider_name: AWS Step Functions
provider_slug: step-functions
search_terms:
- poll for a task from an activity queue
- api composition
- aws
- list published versions
- activity task polling and completion
- publish version
- execution inspection
- stop a running state machine execution. optionally specify an error code and cause for the stoppage.
- publish state machine version
- list all step functions activity resources used for worker-based tasks.
- report successful completion of an activity task to step functions. the task token comes from getactivitytask.
- get execution status and i/o
- workflow
- list all activity resources
- describe a specific state machine
- report that an activity task has failed to step functions so the workflow can apply retry logic or transition to a fail state.
- validate an amazon states language definition
- start and wait for express workflow result
- start sync execution
- start and wait for the result of an express (synchronous) workflow execution. returns output when the execution completes.
- get execution history
- publish an immutable version of the current state machine definition. versions are referenced by aliases for safe deployments.
- describe execution
- start an asynchronous aws step functions state machine execution with optional json input.
- redrive execution
- activity worker management
- describe state machine
- serverless orchestration
- serverless
- synchronous express workflow execution
- create activity
- state machine alias management for deployment routing
- state machine execution management
- get the full definition and configuration of a specific state machine.
- get the status, input, and output of a specific state machine execution.
- create a new aws step functions state machine with an amazon states language definition and iam role arn.
- step functions
- retrieve the execution event log
- redrive a failed or aborted execution from where it left off, using the same input.
- create state machine
- list executions
- stop running executions
- create a routing alias (e.g., prod, staging)
- execution event history
- orchestration
- start execution
- state machine
- get state machine configuration and definition
- validate an amazon states language (asl) definition without creating a state machine. use before deploying to check for syntax errors.
- create a new state machine with asl definition
- validate state machine definition
- get activity task
- list executions for a state machine, optionally filtered by status (running, succeeded, failed, timed_out, aborted).
- create alias
- retrieve the complete event history for a state machine execution, showing all state transitions and task results.
- start a new asynchronous execution
- state machine lifecycle management
- stop a running execution
- list all state machines in the account
- list all aliases for a state machine
- create an activity for worker-based task processing
- send task success
- stop execution
- list activities
- list aliases
- list all aws step functions state machines in the current account and region.
- send task failure
- list state machine versions
- state machine version management
- publish a new immutable version
- list state machines
- validate state machine definitions before deployment
- list executions for a state machine
- automation
slug: workflow-orchestration
source_filename: workflow-orchestration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AWS Step Functions Workflow Orchestration\n  description: Workflow orchestration capabilities using AWS Step Functions for building, deploying, and monitoring state\n    machine-based distributed applications. Covers the full lifecycle from state machine creation and versioning through execution\n    management and activity worker coordination.\n  tags:\n  - AWS\n  - Step Functions\n  - Serverless\n  - Workflow\n  - Orchestration\n  - State Machine\n  - Automation\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\n    AWS_SIGV4_AUTH: AWS_SIGV4_AUTH\ncapability:\n  consumes:\n  - type: http\n    namespace: step-functions\n    baseUri: https://states.{{env.AWS_REGION}}.amazonaws.com\n    description: AWS Step Functions regional API endpoint\n    authentication:\n      type: apikey\n \
  \     key: Authorization\n      value: '{{env.AWS_SIGV4_AUTH}}'\n      placement: header\n    resources:\n    - name: state-machines\n      path: /\n      description: State machine management via AWS JSON protocol\n      operations:\n      - name: create-state-machine\n        method: POST\n        description: Create a new state machine\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: AmazonStates.CreateStateMachine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            definition: '{{tools.definition}}'\n            roleArn: '{{tools.roleArn}}'\n            type: '{{tools.type}}'\n      - name: list-state-machines\n        method: POST\n        description: List all state machines\n        inputParameters:\n \
  \       - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n          description: AmazonStates.ListStateMachines\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describe-state-machine\n        method: POST\n        description: Describe a specific state machine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            stateMachineArn: '{{tools.stateMachineArn}}'\n      - name: update-state-machine\n        method: POST\n        description: Update a state machine definition or configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            stateMachineArn: '{{tools.stateMachineArn}}'\n\
  \            definition: '{{tools.definition}}'\n      - name: delete-state-machine\n        method: POST\n        description: Delete a state machine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            stateMachineArn: '{{tools.stateMachineArn}}'\n      - name: start-execution\n        method: POST\n        description: Start a state machine execution\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            stateMachineArn: '{{tools.stateMachineArn}}'\n            name: '{{tools.name}}'\n            input: '{{tools.input}}'\n      - name: start-sync-execution\n        method: POST\n        description: Start a synchronous Express workflow execution\n        outputRawFormat: json\n        outputParameters:\n   \
  \     - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            stateMachineArn: '{{tools.stateMachineArn}}'\n            input: '{{tools.input}}'\n      - name: stop-execution\n        method: POST\n        description: Stop a running state machine execution\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            executionArn: '{{tools.executionArn}}'\n            error: '{{tools.error}}'\n            cause: '{{tools.cause}}'\n      - name: describe-execution\n        method: POST\n        description: Describe a specific execution\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            executionArn: '{{tools.executionArn}}'\n      - name: list-executions\n\
  \        method: POST\n        description: List executions for a state machine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            stateMachineArn: '{{tools.stateMachineArn}}'\n            statusFilter: '{{tools.statusFilter}}'\n      - name: get-execution-history\n        method: POST\n        description: Get execution history events\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            executionArn: '{{tools.executionArn}}'\n      - name: redrive-execution\n        method: POST\n        description: Redrive a failed or aborted execution\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n     \
  \     data:\n            executionArn: '{{tools.executionArn}}'\n      - name: create-activity\n        method: POST\n        description: Create an activity for worker-based tasks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: list-activities\n        method: POST\n        description: List all activities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-activity-task\n        method: POST\n        description: Poll for a task from an activity queue\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            activityArn: '{{tools.activityArn}}'\n            workerName: '{{tools.workerName}}'\n\
  \      - name: send-task-success\n        method: POST\n        description: Report successful completion of an activity task\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            taskToken: '{{tools.taskToken}}'\n            output: '{{tools.output}}'\n      - name: send-task-failure\n        method: POST\n        description: Report failure of an activity task\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            taskToken: '{{tools.taskToken}}'\n            error: '{{tools.error}}'\n            cause: '{{tools.cause}}'\n      - name: send-task-heartbeat\n        method: POST\n        description: Send a heartbeat to keep an activity task from timing out\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            taskToken: '{{tools.taskToken}}'\n      - name: publish-state-machine-version\n        method: POST\n        description: Publish a new version of a state machine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            stateMachineArn: '{{tools.stateMachineArn}}'\n            description: '{{tools.description}}'\n      - name: list-state-machine-versions\n        method: POST\n        description: List published versions of a state machine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            stateMachineArn: '{{tools.stateMachineArn}}'\n      - name: create-state-machine-alias\n\
  \        method: POST\n        description: Create an alias pointing to a specific version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            routingConfiguration: '{{tools.routingConfiguration}}'\n      - name: list-state-machine-aliases\n        method: POST\n        description: List aliases for a state machine\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            stateMachineArn: '{{tools.stateMachineArn}}'\n      - name: tag-resource\n        method: POST\n        description: Add tags to a Step Functions resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type:\
  \ json\n          data:\n            resourceArn: '{{tools.resourceArn}}'\n            tags: '{{tools.tags}}'\n      - name: list-tags-for-resource\n        method: POST\n        description: List tags on a Step Functions resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            resourceArn: '{{tools.resourceArn}}'\n      - name: validate-state-machine-definition\n        method: POST\n        description: Validate a state machine definition before creating\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            definition: '{{tools.definition}}'\n      - name: test-state\n        method: POST\n        description: Test a single state in a state machine definition\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            stateMachineArn: '{{tools.stateMachineArn}}'\n            name: '{{tools.name}}'\n            input: '{{tools.input}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: workflow-orchestration-api\n    description: Unified REST API for AWS Step Functions workflow orchestration.\n    resources:\n    - path: /v1/state-machines\n      name: state-machines\n      description: State machine lifecycle management\n      operations:\n      - method: GET\n        name: list-state-machines\n        description: List all state machines in the account\n        call: step-functions.list-state-machines\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-state-machine\n        description: Create a new state machine with ASL definition\n        call: step-functions.create-state-machine\n     \
  \   with:\n          name: rest.name\n          definition: rest.definition\n          roleArn: rest.roleArn\n          type: rest.type\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/state-machines/{arn}/describe\n      name: describe-state-machine\n      description: Get state machine configuration and definition\n      operations:\n      - method: GET\n        name: describe-state-machine\n        description: Describe a specific state machine\n        call: step-functions.describe-state-machine\n        with:\n          stateMachineArn: rest.arn\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/state-machines/{arn}/validate\n      name: validate-definition\n      description: Validate state machine definitions before deployment\n      operations:\n      - method: POST\n        name: validate-state-machine-definition\n        description: Validate an Amazon States Language definition\n        call: step-functions.validate-state-machine-definition\n\
  \        with:\n          definition: rest.definition\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/state-machines/{arn}/versions\n      name: versions\n      description: State machine version management\n      operations:\n      - method: GET\n        name: list-state-machine-versions\n        description: List published versions\n        call: step-functions.list-state-machine-versions\n        with:\n          stateMachineArn: rest.arn\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: publish-version\n        description: Publish a new immutable version\n        call: step-functions.publish-state-machine-version\n        with:\n          stateMachineArn: rest.arn\n          description: rest.description\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/state-machines/{arn}/aliases\n      name: aliases\n      description: State machine alias\
  \ management for deployment routing\n      operations:\n      - method: GET\n        name: list-aliases\n        description: List all aliases for a state machine\n        call: step-functions.list-state-machine-aliases\n        with:\n          stateMachineArn: rest.arn\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-alias\n        description: Create a routing alias (e.g., PROD, STAGING)\n        call: step-functions.create-state-machine-alias\n        with:\n          name: rest.name\n          routingConfiguration: rest.routingConfiguration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/executions\n      name: executions\n      description: State machine execution management\n      operations:\n      - method: POST\n        name: start-execution\n        description: Start a new asynchronous execution\n        call: step-functions.start-execution\n        with:\n      \
  \    stateMachineArn: rest.stateMachineArn\n          name: rest.name\n          input: rest.input\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-executions\n        description: List executions for a state machine\n        call: step-functions.list-executions\n        with:\n          stateMachineArn: rest.stateMachineArn\n          statusFilter: rest.statusFilter\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/executions/{arn}/describe\n      name: describe-execution\n      description: Execution inspection\n      operations:\n      - method: GET\n        name: describe-execution\n        description: Get execution status and I/O\n        call: step-functions.describe-execution\n        with:\n          executionArn: rest.arn\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/executions/{arn}/history\n      name: execution-history\n  \
  \    description: Execution event history\n      operations:\n      - method: GET\n        name: get-execution-history\n        description: Retrieve the execution event log\n        call: step-functions.get-execution-history\n        with:\n          executionArn: rest.arn\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/executions/{arn}/stop\n      name: stop-execution\n      description: Stop running executions\n      operations:\n      - method: POST\n        name: stop-execution\n        description: Stop a running execution\n        call: step-functions.stop-execution\n        with:\n          executionArn: rest.arn\n          error: rest.error\n          cause: rest.cause\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sync-executions\n      name: sync-executions\n      description: Synchronous Express workflow execution\n      operations:\n      - method: POST\n        name: start-sync-execution\n\
  \        description: Start and wait for Express workflow result\n        call: step-functions.start-sync-execution\n        with:\n          stateMachineArn: rest.stateMachineArn\n          input: rest.input\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/activities\n      name: activities\n      description: Activity worker management\n      operations:\n      - method: GET\n        name: list-activities\n        description: List all activity resources\n        call: step-functions.list-activities\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-activity\n        description: Create an activity for worker-based task processing\n        call: step-functions.create-activity\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/activities/tasks\n      name: activity-tasks\n      description: Activity\
  \ task polling and completion\n      operations:\n      - method: POST\n        name: get-activity-task\n        description: Poll for a task from an activity queue\n        call: step-functions.get-activity-task\n        with:\n          activityArn: rest.activityArn\n          workerName: rest.workerName\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: workflow-orchestration-mcp\n    transport: http\n    description: MCP server for AI-assisted AWS Step Functions workflow orchestration.\n    tools:\n    - name: list-state-machines\n      description: List all AWS Step Functions state machines in the current account and region.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: step-functions.list-state-machines\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-state-machine\n      description: Get the full definition and configuration of a specific state\
  \ machine.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: step-functions.describe-state-machine\n      with:\n        stateMachineArn: tools.stateMachineArn\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-state-machine\n      description: Create a new AWS Step Functions state machine with an Amazon States Language definition and IAM role ARN.\n      hints:\n        readOnly: false\n        destructive: false\n      call: step-functions.create-state-machine\n      with:\n        name: tools.name\n        definition: tools.definition\n        roleArn: tools.roleArn\n        type: tools.type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: validate-state-machine-definition\n      description: Validate an Amazon States Language (ASL) definition without creating a state machine. Use before deploying\n        to check for syntax errors.\n      hints:\n        readOnly: true\n        openWorld:\
  \ false\n      call: step-functions.validate-state-machine-definition\n      with:\n        definition: tools.definition\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-execution\n      description: Start an asynchronous AWS Step Functions state machine execution with optional JSON input.\n      hints:\n        readOnly: false\n        destructive: false\n      call: step-functions.start-execution\n      with:\n        stateMachineArn: tools.stateMachineArn\n        name: tools.name\n        input: tools.input\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-sync-execution\n      description: Start and wait for the result of an Express (synchronous) workflow execution. Returns output when the execution\n        completes.\n      hints:\n        readOnly: false\n        destructive: false\n      call: step-functions.start-sync-execution\n      with:\n        stateMachineArn: tools.stateMachineArn\n        input:\
  \ tools.input\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-execution\n      description: Get the status, input, and output of a specific state machine execution.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: step-functions.describe-execution\n      with:\n        executionArn: tools.executionArn\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-executions\n      description: List executions for a state machine, optionally filtered by status (RUNNING, SUCCEEDED, FAILED, TIMED_OUT,\n        ABORTED).\n      hints:\n        readOnly: true\n        openWorld: true\n      call: step-functions.list-executions\n      with:\n        stateMachineArn: tools.stateMachineArn\n        statusFilter: tools.statusFilter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-execution-history\n      description: Retrieve the complete event history for a state machine\
  \ execution, showing all state transitions and task\n        results.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: step-functions.get-execution-history\n      with:\n        executionArn: tools.executionArn\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stop-execution\n      description: Stop a running state machine execution. Optionally specify an error code and cause for the stoppage.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: step-functions.stop-execution\n      with:\n        executionArn: tools.executionArn\n        error: tools.error\n        cause: tools.cause\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publish-state-machine-version\n      description: Publish an immutable version of the current state machine definition. Versions are referenced by aliases\n        for safe deployments.\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n      call: step-functions.publish-state-machine-version\n      with:\n        stateMachineArn: tools.stateMachineArn\n        description: tools.description\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: redrive-execution\n      description: Redrive a failed or aborted execution from where it left off, using the same input.\n      hints:\n        readOnly: false\n        destructive: false\n      call: step-functions.redrive-execution\n      with:\n        executionArn: tools.executionArn\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-activities\n      description: List all Step Functions activity resources used for worker-based tasks.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: step-functions.list-activities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-task-success\n      description: Report successful completion\
  \ of an activity task to Step Functions. The task token comes from GetActivityTask.\n      hints:\n        readOnly: false\n        destructive: false\n      call: step-functions.send-task-success\n      with:\n        taskToken: tools.taskToken\n        output: tools.output\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-task-failure\n      description: Report that an activity task has failed to Step Functions so the workflow can apply retry logic or transition\n        to a Fail state.\n      hints:\n        readOnly: false\n        destructive: false\n      call: step-functions.send-task-failure\n      with:\n        taskToken: tools.taskToken\n        error: tools.error\n        cause: tools.cause\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/step-functions/refs/heads/main/capabilities/workflow-orchestration.yaml
tags:
- Step Functions
- Serverless
- Workflow
- Orchestration
- State Machine
- Automation
tools:
- description: List all AWS Step Functions state machines in the current account and region.
  hints:
    openWorld: true
    readOnly: true
  name: list-state-machines
- description: Get the full definition and configuration of a specific state machine.
  hints:
    openWorld: true
    readOnly: true
  name: describe-state-machine
- description: Create a new AWS Step Functions state machine with an Amazon States Language definition and IAM role ARN.
  hints:
    destructive: false
    readOnly: false
  name: create-state-machine
- description: Validate an Amazon States Language (ASL) definition without creating a state machine. Use before deploying to check for syntax errors.
  hints:
    openWorld: false
    readOnly: true
  name: validate-state-machine-definition
- description: Start an asynchronous AWS Step Functions state machine execution with optional JSON input.
  hints:
    destructive: false
    readOnly: false
  name: start-execution
- description: Start and wait for the result of an Express (synchronous) workflow execution. Returns output when the execution completes.
  hints:
    destructive: false
    readOnly: false
  name: start-sync-execution
- description: Get the status, input, and output of a specific state machine execution.
  hints:
    openWorld: true
    readOnly: true
  name: describe-execution
- description: List executions for a state machine, optionally filtered by status (RUNNING, SUCCEEDED, FAILED, TIMED_OUT, ABORTED).
  hints:
    openWorld: true
    readOnly: true
  name: list-executions
- description: Retrieve the complete event history for a state machine execution, showing all state transitions and task results.
  hints:
    openWorld: true
    readOnly: true
  name: get-execution-history
- description: Stop a running state machine execution. Optionally specify an error code and cause for the stoppage.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: stop-execution
- description: Publish an immutable version of the current state machine definition. Versions are referenced by aliases for safe deployments.
  hints:
    destructive: false
    readOnly: false
  name: publish-state-machine-version
- description: Redrive a failed or aborted execution from where it left off, using the same input.
  hints:
    destructive: false
    readOnly: false
  name: redrive-execution
- description: List all Step Functions activity resources used for worker-based tasks.
  hints:
    openWorld: true
    readOnly: true
  name: list-activities
- description: Report successful completion of an activity task to Step Functions. The task token comes from GetActivityTask.
  hints:
    destructive: false
    readOnly: false
  name: send-task-success
- description: Report that an activity task has failed to Step Functions so the workflow can apply retry logic or transition to a Fail state.
  hints:
    destructive: false
    readOnly: false
  name: send-task-failure
---
