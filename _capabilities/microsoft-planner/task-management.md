---
categories:
- collaboration
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
- collaboration
- create a new task in a plan
- list all buckets in a plan
- manage tasks
- delete bucket
- create a new bucket in a plan
- planner
- list group plans
- get plan details
- get task details
- delete task
- get bucket details
- list all tasks in a plan
- get details of a specific bucket
- create bucket
- update bucket
- get plan
- get plan details including category labels
- create plan
- delete a task
- delete plan
- update a plan
- delete a plan
- create a new task
- manage plans
- create task
- task management
- get task details including checklist and references
- get details of a specific plan
- microsoft
- list tasks assigned to the current user
- update plan
- update task details
- update a bucket
- create a new bucket
- manage a specific plan
- microsoft 365
- list plan tasks
- manage buckets
- update task details including checklist items
- update a task
- get bucket
- get task
- get details of a specific task
- create a new plan
- manage a specific bucket
- create a new planner plan
- list bucket tasks
- delete a bucket
- productivity
- update task
- list plan buckets
- manage a specific task
- list my tasks
- project management
- update plan details
- list plans for a group
- list tasks in a specific bucket
slug: task-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Microsoft Planner Task Management\"\n  description: \"Manage plans, tasks, and buckets in Microsoft Planner for team collaboration and project management. Used by project managers and team leads.\"\n  tags:\n    - Microsoft\n    - Planner\n    - Task Management\n    - Collaboration\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      MICROSOFT_GRAPH_TOKEN: MICROSOFT_GRAPH_TOKEN\n\ncapability:\n  consumes:\n    - import: planner\n      location: ./shared/planner.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: planner-task-api\n      description: \"Unified REST API for Microsoft Planner task management.\"\n      resources:\n        - path: /v1/plans\n          name: plans\n          description: \"Manage plans\"\n          operations:\n            - method: POST\n              name: create-plan\n              description: \"Create a new plan\"\n          \
  \    call: \"planner.create-plan\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-group-plans\n              description: \"List plans for a group\"\n              call: \"planner.list-plan-tasks\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/plans/{planId}\n          name: plan\n          description: \"Manage a specific plan\"\n          operations:\n            - method: GET\n              name: get-plan\n              description: \"Get plan details\"\n              call: \"planner.get-plan\"\n              with:\n                planId: \"rest.planId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-plan\n              description: \"Update a plan\"\n              call: \"planner.update-plan\"\n\
  \              with:\n                planId: \"rest.planId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-plan\n              description: \"Delete a plan\"\n              call: \"planner.delete-plan\"\n              with:\n                planId: \"rest.planId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tasks\n          name: tasks\n          description: \"Manage tasks\"\n          operations:\n            - method: POST\n              name: create-task\n              description: \"Create a new task\"\n              call: \"planner.create-task\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tasks/{taskId}\n          name: task\n          description: \"Manage a specific task\"\n          operations:\n            - method:\
  \ GET\n              name: get-task\n              description: \"Get task details\"\n              call: \"planner.get-task\"\n              with:\n                taskId: \"rest.taskId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-task\n              description: \"Update a task\"\n              call: \"planner.update-task\"\n              with:\n                taskId: \"rest.taskId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-task\n              description: \"Delete a task\"\n              call: \"planner.delete-task\"\n              with:\n                taskId: \"rest.taskId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/buckets\n          name: buckets\n          description: \"\
  Manage buckets\"\n          operations:\n            - method: POST\n              name: create-bucket\n              description: \"Create a new bucket\"\n              call: \"planner.create-bucket\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/buckets/{bucketId}\n          name: bucket\n          description: \"Manage a specific bucket\"\n          operations:\n            - method: GET\n              name: get-bucket\n              description: \"Get bucket details\"\n              call: \"planner.get-bucket\"\n              with:\n                bucketId: \"rest.bucketId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-bucket\n              description: \"Update a bucket\"\n              call: \"planner.update-bucket\"\n              with:\n                bucketId: \"rest.bucketId\"\n           \
  \   outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-bucket\n              description: \"Delete a bucket\"\n              call: \"planner.delete-bucket\"\n              with:\n                bucketId: \"rest.bucketId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: planner-task-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Microsoft Planner task management.\"\n      tools:\n        - name: create-plan\n          description: \"Create a new Planner plan\"\n          hints:\n            readOnly: false\n          call: \"planner.create-plan\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-plan\n          description: \"Get details of a specific plan\"\n          hints:\n            readOnly: true\n\
  \          call: \"planner.get-plan\"\n          with:\n            planId: \"tools.planId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-plan\n          description: \"Update a plan\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"planner.update-plan\"\n          with:\n            planId: \"tools.planId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-plan\n          description: \"Delete a plan\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"planner.delete-plan\"\n          with:\n            planId: \"tools.planId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-plan-tasks\n          description: \"List all tasks in a plan\"\n          hints:\n            readOnly: true\n          call: \"planner.list-plan-tasks\"\
  \n          with:\n            planId: \"tools.planId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-plan-buckets\n          description: \"List all buckets in a plan\"\n          hints:\n            readOnly: true\n          call: \"planner.list-plan-buckets\"\n          with:\n            planId: \"tools.planId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-plan-details\n          description: \"Get plan details including category labels\"\n          hints:\n            readOnly: true\n          call: \"planner.get-plan-details\"\n          with:\n            planId: \"tools.planId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-plan-details\n          description: \"Update plan details\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"planner.update-plan-details\"\
  \n          with:\n            planId: \"tools.planId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-task\n          description: \"Create a new task in a plan\"\n          hints:\n            readOnly: false\n          call: \"planner.create-task\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-task\n          description: \"Get details of a specific task\"\n          hints:\n            readOnly: true\n          call: \"planner.get-task\"\n          with:\n            taskId: \"tools.taskId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-task\n          description: \"Update a task\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"planner.update-task\"\n          with:\n            taskId: \"tools.taskId\"\n          outputParameters:\n        \
  \    - type: object\n              mapping: \"$.\"\n        - name: delete-task\n          description: \"Delete a task\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"planner.delete-task\"\n          with:\n            taskId: \"tools.taskId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-task-details\n          description: \"Get task details including checklist and references\"\n          hints:\n            readOnly: true\n          call: \"planner.get-task-details\"\n          with:\n            taskId: \"tools.taskId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-task-details\n          description: \"Update task details including checklist items\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"planner.update-task-details\"\n          with:\n          \
  \  taskId: \"tools.taskId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-bucket\n          description: \"Create a new bucket in a plan\"\n          hints:\n            readOnly: false\n          call: \"planner.create-bucket\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-bucket\n          description: \"Get details of a specific bucket\"\n          hints:\n            readOnly: true\n          call: \"planner.get-bucket\"\n          with:\n            bucketId: \"tools.bucketId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-bucket\n          description: \"Update a bucket\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"planner.update-bucket\"\n          with:\n            bucketId: \"tools.bucketId\"\n          outputParameters:\n          \
  \  - type: object\n              mapping: \"$.\"\n        - name: delete-bucket\n          description: \"Delete a bucket\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"planner.delete-bucket\"\n          with:\n            bucketId: \"tools.bucketId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-bucket-tasks\n          description: \"List tasks in a specific bucket\"\n          hints:\n            readOnly: true\n          call: \"planner.list-bucket-tasks\"\n          with:\n            bucketId: \"tools.bucketId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-my-tasks\n          description: \"List tasks assigned to the current user\"\n          hints:\n            readOnly: true\n          call: \"planner.list-my-tasks\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-planner/refs/heads/main/capabilities/task-management.yaml
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
