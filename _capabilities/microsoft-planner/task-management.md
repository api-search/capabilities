---
categories:
- collaboration
consumed_apis: []
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
- manage a specific task
- list plans for a group
- get plan details
- task management
- planner
- list group plans
- microsoft 365
- get details of a specific task
- list bucket tasks
- delete a task
- update bucket
- list all tasks in a plan
- manage a specific bucket
- delete a bucket
- update a task
- list plan buckets
- update a bucket
- get task
- update plan details
- productivity
- project management
- delete plan
- get bucket details
- microsoft
- manage a specific plan
- collaboration
- get task details including checklist and references
- create a new plan
- create a new bucket in a plan
- create bucket
- manage plans
- create task
- update task details
- manage buckets
- list my tasks
- update task
- get task details
- update plan
- list tasks in a specific bucket
- get details of a specific plan
- list all buckets in a plan
- delete a plan
- delete bucket
- create a new planner plan
- delete task
- update task details including checklist items
- create plan
- create a new task
- get plan
- create a new bucket
- get bucket
- manage tasks
- update a plan
- create a new task in a plan
- list tasks assigned to the current user
- get details of a specific bucket
- list plan tasks
- get plan details including category labels
slug: task-management
source_filename: task-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Microsoft Planner Task Management\n  description: Manage plans, tasks, and buckets in Microsoft Planner for team collaboration and project management. Used by\n    project managers and team leads.\n  tags:\n  - Microsoft\n  - Planner\n  - Task Management\n  - Collaboration\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    MICROSOFT_GRAPH_TOKEN: MICROSOFT_GRAPH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: planner\n    baseUri: https://graph.microsoft.com/v1.0\n    description: Microsoft Graph Planner API\n    authentication:\n      type: bearer\n      token: '{{MICROSOFT_GRAPH_TOKEN}}'\n    resources:\n    - name: plans\n      path: /planner/plans\n      description: Manage Planner plans\n      operations:\n      - name: create-plan\n        method: POST\n        description: Create a new plan\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n \
  \         type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            container:\n              url: '{{tools.containerUrl}}'\n      - name: get-plan\n        method: GET\n        description: Get a plan by ID\n        inputParameters:\n        - name: planId\n          in: path\n          type: string\n          required: true\n          description: The plan ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-plan\n        method: PATCH\n        description: Update a plan\n        inputParameters:\n        - name: planId\n          in: path\n          type: string\n          required: true\n          description: The plan ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n   \
  \         title: '{{tools.title}}'\n      - name: delete-plan\n        method: DELETE\n        description: Delete a plan\n        inputParameters:\n        - name: planId\n          in: path\n          type: string\n          required: true\n          description: The plan ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-plan-tasks\n        method: GET\n        description: List tasks in a plan\n        inputParameters:\n        - name: planId\n          in: path\n          type: string\n          required: true\n          description: The plan ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-plan-buckets\n        method: GET\n        description: List buckets in a plan\n        inputParameters:\n        - name: planId\n          in: path\n          type: string\n          required: true\n\
  \          description: The plan ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-plan-details\n        method: GET\n        description: Get plan details\n        inputParameters:\n        - name: planId\n          in: path\n          type: string\n          required: true\n          description: The plan ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-plan-details\n        method: PATCH\n        description: Update plan details\n        inputParameters:\n        - name: planId\n          in: path\n          type: string\n          required: true\n          description: The plan ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tasks\n      path: /planner/tasks\n      description: Manage Planner\
  \ tasks\n      operations:\n      - name: create-task\n        method: POST\n        description: Create a new task\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            planId: '{{tools.planId}}'\n            title: '{{tools.title}}'\n            bucketId: '{{tools.bucketId}}'\n      - name: get-task\n        method: GET\n        description: Get a task by ID\n        inputParameters:\n        - name: taskId\n          in: path\n          type: string\n          required: true\n          description: The task ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-task\n        method: PATCH\n        description: Update a task\n        inputParameters:\n        - name: taskId\n          in: path\n          type: string\n          required: true\n      \
  \    description: The task ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-task\n        method: DELETE\n        description: Delete a task\n        inputParameters:\n        - name: taskId\n          in: path\n          type: string\n          required: true\n          description: The task ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-task-details\n        method: GET\n        description: Get task details including checklist and references\n        inputParameters:\n        - name: taskId\n          in: path\n          type: string\n          required: true\n          description: The task ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-task-details\n        method: PATCH\n   \
  \     description: Update task details\n        inputParameters:\n        - name: taskId\n          in: path\n          type: string\n          required: true\n          description: The task ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: buckets\n      path: /planner/buckets\n      description: Manage Planner buckets\n      operations:\n      - name: create-bucket\n        method: POST\n        description: Create a new bucket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            planId: '{{tools.planId}}'\n      - name: get-bucket\n        method: GET\n        description: Get a bucket by ID\n        inputParameters:\n        - name: bucketId\n          in: path\n          type: string\n          required: true\n   \
  \       description: The bucket ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-bucket\n        method: PATCH\n        description: Update a bucket\n        inputParameters:\n        - name: bucketId\n          in: path\n          type: string\n          required: true\n          description: The bucket ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-bucket\n        method: DELETE\n        description: Delete a bucket\n        inputParameters:\n        - name: bucketId\n          in: path\n          type: string\n          required: true\n          description: The bucket ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-bucket-tasks\n        method: GET\n        description: List tasks\
  \ in a bucket\n        inputParameters:\n        - name: bucketId\n          in: path\n          type: string\n          required: true\n          description: The bucket ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-tasks\n      path: /me/planner/tasks\n      description: Access user tasks\n      operations:\n      - name: list-my-tasks\n        method: GET\n        description: List tasks assigned to the current user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: planner-task-api\n    description: Unified REST API for Microsoft Planner task management.\n    resources:\n    - path: /v1/plans\n      name: plans\n      description: Manage plans\n      operations:\n      - method: POST\n        name: create-plan\n        description: Create a new plan\n\
  \        call: planner.create-plan\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-group-plans\n        description: List plans for a group\n        call: planner.list-plan-tasks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/plans/{planId}\n      name: plan\n      description: Manage a specific plan\n      operations:\n      - method: GET\n        name: get-plan\n        description: Get plan details\n        call: planner.get-plan\n        with:\n          planId: rest.planId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-plan\n        description: Update a plan\n        call: planner.update-plan\n        with:\n          planId: rest.planId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-plan\n        description: Delete a plan\n  \
  \      call: planner.delete-plan\n        with:\n          planId: rest.planId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tasks\n      name: tasks\n      description: Manage tasks\n      operations:\n      - method: POST\n        name: create-task\n        description: Create a new task\n        call: planner.create-task\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tasks/{taskId}\n      name: task\n      description: Manage a specific task\n      operations:\n      - method: GET\n        name: get-task\n        description: Get task details\n        call: planner.get-task\n        with:\n          taskId: rest.taskId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-task\n        description: Update a task\n        call: planner.update-task\n        with:\n          taskId: rest.taskId\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n      - method: DELETE\n        name: delete-task\n        description: Delete a task\n        call: planner.delete-task\n        with:\n          taskId: rest.taskId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/buckets\n      name: buckets\n      description: Manage buckets\n      operations:\n      - method: POST\n        name: create-bucket\n        description: Create a new bucket\n        call: planner.create-bucket\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/buckets/{bucketId}\n      name: bucket\n      description: Manage a specific bucket\n      operations:\n      - method: GET\n        name: get-bucket\n        description: Get bucket details\n        call: planner.get-bucket\n        with:\n          bucketId: rest.bucketId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-bucket\n  \
  \      description: Update a bucket\n        call: planner.update-bucket\n        with:\n          bucketId: rest.bucketId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-bucket\n        description: Delete a bucket\n        call: planner.delete-bucket\n        with:\n          bucketId: rest.bucketId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: planner-task-mcp\n    transport: http\n    description: MCP server for AI-assisted Microsoft Planner task management.\n    tools:\n    - name: create-plan\n      description: Create a new Planner plan\n      hints:\n        readOnly: false\n      call: planner.create-plan\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-plan\n      description: Get details of a specific plan\n      hints:\n        readOnly: true\n      call: planner.get-plan\n      with:\n       \
  \ planId: tools.planId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-plan\n      description: Update a plan\n      hints:\n        readOnly: false\n        idempotent: true\n      call: planner.update-plan\n      with:\n        planId: tools.planId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-plan\n      description: Delete a plan\n      hints:\n        destructive: true\n        idempotent: true\n      call: planner.delete-plan\n      with:\n        planId: tools.planId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-plan-tasks\n      description: List all tasks in a plan\n      hints:\n        readOnly: true\n      call: planner.list-plan-tasks\n      with:\n        planId: tools.planId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-plan-buckets\n      description: List all buckets in a plan\n      hints:\n        readOnly:\
  \ true\n      call: planner.list-plan-buckets\n      with:\n        planId: tools.planId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-plan-details\n      description: Get plan details including category labels\n      hints:\n        readOnly: true\n      call: planner.get-plan-details\n      with:\n        planId: tools.planId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-plan-details\n      description: Update plan details\n      hints:\n        readOnly: false\n        idempotent: true\n      call: planner.update-plan-details\n      with:\n        planId: tools.planId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-task\n      description: Create a new task in a plan\n      hints:\n        readOnly: false\n      call: planner.create-task\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-task\n      description: Get details of a specific\
  \ task\n      hints:\n        readOnly: true\n      call: planner.get-task\n      with:\n        taskId: tools.taskId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-task\n      description: Update a task\n      hints:\n        readOnly: false\n        idempotent: true\n      call: planner.update-task\n      with:\n        taskId: tools.taskId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-task\n      description: Delete a task\n      hints:\n        destructive: true\n        idempotent: true\n      call: planner.delete-task\n      with:\n        taskId: tools.taskId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-task-details\n      description: Get task details including checklist and references\n      hints:\n        readOnly: true\n      call: planner.get-task-details\n      with:\n        taskId: tools.taskId\n      outputParameters:\n      - type: object\n      \
  \  mapping: $.\n    - name: update-task-details\n      description: Update task details including checklist items\n      hints:\n        readOnly: false\n        idempotent: true\n      call: planner.update-task-details\n      with:\n        taskId: tools.taskId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-bucket\n      description: Create a new bucket in a plan\n      hints:\n        readOnly: false\n      call: planner.create-bucket\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-bucket\n      description: Get details of a specific bucket\n      hints:\n        readOnly: true\n      call: planner.get-bucket\n      with:\n        bucketId: tools.bucketId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-bucket\n      description: Update a bucket\n      hints:\n        readOnly: false\n        idempotent: true\n      call: planner.update-bucket\n      with:\n        bucketId:\
  \ tools.bucketId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-bucket\n      description: Delete a bucket\n      hints:\n        destructive: true\n        idempotent: true\n      call: planner.delete-bucket\n      with:\n        bucketId: tools.bucketId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-bucket-tasks\n      description: List tasks in a specific bucket\n      hints:\n        readOnly: true\n      call: planner.list-bucket-tasks\n      with:\n        bucketId: tools.bucketId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-my-tasks\n      description: List tasks assigned to the current user\n      hints:\n        readOnly: true\n      call: planner.list-my-tasks\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
