---
api_specs:
- filename: step-functions-openapi.yml
  format: yaml
  label: step-functions
  slug: step-functions
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/step-functions/refs/heads/main/openapi/step-functions-openapi.yml
categories: []
consumed_apis:
- step-functions
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
- activity task polling and completion
- automation
- start and wait for express workflow result
- stop a running state machine execution. optionally specify an error code and cause for the stoppage.
- start sync execution
- get the status, input, and output of a specific state machine execution.
- list state machine versions
- execution inspection
- describe a specific state machine
- create a routing alias (e.g., prod, staging)
- start a new asynchronous execution
- get the full definition and configuration of a specific state machine.
- publish an immutable version of the current state machine definition. versions are referenced by aliases for safe deployments.
- list all aws step functions state machines in the current account and region.
- stop execution
- get execution history
- synchronous express workflow execution
- describe state machine
- retrieve the complete event history for a state machine execution, showing all state transitions and task results.
- validate an amazon states language definition
- send task failure
- report that an activity task has failed to step functions so the workflow can apply retry logic or transition to a fail state.
- publish version
- send task success
- serverless orchestration
- list all step functions activity resources used for worker-based tasks.
- activity worker management
- create activity
- list published versions
- list activities
- redrive execution
- api composition
- retrieve the execution event log
- list all aliases for a state machine
- report successful completion of an activity task to step functions. the task token comes from getactivitytask.
- publish a new immutable version
- aws
- list aliases
- start an asynchronous aws step functions state machine execution with optional json input.
- validate an amazon states language (asl) definition without creating a state machine. use before deploying to check for syntax errors.
- get execution status and i/o
- state machine execution management
- create an activity for worker-based task processing
- validate state machine definitions before deployment
- list state machines
- create state machine
- publish state machine version
- list executions
- validate state machine definition
- list all state machines in the account
- poll for a task from an activity queue
- start execution
- stop a running execution
- redrive a failed or aborted execution from where it left off, using the same input.
- step functions
- state machine lifecycle management
- create a new state machine with asl definition
- list all activity resources
- stop running executions
- state machine alias management for deployment routing
- orchestration
- state machine
- list executions for a state machine
- describe execution
- get activity task
- create a new aws step functions state machine with an amazon states language definition and iam role arn.
- execution event history
- state machine version management
- get state machine configuration and definition
- serverless
- create alias
- start and wait for the result of an express (synchronous) workflow execution. returns output when the execution completes.
- list executions for a state machine, optionally filtered by status (running, succeeded, failed, timed_out, aborted).
- workflow
slug: workflow-orchestration
source_filename: workflow-orchestration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"AWS Step Functions Workflow Orchestration\"\n  description: >-\n    Workflow orchestration capabilities using AWS Step Functions for building,\n    deploying, and monitoring state machine-based distributed applications.\n    Covers the full lifecycle from state machine creation and versioning through\n    execution management and activity worker coordination.\n  tags:\n    - AWS\n    - Step Functions\n    - Serverless\n    - Workflow\n    - Orchestration\n    - State Machine\n    - Automation\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n      AWS_SIGV4_AUTH: AWS_SIGV4_AUTH\n\ncapability:\n  consumes:\n    - import: step-functions\n      location: ./shared/step-functions.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: workflow-orchestration-api\n\
  \      description: \"Unified REST API for AWS Step Functions workflow orchestration.\"\n      resources:\n        - path: /v1/state-machines\n          name: state-machines\n          description: State machine lifecycle management\n          operations:\n            - method: GET\n              name: list-state-machines\n              description: List all state machines in the account\n              call: \"step-functions.list-state-machines\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-state-machine\n              description: Create a new state machine with ASL definition\n              call: \"step-functions.create-state-machine\"\n              with:\n                name: \"rest.name\"\n                definition: \"rest.definition\"\n                roleArn: \"rest.roleArn\"\n                type: \"rest.type\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n        - path: /v1/state-machines/{arn}/describe\n          name: describe-state-machine\n          description: Get state machine configuration and definition\n          operations:\n            - method: GET\n              name: describe-state-machine\n              description: Describe a specific state machine\n              call: \"step-functions.describe-state-machine\"\n              with:\n                stateMachineArn: \"rest.arn\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/state-machines/{arn}/validate\n          name: validate-definition\n          description: Validate state machine definitions before deployment\n          operations:\n            - method: POST\n              name: validate-state-machine-definition\n              description: Validate an Amazon States Language definition\n              call: \"step-functions.validate-state-machine-definition\"\
  \n              with:\n                definition: \"rest.definition\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/state-machines/{arn}/versions\n          name: versions\n          description: State machine version management\n          operations:\n            - method: GET\n              name: list-state-machine-versions\n              description: List published versions\n              call: \"step-functions.list-state-machine-versions\"\n              with:\n                stateMachineArn: \"rest.arn\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: publish-version\n              description: Publish a new immutable version\n              call: \"step-functions.publish-state-machine-version\"\n              with:\n                stateMachineArn: \"rest.arn\"\n                description: \"rest.description\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/state-machines/{arn}/aliases\n          name: aliases\n          description: State machine alias management for deployment routing\n          operations:\n            - method: GET\n              name: list-aliases\n              description: List all aliases for a state machine\n              call: \"step-functions.list-state-machine-aliases\"\n              with:\n                stateMachineArn: \"rest.arn\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-alias\n              description: Create a routing alias (e.g., PROD, STAGING)\n              call: \"step-functions.create-state-machine-alias\"\n              with:\n                name: \"rest.name\"\n                routingConfiguration: \"rest.routingConfiguration\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/executions\n          name: executions\n          description: State machine execution management\n          operations:\n            - method: POST\n              name: start-execution\n              description: Start a new asynchronous execution\n              call: \"step-functions.start-execution\"\n              with:\n                stateMachineArn: \"rest.stateMachineArn\"\n                name: \"rest.name\"\n                input: \"rest.input\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-executions\n              description: List executions for a state machine\n              call: \"step-functions.list-executions\"\n              with:\n                stateMachineArn: \"rest.stateMachineArn\"\n                statusFilter: \"rest.statusFilter\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/executions/{arn}/describe\n          name: describe-execution\n          description: Execution inspection\n          operations:\n            - method: GET\n              name: describe-execution\n              description: Get execution status and I/O\n              call: \"step-functions.describe-execution\"\n              with:\n                executionArn: \"rest.arn\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/executions/{arn}/history\n          name: execution-history\n          description: Execution event history\n          operations:\n            - method: GET\n              name: get-execution-history\n              description: Retrieve the execution event log\n              call: \"step-functions.get-execution-history\"\n              with:\n                executionArn: \"rest.arn\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/executions/{arn}/stop\n          name: stop-execution\n          description: Stop running executions\n          operations:\n            - method: POST\n              name: stop-execution\n              description: Stop a running execution\n              call: \"step-functions.stop-execution\"\n              with:\n                executionArn: \"rest.arn\"\n                error: \"rest.error\"\n                cause: \"rest.cause\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sync-executions\n          name: sync-executions\n          description: Synchronous Express workflow execution\n          operations:\n            - method: POST\n              name: start-sync-execution\n              description: Start and wait for Express workflow result\n              call: \"step-functions.start-sync-execution\"\n            \
  \  with:\n                stateMachineArn: \"rest.stateMachineArn\"\n                input: \"rest.input\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/activities\n          name: activities\n          description: Activity worker management\n          operations:\n            - method: GET\n              name: list-activities\n              description: List all activity resources\n              call: \"step-functions.list-activities\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-activity\n              description: Create an activity for worker-based task processing\n              call: \"step-functions.create-activity\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/activities/tasks\n\
  \          name: activity-tasks\n          description: Activity task polling and completion\n          operations:\n            - method: POST\n              name: get-activity-task\n              description: Poll for a task from an activity queue\n              call: \"step-functions.get-activity-task\"\n              with:\n                activityArn: \"rest.activityArn\"\n                workerName: \"rest.workerName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: workflow-orchestration-mcp\n      transport: http\n      description: \"MCP server for AI-assisted AWS Step Functions workflow orchestration.\"\n      tools:\n        - name: list-state-machines\n          description: >-\n            List all AWS Step Functions state machines in the current account and region.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"step-functions.list-state-machines\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-state-machine\n          description: >-\n            Get the full definition and configuration of a specific state machine.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"step-functions.describe-state-machine\"\n          with:\n            stateMachineArn: \"tools.stateMachineArn\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-state-machine\n          description: >-\n            Create a new AWS Step Functions state machine with an Amazon States\n            Language definition and IAM role ARN.\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"step-functions.create-state-machine\"\n          with:\n            name: \"tools.name\"\n            definition: \"tools.definition\"\n            roleArn: \"tools.roleArn\"\
  \n            type: \"tools.type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: validate-state-machine-definition\n          description: >-\n            Validate an Amazon States Language (ASL) definition without creating\n            a state machine. Use before deploying to check for syntax errors.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"step-functions.validate-state-machine-definition\"\n          with:\n            definition: \"tools.definition\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: start-execution\n          description: >-\n            Start an asynchronous AWS Step Functions state machine execution\n            with optional JSON input.\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"step-functions.start-execution\"\n          with:\n            stateMachineArn:\
  \ \"tools.stateMachineArn\"\n            name: \"tools.name\"\n            input: \"tools.input\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: start-sync-execution\n          description: >-\n            Start and wait for the result of an Express (synchronous) workflow execution.\n            Returns output when the execution completes.\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"step-functions.start-sync-execution\"\n          with:\n            stateMachineArn: \"tools.stateMachineArn\"\n            input: \"tools.input\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-execution\n          description: >-\n            Get the status, input, and output of a specific state machine execution.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"step-functions.describe-execution\"\
  \n          with:\n            executionArn: \"tools.executionArn\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-executions\n          description: >-\n            List executions for a state machine, optionally filtered by status\n            (RUNNING, SUCCEEDED, FAILED, TIMED_OUT, ABORTED).\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"step-functions.list-executions\"\n          with:\n            stateMachineArn: \"tools.stateMachineArn\"\n            statusFilter: \"tools.statusFilter\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-execution-history\n          description: >-\n            Retrieve the complete event history for a state machine execution,\n            showing all state transitions and task results.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"step-functions.get-execution-history\"\
  \n          with:\n            executionArn: \"tools.executionArn\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: stop-execution\n          description: >-\n            Stop a running state machine execution. Optionally specify an error\n            code and cause for the stoppage.\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"step-functions.stop-execution\"\n          with:\n            executionArn: \"tools.executionArn\"\n            error: \"tools.error\"\n            cause: \"tools.cause\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: publish-state-machine-version\n          description: >-\n            Publish an immutable version of the current state machine definition.\n            Versions are referenced by aliases for safe deployments.\n          hints:\n            readOnly: false\n\
  \            destructive: false\n          call: \"step-functions.publish-state-machine-version\"\n          with:\n            stateMachineArn: \"tools.stateMachineArn\"\n            description: \"tools.description\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: redrive-execution\n          description: >-\n            Redrive a failed or aborted execution from where it left off,\n            using the same input.\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"step-functions.redrive-execution\"\n          with:\n            executionArn: \"tools.executionArn\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-activities\n          description: >-\n            List all Step Functions activity resources used for worker-based tasks.\n          hints:\n            readOnly: true\n            openWorld: true\n          call:\
  \ \"step-functions.list-activities\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-task-success\n          description: >-\n            Report successful completion of an activity task to Step Functions.\n            The task token comes from GetActivityTask.\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"step-functions.send-task-success\"\n          with:\n            taskToken: \"tools.taskToken\"\n            output: \"tools.output\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-task-failure\n          description: >-\n            Report that an activity task has failed to Step Functions so the\n            workflow can apply retry logic or transition to a Fail state.\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"step-functions.send-task-failure\"\n      \
  \    with:\n            taskToken: \"tools.taskToken\"\n            error: \"tools.error\"\n            cause: \"tools.cause\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
