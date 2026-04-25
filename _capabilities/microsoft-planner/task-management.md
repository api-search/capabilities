---
consumed_apis:
- planner
description: Manage plans, tasks, and buckets in Microsoft Planner for team collaboration and project management. Used by project managers and team leads.
layout: capability
name: Microsoft Planner Task Management
operations:
- description: Create a new plan
  method: POST
  name: create-plan
  path: /v1/plans
- description: List plans for a group
  method: GET
  name: list-group-plans
  path: /v1/plans
- description: Get plan details
  method: GET
  name: get-plan
  path: /v1/plans/{planId}
- description: Update a plan
  method: PATCH
  name: update-plan
  path: /v1/plans/{planId}
- description: Delete a plan
  method: DELETE
  name: delete-plan
  path: /v1/plans/{planId}
- description: Create a new task
  method: POST
  name: create-task
  path: /v1/tasks
- description: Get task details
  method: GET
  name: get-task
  path: /v1/tasks/{taskId}
- description: Update a task
  method: PATCH
  name: update-task
  path: /v1/tasks/{taskId}
- description: Delete a task
  method: DELETE
  name: delete-task
  path: /v1/tasks/{taskId}
- description: Create a new bucket
  method: POST
  name: create-bucket
  path: /v1/buckets
- description: Get bucket details
  method: GET
  name: get-bucket
  path: /v1/buckets/{bucketId}
- description: Update a bucket
  method: PATCH
  name: update-bucket
  path: /v1/buckets/{bucketId}
- description: Delete a bucket
  method: DELETE
  name: delete-bucket
  path: /v1/buckets/{bucketId}
personas: []
provider_name: Microsoft Planner
provider_slug: microsoft-planner
search_terms:
- planner
- productivity
- list plans for a group
- manage a specific plan
- manage buckets
- manage tasks
- list all buckets in a plan
- delete plan
- create a new bucket in a plan
- get bucket details
- collaboration
- project management
- task management
- list all tasks in a plan
- list bucket tasks
- update task details including checklist items
- update plan
- update a plan
- update task details
- delete a task
- delete task
- update a bucket
- delete bucket
- list plan buckets
- get details of a specific bucket
- update a task
- delete a bucket
- list my tasks
- get plan details
- create a new planner plan
- get plan details including category labels
- list tasks assigned to the current user
- create plan
- manage a specific bucket
- get plan
- manage a specific task
- create a new bucket
- microsoft
- update bucket
- get details of a specific plan
- microsoft 365
- update plan details
- list tasks in a specific bucket
- create a new task
- manage plans
- get task details including checklist and references
- create task
- create a new plan
- update task
- create a new task in a plan
- list group plans
- get details of a specific task
- create bucket
- get bucket
- list plan tasks
- get task details
- delete a plan
- get task
slug: task-management
tags:
- Microsoft
- Planner
- Task Management
- Collaboration
tools:
- description: Create a new Planner plan
  hints:
    readOnly: false
  name: create-plan
- description: Get details of a specific plan
  hints:
    readOnly: true
  name: get-plan
- description: Update a plan
  hints:
    idempotent: true
    readOnly: false
  name: update-plan
- description: Delete a plan
  hints:
    destructive: true
    idempotent: true
  name: delete-plan
- description: List all tasks in a plan
  hints:
    readOnly: true
  name: list-plan-tasks
- description: List all buckets in a plan
  hints:
    readOnly: true
  name: list-plan-buckets
- description: Get plan details including category labels
  hints:
    readOnly: true
  name: get-plan-details
- description: Update plan details
  hints:
    idempotent: true
    readOnly: false
  name: update-plan-details
- description: Create a new task in a plan
  hints:
    readOnly: false
  name: create-task
- description: Get details of a specific task
  hints:
    readOnly: true
  name: get-task
- description: Update a task
  hints:
    idempotent: true
    readOnly: false
  name: update-task
- description: Delete a task
  hints:
    destructive: true
    idempotent: true
  name: delete-task
- description: Get task details including checklist and references
  hints:
    readOnly: true
  name: get-task-details
- description: Update task details including checklist items
  hints:
    idempotent: true
    readOnly: false
  name: update-task-details
- description: Create a new bucket in a plan
  hints:
    readOnly: false
  name: create-bucket
- description: Get details of a specific bucket
  hints:
    readOnly: true
  name: get-bucket
- description: Update a bucket
  hints:
    idempotent: true
    readOnly: false
  name: update-bucket
- description: Delete a bucket
  hints:
    destructive: true
    idempotent: true
  name: delete-bucket
- description: List tasks in a specific bucket
  hints:
    readOnly: true
  name: list-bucket-tasks
- description: List tasks assigned to the current user
  hints:
    readOnly: true
  name: list-my-tasks
---
