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
- start a new workflow execution.
- list task definitions
- resume a paused workflow.
- automation
- update task
- pause a running workflow.
- delete a workflow execution.
- get workflow execution
- pause workflow
- create task definitions
- poll for a task to execute.
- list workflow definitions
- start a new workflow.
- get workflow execution status.
- search for workflow executions.
- list all task definitions.
- create task definitions.
- create a new workflow definition.
- state
- create a workflow definition.
- start workflow
- orchestration
- get a workflow definition.
- get workflow definition
- delete workflow execution
- search workflows
- workflows
- create an event handler.
- poll for task
- terminate a running workflow.
- create event handler
- workflow definition management.
- terminate workflow
- delete workflow definition
- get a task definition.
- get task definition
- tasks
- individual workflow execution.
- workflow execution management.
- workflow orchestration
- get a workflow definition by name.
- list all workflow definitions.
- create workflow definition
- create new task definitions.
- update task execution status.
- list event handlers
- individual workflow definition.
- task definition management.
- conductor
- delete a workflow definition.
- list all event handlers.
- task management
- resume workflow
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
