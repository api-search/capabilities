---
categories: []
consumed_apis: []
description: Unified workflow for managing workflow definitions, task definitions, workflow executions, and event handlers. Used by backend developers and DevOps engineers.
layout: capability
name: Conductor Workflow Orchestration
operations:
- description: List all workflow definitions.
  method: GET
  name: list-workflow-definitions
  path: /v1/workflow-definitions
- description: Create a workflow definition.
  method: POST
  name: create-workflow-definition
  path: /v1/workflow-definitions
- description: Get a workflow definition.
  method: GET
  name: get-workflow-definition
  path: /v1/workflow-definitions/{id}
- description: Delete a workflow definition.
  method: DELETE
  name: delete-workflow-definition
  path: /v1/workflow-definitions/{id}
- description: List all task definitions.
  method: GET
  name: list-task-definitions
  path: /v1/task-definitions
- description: Create task definitions.
  method: POST
  name: create-task-definitions
  path: /v1/task-definitions
- description: Start a new workflow.
  method: POST
  name: start-workflow
  path: /v1/workflows
- description: Get workflow execution status.
  method: GET
  name: get-workflow-execution
  path: /v1/workflows/{id}
- description: Delete a workflow execution.
  method: DELETE
  name: delete-workflow-execution
  path: /v1/workflows/{id}
personas: []
provider_name: Conductor
provider_slug: conductor
search_terms:
- create task definitions.
- delete workflow definition
- list event handlers
- state
- start a new workflow execution.
- pause workflow
- tasks
- list all event handlers.
- list all workflow definitions.
- search workflows
- terminate workflow
- create event handler
- create task definitions
- get task definition
- list task definitions
- update task execution status.
- create an event handler.
- list workflow definitions
- create a new workflow definition.
- update task
- get workflow definition
- workflow orchestration
- create new task definitions.
- task definition management.
- conductor
- delete a workflow execution.
- workflow definition management.
- pause a running workflow.
- individual workflow execution.
- get workflow execution status.
- orchestration
- task management
- get a task definition.
- start a new workflow.
- resume workflow
- get a workflow definition by name.
- delete workflow execution
- workflows
- delete a workflow definition.
- start workflow
- get workflow execution
- list all task definitions.
- search for workflow executions.
- create workflow definition
- get a workflow definition.
- poll for task
- create a workflow definition.
- workflow execution management.
- resume a paused workflow.
- terminate a running workflow.
- poll for a task to execute.
- individual workflow definition.
- automation
slug: workflow-orchestration
source_filename: workflow-orchestration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Conductor Workflow Orchestration\n  description: Unified workflow for managing workflow definitions, task definitions, workflow executions, and event handlers.\n    Used by backend developers and DevOps engineers.\n  tags:\n  - Conductor\n  - Workflow Orchestration\n  - Task Management\n  - Automation\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    CONDUCTOR_API_TOKEN: CONDUCTOR_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: conductor\n    baseUri: https://play.orkes.io/api\n    description: Conductor API for workflow and task orchestration.\n    authentication:\n      type: bearer\n      token: '{{CONDUCTOR_API_TOKEN}}'\n    resources:\n    - name: workflow-definitions\n      path: /metadata/workflow\n      description: Workflow definition management.\n      operations:\n      - name: create-workflow-definition\n        method: POST\n        description: Create a new workflow\
  \ definition.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: get-all-workflow-definitions\n        method: GET\n        description: Get all workflow definitions.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-workflow-definitions\n        method: PUT\n        description: Update workflow definitions.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflow-definition-details\n      path: /metadata/workflow/{name}\n      description: Individual workflow definition management.\n      operations:\n      - name: get-workflow-definition\n        method: GET\n        description: Get a workflow definition by name.\n  \
  \      inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Workflow name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-workflow-definition\n        method: DELETE\n        description: Delete a workflow definition.\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Workflow name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: task-definitions\n      path: /metadata/taskdefs\n      description: Task definition management.\n      operations:\n      - name: create-task-definitions\n        method: POST\n        description: Create new task definitions.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: get-all-task-definitions\n        method: GET\n        description: Get all task definitions.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-task-definition\n        method: PUT\n        description: Update a task definition.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: task-definition-details\n      path: /metadata/taskdefs/{taskType}\n      description: Individual task definition management.\n      operations:\n      - name: get-task-definition\n        method: GET\n        description: Get a task definition.\n        inputParameters:\n        - name: taskType\n          in: path\n          type: string\n          required: true\n          description: Task type.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: delete-task-definition\n        method: DELETE\n        description: Delete a task definition.\n        inputParameters:\n        - name: taskType\n          in: path\n          type: string\n          required: true\n          description: Task type.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflow-executions\n      path: /workflow\n      description: Workflow execution management.\n      operations:\n      - name: start-workflow\n        method: POST\n        description: Start a new workflow.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n    - name: workflow-execution-details\n      path: /workflow/{workflowId}\n      description: Individual\
  \ workflow execution management.\n      operations:\n      - name: get-workflow-execution\n        method: GET\n        description: Get workflow execution status.\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n          description: Workflow ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-workflow-execution\n        method: DELETE\n        description: Delete a workflow execution.\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n          description: Workflow ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflow-lifecycle\n      path: /workflow/{workflowId}\n      description: Workflow lifecycle operations.\n      operations:\n    \
  \  - name: pause-workflow\n        method: PUT\n        description: Pause a running workflow.\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n          description: Workflow ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: resume-workflow\n        method: PUT\n        description: Resume a paused workflow.\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n          description: Workflow ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: terminate-workflow\n        method: DELETE\n        description: Terminate a running workflow.\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required:\
  \ true\n          description: Workflow ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflow-search\n      path: /workflow/search\n      description: Workflow search.\n      operations:\n      - name: search-workflows\n        method: GET\n        description: Search for workflow executions.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tasks\n      path: /tasks\n      description: Task operations.\n      operations:\n      - name: update-task\n        method: POST\n        description: Update task status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: task-polling\n      path: /tasks/poll/{taskType}\n      description: Task polling.\n      operations:\n      - name: poll-for-task\n        method: GET\n\
  \        description: Poll for a task.\n        inputParameters:\n        - name: taskType\n          in: path\n          type: string\n          required: true\n          description: Task type.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event-handlers\n      path: /event\n      description: Event handler management.\n      operations:\n      - name: create-event-handler\n        method: POST\n        description: Create an event handler.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-all-event-handlers\n        method: GET\n        description: Get all event handlers.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-event-handler\n        method: PUT\n        description: Update an event handler.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: workflow-orchestration-api\n    description: Unified REST API for Conductor workflow orchestration.\n    resources:\n    - path: /v1/workflow-definitions\n      name: workflow-definitions\n      description: Workflow definition management.\n      operations:\n      - method: GET\n        name: list-workflow-definitions\n        description: List all workflow definitions.\n        call: conductor.get-all-workflow-definitions\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-workflow-definition\n        description: Create a workflow definition.\n        call: conductor.create-workflow-definition\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workflow-definitions/{id}\n      name: workflow-definition-details\n\
  \      description: Individual workflow definition.\n      operations:\n      - method: GET\n        name: get-workflow-definition\n        description: Get a workflow definition.\n        call: conductor.get-workflow-definition\n        with:\n          name: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-workflow-definition\n        description: Delete a workflow definition.\n        call: conductor.delete-workflow-definition\n        with:\n          name: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/task-definitions\n      name: task-definitions\n      description: Task definition management.\n      operations:\n      - method: GET\n        name: list-task-definitions\n        description: List all task definitions.\n        call: conductor.get-all-task-definitions\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method:\
  \ POST\n        name: create-task-definitions\n        description: Create task definitions.\n        call: conductor.create-task-definitions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workflows\n      name: workflows\n      description: Workflow execution management.\n      operations:\n      - method: POST\n        name: start-workflow\n        description: Start a new workflow.\n        call: conductor.start-workflow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workflows/{id}\n      name: workflow-details\n      description: Individual workflow execution.\n      operations:\n      - method: GET\n        name: get-workflow-execution\n        description: Get workflow execution status.\n        call: conductor.get-workflow-execution\n        with:\n          workflowId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-workflow-execution\n\
  \        description: Delete a workflow execution.\n        call: conductor.delete-workflow-execution\n        with:\n          workflowId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: workflow-orchestration-mcp\n    transport: http\n    description: MCP server for AI-assisted workflow orchestration.\n    tools:\n    - name: list-workflow-definitions\n      description: List all workflow definitions.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: conductor.get-all-workflow-definitions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-workflow-definition\n      description: Get a workflow definition by name.\n      hints:\n        readOnly: true\n      call: conductor.get-workflow-definition\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-workflow-definition\n   \
  \   description: Create a new workflow definition.\n      hints:\n        readOnly: false\n      call: conductor.create-workflow-definition\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-workflow-definition\n      description: Delete a workflow definition.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: conductor.delete-workflow-definition\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-task-definitions\n      description: List all task definitions.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: conductor.get-all-task-definitions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-task-definition\n      description: Get a task definition.\n      hints:\n        readOnly: true\n      call: conductor.get-task-definition\n      with:\n        taskType: tools.taskType\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-task-definitions\n      description: Create new task definitions.\n      hints:\n        readOnly: false\n      call: conductor.create-task-definitions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-workflow\n      description: Start a new workflow execution.\n      hints:\n        readOnly: false\n      call: conductor.start-workflow\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-workflow-execution\n      description: Get workflow execution status.\n      hints:\n        readOnly: true\n      call: conductor.get-workflow-execution\n      with:\n        workflowId: tools.workflowId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pause-workflow\n      description: Pause a running workflow.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: conductor.pause-workflow\n\
  \      with:\n        workflowId: tools.workflowId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: resume-workflow\n      description: Resume a paused workflow.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: conductor.resume-workflow\n      with:\n        workflowId: tools.workflowId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: terminate-workflow\n      description: Terminate a running workflow.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: conductor.terminate-workflow\n      with:\n        workflowId: tools.workflowId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-workflows\n      description: Search for workflow executions.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: conductor.search-workflows\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: poll-for-task\n      description: Poll for a task to execute.\n      hints:\n        readOnly: true\n      call: conductor.poll-for-task\n      with:\n        taskType: tools.taskType\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-task\n      description: Update task execution status.\n      hints:\n        readOnly: false\n      call: conductor.update-task\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-event-handlers\n      description: List all event handlers.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: conductor.get-all-event-handlers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-event-handler\n      description: Create an event handler.\n      hints:\n        readOnly: false\n      call: conductor.create-event-handler\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/conductor/refs/heads/main/capabilities/workflow-orchestration.yaml
tags:
- Conductor
- Workflow Orchestration
- Task Management
- Automation
tools:
- description: List all workflow definitions.
  hints:
    openWorld: true
    readOnly: true
  name: list-workflow-definitions
- description: Get a workflow definition by name.
  hints:
    readOnly: true
  name: get-workflow-definition
- description: Create a new workflow definition.
  hints:
    readOnly: false
  name: create-workflow-definition
- description: Delete a workflow definition.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-workflow-definition
- description: List all task definitions.
  hints:
    openWorld: true
    readOnly: true
  name: list-task-definitions
- description: Get a task definition.
  hints:
    readOnly: true
  name: get-task-definition
- description: Create new task definitions.
  hints:
    readOnly: false
  name: create-task-definitions
- description: Start a new workflow execution.
  hints:
    readOnly: false
  name: start-workflow
- description: Get workflow execution status.
  hints:
    readOnly: true
  name: get-workflow-execution
- description: Pause a running workflow.
  hints:
    idempotent: true
    readOnly: false
  name: pause-workflow
- description: Resume a paused workflow.
  hints:
    idempotent: true
    readOnly: false
  name: resume-workflow
- description: Terminate a running workflow.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: terminate-workflow
- description: Search for workflow executions.
  hints:
    openWorld: true
    readOnly: true
  name: search-workflows
- description: Poll for a task to execute.
  hints:
    readOnly: true
  name: poll-for-task
- description: Update task execution status.
  hints:
    readOnly: false
  name: update-task
- description: List all event handlers.
  hints:
    openWorld: true
    readOnly: true
  name: list-event-handlers
- description: Create an event handler.
  hints:
    readOnly: false
  name: create-event-handler
---
