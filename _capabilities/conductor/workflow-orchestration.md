---
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
- conductor
- get workflow execution status.
- delete workflow definition
- create new task definitions.
- individual workflow execution.
- state
- delete a workflow definition.
- delete workflow execution
- automation
- task definition management.
- terminate a running workflow.
- search for workflow executions.
- resume workflow
- workflow execution management.
- list event handlers
- workflows
- create a workflow definition.
- delete a workflow execution.
- update task execution status.
- workflow orchestration
- create an event handler.
- get a workflow definition.
- list task definitions
- get workflow execution
- get workflow definition
- start a new workflow.
- pause a running workflow.
- get task definition
- start workflow
- resume a paused workflow.
- list all task definitions.
- individual workflow definition.
- pause workflow
- terminate workflow
- update task
- tasks
- list workflow definitions
- start a new workflow execution.
- create event handler
- create task definitions
- list all workflow definitions.
- search workflows
- workflow definition management.
- task management
- list all event handlers.
- create task definitions.
- create workflow definition
- get a task definition.
- poll for task
- create a new workflow definition.
- get a workflow definition by name.
- poll for a task to execute.
- orchestration
slug: workflow-orchestration
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
