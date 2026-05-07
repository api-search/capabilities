---
categories: []
consumed_apis: []
description: The Google Tasks API lets you search, read, and update Google Tasks content and metadata. You can manage task lists and individual tasks, including creating, updating, moving, and deleting tasks programmatically.
layout: capability
name: Google Tasks API
operations:
- description: List task lists
  method: GET
  name: listtasklists
  path: /users/@me/lists
- description: Create a task list
  method: POST
  name: inserttasklist
  path: /users/@me/lists
- description: Get a task list
  method: GET
  name: gettasklist
  path: /users/@me/lists/{taskListId}
- description: Update a task list
  method: PUT
  name: updatetasklist
  path: /users/@me/lists/{taskListId}
- description: Patch a task list
  method: PATCH
  name: patchtasklist
  path: /users/@me/lists/{taskListId}
- description: Delete a task list
  method: DELETE
  name: deletetasklist
  path: /users/@me/lists/{taskListId}
- description: List tasks
  method: GET
  name: listtasks
  path: /lists/{taskListId}/tasks
- description: Create a task
  method: POST
  name: inserttask
  path: /lists/{taskListId}/tasks
- description: Get a task
  method: GET
  name: gettask
  path: /lists/{taskListId}/tasks/{taskId}
- description: Update a task
  method: PUT
  name: updatetask
  path: /lists/{taskListId}/tasks/{taskId}
- description: Delete a task
  method: DELETE
  name: deletetask
  path: /lists/{taskListId}/tasks/{taskId}
- description: Move a task
  method: POST
  name: movetask
  path: /lists/{taskListId}/tasks/{taskId}/move
- description: Clear completed tasks
  method: POST
  name: cleartasks
  path: /lists/{taskListId}/clear
personas: []
provider_name: Google Tasks
provider_slug: google-tasks
search_terms:
- listtasks
- task management
- inserttask
- todo
- delete a task
- api
- move a task
- get a task list
- workspace
- get a task
- update a task
- gettask
- google
- list tasks
- productivity
- patch a task list
- inserttasklist
- patchtasklist
- cleartasks
- create a task
- tasks
- deletetasklist
- update a task list
- updatetask
- clear completed tasks
- create a task list
- updatetasklist
- deletetask
- delete a task list
- list task lists
- listtasklists
- gettasklist
- movetask
slug: google-tasks-capability
source_filename: google-tasks-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Tasks API\n  description: The Google Tasks API lets you search, read, and update Google Tasks content and metadata. You can manage task\n    lists and individual tasks, including creating, updating, moving, and deleting tasks programmatically.\n  tags:\n  - Google\n  - Tasks\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-tasks\n    baseUri: https://tasks.googleapis.com/tasks/v1\n    description: Google Tasks API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_TASKS_TOKEN}}'\n    resources:\n    - name: users-me-lists\n      path: /users/@me/lists\n      operations:\n      - name: listtasklists\n        method: GET\n        description: List task lists\n        inputParameters:\n        - name: maxResults\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n   \
  \     outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: inserttasklist\n        method: POST\n        description: Create a task list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-me-lists-tasklistid\n      path: /users/@me/lists/{taskListId}\n      operations:\n      - name: gettasklist\n        method: GET\n        description: Get a task list\n        inputParameters:\n        - name: taskListId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatetasklist\n        method: PUT\n        description: Update a task list\n        inputParameters:\n        - name: taskListId\n          in: path\n          type: string\n          required: true\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchtasklist\n        method: PATCH\n        description: Patch a task list\n        inputParameters:\n        - name: taskListId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetasklist\n        method: DELETE\n        description: Delete a task list\n        inputParameters:\n        - name: taskListId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lists-tasklistid-tasks\n      path: /lists/{taskListId}/tasks\n      operations:\n      - name: listtasks\n        method: GET\n        description: List tasks\n        inputParameters:\n\
  \        - name: taskListId\n          in: path\n          type: string\n          required: true\n        - name: maxResults\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        - name: showCompleted\n          in: query\n          type: boolean\n        - name: showHidden\n          in: query\n          type: boolean\n        - name: dueMin\n          in: query\n          type: string\n        - name: dueMax\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: inserttask\n        method: POST\n        description: Create a task\n        inputParameters:\n        - name: taskListId\n          in: path\n          type: string\n          required: true\n        - name: parent\n          in: query\n          type: string\n        - name: previous\n          in: query\n          type:\
  \ string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lists-tasklistid-tasks-taskid\n      path: /lists/{taskListId}/tasks/{taskId}\n      operations:\n      - name: gettask\n        method: GET\n        description: Get a task\n        inputParameters:\n        - name: taskListId\n          in: path\n          type: string\n          required: true\n        - name: taskId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatetask\n        method: PUT\n        description: Update a task\n        inputParameters:\n        - name: taskListId\n          in: path\n          type: string\n          required: true\n        - name: taskId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetask\n        method: DELETE\n        description: Delete a task\n        inputParameters:\n        - name: taskListId\n          in: path\n          type: string\n          required: true\n        - name: taskId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lists-tasklistid-tasks-taskid-move\n      path: /lists/{taskListId}/tasks/{taskId}/move\n      operations:\n      - name: movetask\n        method: POST\n        description: Move a task\n        inputParameters:\n        - name: taskListId\n          in: path\n          type: string\n          required: true\n        - name: taskId\n          in: path\n          type: string\n          required: true\n        - name: parent\n          in: query\n        \
  \  type: string\n        - name: previous\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lists-tasklistid-clear\n      path: /lists/{taskListId}/clear\n      operations:\n      - name: cleartasks\n        method: POST\n        description: Clear completed tasks\n        inputParameters:\n        - name: taskListId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-tasks-rest\n    description: REST adapter for Google Tasks API.\n    resources:\n    - path: /users/@me/lists\n      name: listtasklists\n      operations:\n      - method: GET\n        name: listtasklists\n        description: List task lists\n        call: google-tasks.listtasklists\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/@me/lists\n      name: inserttasklist\n      operations:\n      - method: POST\n        name: inserttasklist\n        description: Create a task list\n        call: google-tasks.inserttasklist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/@me/lists/{taskListId}\n      name: gettasklist\n      operations:\n      - method: GET\n        name: gettasklist\n        description: Get a task list\n        call: google-tasks.gettasklist\n        with:\n          taskListId: rest.taskListId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/@me/lists/{taskListId}\n      name: updatetasklist\n      operations:\n      - method: PUT\n        name: updatetasklist\n        description: Update a task list\n        call: google-tasks.updatetasklist\n        with:\n          taskListId: rest.taskListId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /users/@me/lists/{taskListId}\n      name: patchtasklist\n      operations:\n      - method: PATCH\n        name: patchtasklist\n        description: Patch a task list\n        call: google-tasks.patchtasklist\n        with:\n          taskListId: rest.taskListId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/@me/lists/{taskListId}\n      name: deletetasklist\n      operations:\n      - method: DELETE\n        name: deletetasklist\n        description: Delete a task list\n        call: google-tasks.deletetasklist\n        with:\n          taskListId: rest.taskListId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /lists/{taskListId}/tasks\n      name: listtasks\n      operations:\n      - method: GET\n        name: listtasks\n        description: List tasks\n        call: google-tasks.listtasks\n        with:\n          taskListId: rest.taskListId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /lists/{taskListId}/tasks\n      name: inserttask\n      operations:\n      - method: POST\n        name: inserttask\n        description: Create a task\n        call: google-tasks.inserttask\n        with:\n          taskListId: rest.taskListId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /lists/{taskListId}/tasks/{taskId}\n      name: gettask\n      operations:\n      - method: GET\n        name: gettask\n        description: Get a task\n        call: google-tasks.gettask\n        with:\n          taskListId: rest.taskListId\n          taskId: rest.taskId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /lists/{taskListId}/tasks/{taskId}\n      name: updatetask\n      operations:\n      - method: PUT\n        name: updatetask\n        description: Update a task\n        call: google-tasks.updatetask\n        with:\n   \
  \       taskListId: rest.taskListId\n          taskId: rest.taskId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /lists/{taskListId}/tasks/{taskId}\n      name: deletetask\n      operations:\n      - method: DELETE\n        name: deletetask\n        description: Delete a task\n        call: google-tasks.deletetask\n        with:\n          taskListId: rest.taskListId\n          taskId: rest.taskId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /lists/{taskListId}/tasks/{taskId}/move\n      name: movetask\n      operations:\n      - method: POST\n        name: movetask\n        description: Move a task\n        call: google-tasks.movetask\n        with:\n          taskListId: rest.taskListId\n          taskId: rest.taskId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /lists/{taskListId}/clear\n      name: cleartasks\n      operations:\n      - method: POST\n        name:\
  \ cleartasks\n        description: Clear completed tasks\n        call: google-tasks.cleartasks\n        with:\n          taskListId: rest.taskListId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-tasks-mcp\n    transport: http\n    description: MCP adapter for Google Tasks API for AI agent use.\n    tools:\n    - name: listtasklists\n      description: List task lists\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-tasks.listtasklists\n      with:\n        maxResults: tools.maxResults\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: maxResults\n        type: integer\n        description: maxResults\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: inserttasklist\n      description: Create a task list\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-tasks.inserttasklist\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettasklist\n      description: Get a task list\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-tasks.gettasklist\n      with:\n        taskListId: tools.taskListId\n      inputParameters:\n      - name: taskListId\n        type: string\n        description: taskListId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatetasklist\n      description: Update a task list\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: google-tasks.updatetasklist\n      with:\n        taskListId: tools.taskListId\n      inputParameters:\n      - name: taskListId\n        type: string\n        description: taskListId\n        required:\
  \ true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchtasklist\n      description: Patch a task list\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-tasks.patchtasklist\n      with:\n        taskListId: tools.taskListId\n      inputParameters:\n      - name: taskListId\n        type: string\n        description: taskListId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletetasklist\n      description: Delete a task list\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-tasks.deletetasklist\n      with:\n        taskListId: tools.taskListId\n      inputParameters:\n      - name: taskListId\n        type: string\n        description: taskListId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtasks\n     \
  \ description: List tasks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-tasks.listtasks\n      with:\n        taskListId: tools.taskListId\n        maxResults: tools.maxResults\n        pageToken: tools.pageToken\n        showCompleted: tools.showCompleted\n        showHidden: tools.showHidden\n        dueMin: tools.dueMin\n        dueMax: tools.dueMax\n      inputParameters:\n      - name: taskListId\n        type: string\n        description: taskListId\n        required: true\n      - name: maxResults\n        type: integer\n        description: maxResults\n      - name: pageToken\n        type: string\n        description: pageToken\n      - name: showCompleted\n        type: boolean\n        description: showCompleted\n      - name: showHidden\n        type: boolean\n        description: showHidden\n      - name: dueMin\n        type: string\n        description: dueMin\n      - name: dueMax\n        type: string\n\
  \        description: dueMax\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: inserttask\n      description: Create a task\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-tasks.inserttask\n      with:\n        taskListId: tools.taskListId\n        parent: tools.parent\n        previous: tools.previous\n      inputParameters:\n      - name: taskListId\n        type: string\n        description: taskListId\n        required: true\n      - name: parent\n        type: string\n        description: parent\n      - name: previous\n        type: string\n        description: previous\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettask\n      description: Get a task\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-tasks.gettask\n      with:\n        taskListId: tools.taskListId\n        taskId: tools.taskId\n\
  \      inputParameters:\n      - name: taskListId\n        type: string\n        description: taskListId\n        required: true\n      - name: taskId\n        type: string\n        description: taskId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatetask\n      description: Update a task\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: google-tasks.updatetask\n      with:\n        taskListId: tools.taskListId\n        taskId: tools.taskId\n      inputParameters:\n      - name: taskListId\n        type: string\n        description: taskListId\n        required: true\n      - name: taskId\n        type: string\n        description: taskId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletetask\n      description: Delete a task\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent:\
  \ true\n      call: google-tasks.deletetask\n      with:\n        taskListId: tools.taskListId\n        taskId: tools.taskId\n      inputParameters:\n      - name: taskListId\n        type: string\n        description: taskListId\n        required: true\n      - name: taskId\n        type: string\n        description: taskId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: movetask\n      description: Move a task\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-tasks.movetask\n      with:\n        taskListId: tools.taskListId\n        taskId: tools.taskId\n        parent: tools.parent\n        previous: tools.previous\n      inputParameters:\n      - name: taskListId\n        type: string\n        description: taskListId\n        required: true\n      - name: taskId\n        type: string\n        description: taskId\n        required: true\n      - name: parent\n   \
  \     type: string\n        description: parent\n      - name: previous\n        type: string\n        description: previous\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cleartasks\n      description: Clear completed tasks\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-tasks.cleartasks\n      with:\n        taskListId: tools.taskListId\n      inputParameters:\n      - name: taskListId\n        type: string\n        description: taskListId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_TASKS_TOKEN: GOOGLE_TASKS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-tasks/refs/heads/main/capabilities/google-tasks-capability.yaml
tags:
- Google
- Tasks
- API
tools:
- description: List task lists
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtasklists
- description: Create a task list
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: inserttasklist
- description: Get a task list
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettasklist
- description: Update a task list
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatetasklist
- description: Patch a task list
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchtasklist
- description: Delete a task list
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetasklist
- description: List tasks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtasks
- description: Create a task
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: inserttask
- description: Get a task
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettask
- description: Update a task
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatetask
- description: Delete a task
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetask
- description: Move a task
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: movetask
- description: Clear completed tasks
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: cleartasks
---
