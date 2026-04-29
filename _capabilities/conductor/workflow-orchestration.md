---
categories: []
consumed_apis:
- conductor
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
- resume a paused workflow.
- list all event handlers.
- workflow execution management.
- list all task definitions.
- start a new workflow.
- create task definitions.
- create a new workflow definition.
- create a workflow definition.
- individual workflow definition.
- list event handlers
- create workflow definition
- list task definitions
- task management
- start workflow
- pause a running workflow.
- delete a workflow execution.
- automation
- resume workflow
- create an event handler.
- workflow orchestration
- list workflow definitions
- get workflow definition
- get a workflow definition by name.
- update task
- get a task definition.
- update task execution status.
- list all workflow definitions.
- start a new workflow execution.
- delete a workflow definition.
- terminate a running workflow.
- delete workflow definition
- get workflow execution status.
- search workflows
- tasks
- create new task definitions.
- create event handler
- poll for task
- terminate workflow
- task definition management.
- individual workflow execution.
- poll for a task to execute.
- create task definitions
- workflows
- pause workflow
- conductor
- get workflow execution
- delete workflow execution
- search for workflow executions.
- get task definition
- orchestration
- state
- workflow definition management.
- get a workflow definition.
slug: workflow-orchestration
source_filename: workflow-orchestration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Conductor Workflow Orchestration\"\n  description: \"Unified workflow for managing workflow definitions, task definitions, workflow executions, and event handlers. Used by backend developers and DevOps engineers.\"\n  tags:\n    - Conductor\n    - Workflow Orchestration\n    - Task Management\n    - Automation\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      CONDUCTOR_API_TOKEN: CONDUCTOR_API_TOKEN\n\ncapability:\n  consumes:\n    - import: conductor\n      location: ./shared/conductor.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: workflow-orchestration-api\n      description: \"Unified REST API for Conductor workflow orchestration.\"\n      resources:\n        - path: /v1/workflow-definitions\n          name: workflow-definitions\n          description: \"Workflow definition management.\"\n          operations:\n            - method: GET\n       \
  \       name: list-workflow-definitions\n              description: \"List all workflow definitions.\"\n              call: \"conductor.get-all-workflow-definitions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-workflow-definition\n              description: \"Create a workflow definition.\"\n              call: \"conductor.create-workflow-definition\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workflow-definitions/{id}\n          name: workflow-definition-details\n          description: \"Individual workflow definition.\"\n          operations:\n            - method: GET\n              name: get-workflow-definition\n              description: \"Get a workflow definition.\"\n              call: \"conductor.get-workflow-definition\"\n              with:\n                name: \"rest.id\"\n          \
  \    outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-workflow-definition\n              description: \"Delete a workflow definition.\"\n              call: \"conductor.delete-workflow-definition\"\n              with:\n                name: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/task-definitions\n          name: task-definitions\n          description: \"Task definition management.\"\n          operations:\n            - method: GET\n              name: list-task-definitions\n              description: \"List all task definitions.\"\n              call: \"conductor.get-all-task-definitions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-task-definitions\n              description: \"Create task\
  \ definitions.\"\n              call: \"conductor.create-task-definitions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workflows\n          name: workflows\n          description: \"Workflow execution management.\"\n          operations:\n            - method: POST\n              name: start-workflow\n              description: \"Start a new workflow.\"\n              call: \"conductor.start-workflow\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workflows/{id}\n          name: workflow-details\n          description: \"Individual workflow execution.\"\n          operations:\n            - method: GET\n              name: get-workflow-execution\n              description: \"Get workflow execution status.\"\n              call: \"conductor.get-workflow-execution\"\n              with:\n                workflowId: \"rest.id\"\n        \
  \      outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-workflow-execution\n              description: \"Delete a workflow execution.\"\n              call: \"conductor.delete-workflow-execution\"\n              with:\n                workflowId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: workflow-orchestration-mcp\n      transport: http\n      description: \"MCP server for AI-assisted workflow orchestration.\"\n      tools:\n        - name: list-workflow-definitions\n          description: \"List all workflow definitions.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"conductor.get-all-workflow-definitions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-workflow-definition\n\
  \          description: \"Get a workflow definition by name.\"\n          hints:\n            readOnly: true\n          call: \"conductor.get-workflow-definition\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-workflow-definition\n          description: \"Create a new workflow definition.\"\n          hints:\n            readOnly: false\n          call: \"conductor.create-workflow-definition\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-workflow-definition\n          description: \"Delete a workflow definition.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"conductor.delete-workflow-definition\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: list-task-definitions\n          description: \"List all task definitions.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"conductor.get-all-task-definitions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-task-definition\n          description: \"Get a task definition.\"\n          hints:\n            readOnly: true\n          call: \"conductor.get-task-definition\"\n          with:\n            taskType: \"tools.taskType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-task-definitions\n          description: \"Create new task definitions.\"\n          hints:\n            readOnly: false\n          call: \"conductor.create-task-definitions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: start-workflow\n          description: \"\
  Start a new workflow execution.\"\n          hints:\n            readOnly: false\n          call: \"conductor.start-workflow\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-workflow-execution\n          description: \"Get workflow execution status.\"\n          hints:\n            readOnly: true\n          call: \"conductor.get-workflow-execution\"\n          with:\n            workflowId: \"tools.workflowId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: pause-workflow\n          description: \"Pause a running workflow.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"conductor.pause-workflow\"\n          with:\n            workflowId: \"tools.workflowId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: resume-workflow\n          description: \"Resume a paused\
  \ workflow.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"conductor.resume-workflow\"\n          with:\n            workflowId: \"tools.workflowId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: terminate-workflow\n          description: \"Terminate a running workflow.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"conductor.terminate-workflow\"\n          with:\n            workflowId: \"tools.workflowId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-workflows\n          description: \"Search for workflow executions.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"conductor.search-workflows\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n \
  \       - name: poll-for-task\n          description: \"Poll for a task to execute.\"\n          hints:\n            readOnly: true\n          call: \"conductor.poll-for-task\"\n          with:\n            taskType: \"tools.taskType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-task\n          description: \"Update task execution status.\"\n          hints:\n            readOnly: false\n          call: \"conductor.update-task\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-event-handlers\n          description: \"List all event handlers.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"conductor.get-all-event-handlers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-event-handler\n          description: \"Create an event handler.\"\n          hints:\n\
  \            readOnly: false\n          call: \"conductor.create-event-handler\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
