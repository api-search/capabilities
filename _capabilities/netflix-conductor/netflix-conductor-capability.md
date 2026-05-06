---
categories: []
consumed_apis: []
description: The Conductor REST API provides endpoints for managing workflow definitions, executing workflows, handling tasks, and managing metadata in the Conductor microservices orchestration engine.
layout: capability
name: Netflix Conductor REST API
operations:
- description: List workflow definitions
  method: GET
  name: listworkflowdefinitions
  path: /metadata/workflow
- description: Register a workflow definition
  method: POST
  name: registerworkflowdefinition
  path: /metadata/workflow
- description: Update workflow definitions
  method: PUT
  name: updateworkflowdefinitions
  path: /metadata/workflow
- description: Get workflow definition
  method: GET
  name: getworkflowdefinition
  path: /metadata/workflow/{name}
- description: Delete a workflow definition
  method: DELETE
  name: deleteworkflowdefinition
  path: /metadata/workflow/{name}
- description: List task definitions
  method: GET
  name: listtaskdefinitions
  path: /metadata/taskdefs
- description: Register task definitions
  method: POST
  name: registertaskdefinitions
  path: /metadata/taskdefs
- description: Get task definition
  method: GET
  name: gettaskdefinition
  path: /metadata/taskdefs/{taskType}
- description: Delete a task definition
  method: DELETE
  name: deletetaskdefinition
  path: /metadata/taskdefs/{taskType}
- description: Start a workflow
  method: POST
  name: startworkflow
  path: /workflow
- description: Get workflow execution
  method: GET
  name: getworkflow
  path: /workflow/{workflowId}
- description: Terminate a workflow
  method: DELETE
  name: terminateworkflow
  path: /workflow/{workflowId}
- description: Pause a workflow
  method: PUT
  name: pauseworkflow
  path: /workflow/{workflowId}/pause
- description: Resume a workflow
  method: PUT
  name: resumeworkflow
  path: /workflow/{workflowId}/resume
- description: Restart a workflow
  method: POST
  name: restartworkflow
  path: /workflow/{workflowId}/restart
- description: Retry a workflow
  method: POST
  name: retryworkflow
  path: /workflow/{workflowId}/retry
- description: Rerun a workflow
  method: POST
  name: rerunworkflow
  path: /workflow/{workflowId}/rerun
- description: Skip a task
  method: PUT
  name: skiptask
  path: /workflow/{workflowId}/skiptask/{taskReferenceName}
- description: Search workflows
  method: GET
  name: searchworkflows
  path: /workflow/search
- description: Poll for a task
  method: GET
  name: polltask
  path: /tasks/poll/{taskType}
- description: Batch poll for tasks
  method: GET
  name: batchpolltasks
  path: /tasks/poll/batch/{taskType}
- description: Update task status
  method: POST
  name: updatetask
  path: /tasks
- description: Get task details
  method: GET
  name: gettask
  path: /tasks/{taskId}
- description: Get task queue sizes
  method: GET
  name: gettaskqueuesizes
  path: /tasks/queue/sizes
- description: List event handlers
  method: GET
  name: listeventhandlers
  path: /event
- description: Create event handler
  method: POST
  name: createeventhandler
  path: /event
personas: []
provider_name: Netflix Conductor
provider_slug: netflix-conductor
search_terms:
- startworkflow
- listworkflowdefinitions
- start a workflow
- listeventhandlers
- searchworkflows
- list event handlers
- gettask
- skiptask
- updatetask
- update task status
- get task queue sizes
- deletetaskdefinition
- getworkflowdefinition
- get task details
- search workflows
- updateworkflowdefinitions
- netflix
- create event handler
- get task definition
- list task definitions
- pauseworkflow
- skip a task
- createeventhandler
- list workflow definitions
- get workflow definition
- delete a task definition
- gettaskdefinition
- open source
- update workflow definitions
- gettaskqueuesizes
- conductor
- restartworkflow
- pause a workflow
- orchestration
- registertaskdefinitions
- restart a workflow
- api
- retry a workflow
- batch poll for tasks
- workflows
- rerun a workflow
- delete a workflow definition
- register task definitions
- polltask
- get workflow execution
- register a workflow definition
- event-driven
- getworkflow
- resumeworkflow
- poll for a task
- terminateworkflow
- terminate a workflow
- registerworkflowdefinition
- rerunworkflow
- listtaskdefinitions
- microservices
- deleteworkflowdefinition
- batchpolltasks
- retryworkflow
- resume a workflow
slug: netflix-conductor-capability
source_filename: netflix-conductor-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Netflix Conductor REST API\n  description: The Conductor REST API provides endpoints for managing workflow definitions, executing workflows, handling\n    tasks, and managing metadata in the Conductor microservices orchestration engine.\n  tags:\n  - Netflix\n  - Conductor\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: netflix-conductor\n    baseUri: http://localhost:8080/api\n    description: Netflix Conductor REST API HTTP API.\n    resources:\n    - name: metadata-workflow\n      path: /metadata/workflow\n      operations:\n      - name: listworkflowdefinitions\n        method: GET\n        description: List workflow definitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: registerworkflowdefinition\n        method: POST\n        description: Register a workflow definition\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateworkflowdefinitions\n        method: PUT\n        description: Update workflow definitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metadata-workflow-name\n      path: /metadata/workflow/{name}\n      operations:\n      - name: getworkflowdefinition\n        method: GET\n        description: Get workflow definition\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        - name: version\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteworkflowdefinition\n        method: DELETE\n        description: Delete a workflow definition\n   \
  \     inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        - name: version\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metadata-taskdefs\n      path: /metadata/taskdefs\n      operations:\n      - name: listtaskdefinitions\n        method: GET\n        description: List task definitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: registertaskdefinitions\n        method: POST\n        description: Register task definitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metadata-taskdefs-tasktype\n      path: /metadata/taskdefs/{taskType}\n      operations:\n      - name: gettaskdefinition\n     \
  \   method: GET\n        description: Get task definition\n        inputParameters:\n        - name: taskType\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetaskdefinition\n        method: DELETE\n        description: Delete a task definition\n        inputParameters:\n        - name: taskType\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflow\n      path: /workflow\n      operations:\n      - name: startworkflow\n        method: POST\n        description: Start a workflow\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflow-workflowid\n      path: /workflow/{workflowId}\n\
  \      operations:\n      - name: getworkflow\n        method: GET\n        description: Get workflow execution\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n        - name: includeTasks\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: terminateworkflow\n        method: DELETE\n        description: Terminate a workflow\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n        - name: reason\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflow-workflowid-pause\n      path: /workflow/{workflowId}/pause\n      operations:\n      - name: pauseworkflow\n        method:\
  \ PUT\n        description: Pause a workflow\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflow-workflowid-resume\n      path: /workflow/{workflowId}/resume\n      operations:\n      - name: resumeworkflow\n        method: PUT\n        description: Resume a workflow\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflow-workflowid-restart\n      path: /workflow/{workflowId}/restart\n      operations:\n      - name: restartworkflow\n        method: POST\n        description: Restart a workflow\n        inputParameters:\n        - name: workflowId\n      \
  \    in: path\n          type: string\n          required: true\n        - name: useLatestDefinitions\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflow-workflowid-retry\n      path: /workflow/{workflowId}/retry\n      operations:\n      - name: retryworkflow\n        method: POST\n        description: Retry a workflow\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n        - name: resumeSubworkflowTasks\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflow-workflowid-rerun\n      path: /workflow/{workflowId}/rerun\n      operations:\n      - name: rerunworkflow\n        method: POST\n        description: Rerun a workflow\n      \
  \  inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflow-workflowid-skiptask-taskreferencename\n      path: /workflow/{workflowId}/skiptask/{taskReferenceName}\n      operations:\n      - name: skiptask\n        method: PUT\n        description: Skip a task\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n        - name: taskReferenceName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflow-search\n      path: /workflow/search\n      operations:\n      - name: searchworkflows\n        method: GET\n        description: Search workflows\n     \
  \   inputParameters:\n        - name: start\n          in: query\n          type: integer\n        - name: size\n          in: query\n          type: integer\n        - name: sort\n          in: query\n          type: string\n        - name: freeText\n          in: query\n          type: string\n        - name: query\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tasks-poll-tasktype\n      path: /tasks/poll/{taskType}\n      operations:\n      - name: polltask\n        method: GET\n        description: Poll for a task\n        inputParameters:\n        - name: taskType\n          in: path\n          type: string\n          required: true\n        - name: workerid\n          in: query\n          type: string\n        - name: domain\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: tasks-poll-batch-tasktype\n      path: /tasks/poll/batch/{taskType}\n      operations:\n      - name: batchpolltasks\n        method: GET\n        description: Batch poll for tasks\n        inputParameters:\n        - name: taskType\n          in: path\n          type: string\n          required: true\n        - name: workerid\n          in: query\n          type: string\n        - name: count\n          in: query\n          type: integer\n        - name: timeout\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tasks\n      path: /tasks\n      operations:\n      - name: updatetask\n        method: POST\n        description: Update task status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tasks-taskid\n\
  \      path: /tasks/{taskId}\n      operations:\n      - name: gettask\n        method: GET\n        description: Get task details\n        inputParameters:\n        - name: taskId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tasks-queue-sizes\n      path: /tasks/queue/sizes\n      operations:\n      - name: gettaskqueuesizes\n        method: GET\n        description: Get task queue sizes\n        inputParameters:\n        - name: taskType\n          in: query\n          type: array\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event\n      path: /event\n      operations:\n      - name: listeventhandlers\n        method: GET\n        description: List event handlers\n        outputRawFormat: json\n        outputParameters:\n      \
  \  - name: result\n          type: object\n          value: $.\n      - name: createeventhandler\n        method: POST\n        description: Create event handler\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: netflix-conductor-rest\n    description: REST adapter for Netflix Conductor REST API.\n    resources:\n    - path: /metadata/workflow\n      name: listworkflowdefinitions\n      operations:\n      - method: GET\n        name: listworkflowdefinitions\n        description: List workflow definitions\n        call: netflix-conductor.listworkflowdefinitions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/workflow\n      name: registerworkflowdefinition\n      operations:\n      - method: POST\n        name: registerworkflowdefinition\n        description: Register a workflow definition\n        call:\
  \ netflix-conductor.registerworkflowdefinition\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/workflow\n      name: updateworkflowdefinitions\n      operations:\n      - method: PUT\n        name: updateworkflowdefinitions\n        description: Update workflow definitions\n        call: netflix-conductor.updateworkflowdefinitions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/workflow/{name}\n      name: getworkflowdefinition\n      operations:\n      - method: GET\n        name: getworkflowdefinition\n        description: Get workflow definition\n        call: netflix-conductor.getworkflowdefinition\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/workflow/{name}\n      name: deleteworkflowdefinition\n      operations:\n      - method: DELETE\n        name: deleteworkflowdefinition\n        description:\
  \ Delete a workflow definition\n        call: netflix-conductor.deleteworkflowdefinition\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/taskdefs\n      name: listtaskdefinitions\n      operations:\n      - method: GET\n        name: listtaskdefinitions\n        description: List task definitions\n        call: netflix-conductor.listtaskdefinitions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/taskdefs\n      name: registertaskdefinitions\n      operations:\n      - method: POST\n        name: registertaskdefinitions\n        description: Register task definitions\n        call: netflix-conductor.registertaskdefinitions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/taskdefs/{taskType}\n      name: gettaskdefinition\n      operations:\n      - method: GET\n        name: gettaskdefinition\n       \
  \ description: Get task definition\n        call: netflix-conductor.gettaskdefinition\n        with:\n          taskType: rest.taskType\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/taskdefs/{taskType}\n      name: deletetaskdefinition\n      operations:\n      - method: DELETE\n        name: deletetaskdefinition\n        description: Delete a task definition\n        call: netflix-conductor.deletetaskdefinition\n        with:\n          taskType: rest.taskType\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflow\n      name: startworkflow\n      operations:\n      - method: POST\n        name: startworkflow\n        description: Start a workflow\n        call: netflix-conductor.startworkflow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflow/{workflowId}\n      name: getworkflow\n      operations:\n      - method: GET\n        name: getworkflow\n\
  \        description: Get workflow execution\n        call: netflix-conductor.getworkflow\n        with:\n          workflowId: rest.workflowId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflow/{workflowId}\n      name: terminateworkflow\n      operations:\n      - method: DELETE\n        name: terminateworkflow\n        description: Terminate a workflow\n        call: netflix-conductor.terminateworkflow\n        with:\n          workflowId: rest.workflowId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflow/{workflowId}/pause\n      name: pauseworkflow\n      operations:\n      - method: PUT\n        name: pauseworkflow\n        description: Pause a workflow\n        call: netflix-conductor.pauseworkflow\n        with:\n          workflowId: rest.workflowId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflow/{workflowId}/resume\n      name: resumeworkflow\n\
  \      operations:\n      - method: PUT\n        name: resumeworkflow\n        description: Resume a workflow\n        call: netflix-conductor.resumeworkflow\n        with:\n          workflowId: rest.workflowId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflow/{workflowId}/restart\n      name: restartworkflow\n      operations:\n      - method: POST\n        name: restartworkflow\n        description: Restart a workflow\n        call: netflix-conductor.restartworkflow\n        with:\n          workflowId: rest.workflowId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflow/{workflowId}/retry\n      name: retryworkflow\n      operations:\n      - method: POST\n        name: retryworkflow\n        description: Retry a workflow\n        call: netflix-conductor.retryworkflow\n        with:\n          workflowId: rest.workflowId\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /workflow/{workflowId}/rerun\n      name: rerunworkflow\n      operations:\n      - method: POST\n        name: rerunworkflow\n        description: Rerun a workflow\n        call: netflix-conductor.rerunworkflow\n        with:\n          workflowId: rest.workflowId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflow/{workflowId}/skiptask/{taskReferenceName}\n      name: skiptask\n      operations:\n      - method: PUT\n        name: skiptask\n        description: Skip a task\n        call: netflix-conductor.skiptask\n        with:\n          workflowId: rest.workflowId\n          taskReferenceName: rest.taskReferenceName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflow/search\n      name: searchworkflows\n      operations:\n      - method: GET\n        name: searchworkflows\n        description: Search workflows\n        call: netflix-conductor.searchworkflows\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /tasks/poll/{taskType}\n      name: polltask\n      operations:\n      - method: GET\n        name: polltask\n        description: Poll for a task\n        call: netflix-conductor.polltask\n        with:\n          taskType: rest.taskType\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tasks/poll/batch/{taskType}\n      name: batchpolltasks\n      operations:\n      - method: GET\n        name: batchpolltasks\n        description: Batch poll for tasks\n        call: netflix-conductor.batchpolltasks\n        with:\n          taskType: rest.taskType\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tasks\n      name: updatetask\n      operations:\n      - method: POST\n        name: updatetask\n        description: Update task status\n        call: netflix-conductor.updatetask\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /tasks/{taskId}\n      name: gettask\n      operations:\n      - method: GET\n        name: gettask\n        description: Get task details\n        call: netflix-conductor.gettask\n        with:\n          taskId: rest.taskId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tasks/queue/sizes\n      name: gettaskqueuesizes\n      operations:\n      - method: GET\n        name: gettaskqueuesizes\n        description: Get task queue sizes\n        call: netflix-conductor.gettaskqueuesizes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /event\n      name: listeventhandlers\n      operations:\n      - method: GET\n        name: listeventhandlers\n        description: List event handlers\n        call: netflix-conductor.listeventhandlers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /event\n      name: createeventhandler\n      operations:\n      - method: POST\n\
  \        name: createeventhandler\n        description: Create event handler\n        call: netflix-conductor.createeventhandler\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: netflix-conductor-mcp\n    transport: http\n    description: MCP adapter for Netflix Conductor REST API for AI agent use.\n    tools:\n    - name: listworkflowdefinitions\n      description: List workflow definitions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: netflix-conductor.listworkflowdefinitions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: registerworkflowdefinition\n      description: Register a workflow definition\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: netflix-conductor.registerworkflowdefinition\n      outputParameters:\n      - type: object\n        mapping: $.\n    -\
  \ name: updateworkflowdefinitions\n      description: Update workflow definitions\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: netflix-conductor.updateworkflowdefinitions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getworkflowdefinition\n      description: Get workflow definition\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: netflix-conductor.getworkflowdefinition\n      with:\n        name: tools.name\n        version: tools.version\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      - name: version\n        type: integer\n        description: version\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteworkflowdefinition\n      description: Delete a workflow definition\n      hints:\n        readOnly: false\n        destructive:\
  \ true\n        idempotent: true\n      call: netflix-conductor.deleteworkflowdefinition\n      with:\n        name: tools.name\n        version: tools.version\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      - name: version\n        type: integer\n        description: version\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtaskdefinitions\n      description: List task definitions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: netflix-conductor.listtaskdefinitions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: registertaskdefinitions\n      description: Register task definitions\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: netflix-conductor.registertaskdefinitions\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: gettaskdefinition\n      description: Get task definition\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: netflix-conductor.gettaskdefinition\n      with:\n        taskType: tools.taskType\n      inputParameters:\n      - name: taskType\n        type: string\n        description: taskType\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletetaskdefinition\n      description: Delete a task definition\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: netflix-conductor.deletetaskdefinition\n      with:\n        taskType: tools.taskType\n      inputParameters:\n      - name: taskType\n        type: string\n        description: taskType\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: startworkflow\n      description: Start a workflow\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: false\n      call: netflix-conductor.startworkflow\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getworkflow\n      description: Get workflow execution\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: netflix-conductor.getworkflow\n      with:\n        workflowId: tools.workflowId\n        includeTasks: tools.includeTasks\n      inputParameters:\n      - name: workflowId\n        type: string\n        description: workflowId\n        required: true\n      - name: includeTasks\n        type: boolean\n        description: includeTasks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: terminateworkflow\n      description: Terminate a workflow\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: netflix-conductor.terminateworkflow\n      with:\n\
  \        workflowId: tools.workflowId\n        reason: tools.reason\n      inputParameters:\n      - name: workflowId\n        type: string\n        description: workflowId\n        required: true\n      - name: reason\n        type: string\n        description: reason\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pauseworkflow\n      description: Pause a workflow\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: netflix-conductor.pauseworkflow\n      with:\n        workflowId: tools.workflowId\n      inputParameters:\n      - name: workflowId\n        type: string\n        description: workflowId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: resumeworkflow\n      description: Resume a workflow\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: netflix-conductor.resumeworkflow\n     \
  \ with:\n        workflowId: tools.workflowId\n      inputParameters:\n      - name: workflowId\n        type: string\n        description: workflowId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: restartworkflow\n      description: Restart a workflow\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: netflix-conductor.restartworkflow\n      with:\n        workflowId: tools.workflowId\n        useLatestDefinitions: tools.useLatestDefinitions\n      inputParameters:\n      - name: workflowId\n        type: string\n        description: workflowId\n        required: true\n      - name: useLatestDefinitions\n        type: boolean\n        description: useLatestDefinitions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retryworkflow\n      description: Retry a workflow\n      hints:\n        readOnly: false\n        destructive: false\n       \
  \ idempotent: false\n      call: netflix-conductor.retryworkflow\n      with:\n        workflowId: tools.workflowId\n        resumeSubworkflowTasks: tools.resumeSubworkflowTasks\n      inputParameters:\n      - name: workflowId\n        type: string\n        description: workflowId\n        required: true\n      - name: resumeSubworkflowTasks\n        type: boolean\n        description: resumeSubworkflowTasks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: rerunworkflow\n      description: Rerun a workflow\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: netflix-conductor.rerunworkflow\n      with:\n        workflowId: tools.workflowId\n      inputParameters:\n      - name: workflowId\n        type: string\n        description: workflowId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: skiptask\n      description: Skip a task\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: true\n      call: netflix-conductor.skiptask\n      with:\n        workflowId: tools.workflowId\n        taskReferenceName: tools.taskReferenceName\n      inputParameters:\n      - name: workflowId\n        type: string\n        description: workflowId\n        required: true\n      - name: taskReferenceName\n        type: string\n        description: taskReferenceName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchworkflows\n      description: Search workflows\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: netflix-conductor.searchworkflows\n      with:\n        start: tools.start\n        size: tools.size\n        sort: tools.sort\n        freeText: tools.freeText\n        query: tools.query\n      inputParameters:\n      - name: start\n        type: integer\n        description: start\n    \
  \  - name: size\n        type: integer\n        description: size\n      - name: sort\n        type: string\n        description: sort\n      - name: freeText\n        type: string\n        description: freeText\n      - name: query\n        type: string\n        description: query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: polltask\n      description: Poll for a task\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: netflix-conductor.polltask\n      with:\n        taskType: tools.taskType\n        workerid: tools.workerid\n        domain: tools.domain\n      inputParameters:\n      - name: taskType\n        type: string\n        description: taskType\n        required: true\n      - name: workerid\n        type: string\n        description: workerid\n      - name: domain\n        type: string\n        description: domain\n      outputParameters:\n      - type: object\n        mapping: $.\n   \
  \ - name: batchpolltasks\n      description: Batch poll for tasks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: netflix-conductor.batchpolltasks\n      with:\n        taskType: tools.taskType\n        workerid: tools.workerid\n        count: tools.count\n        timeout: tools.timeout\n      inputParameters:\n      - name: taskType\n        type: string\n        description: taskType\n        required: true\n      - name: workerid\n        type: string\n        description: workerid\n      - name: count\n        type: integer\n        description: count\n      - name: timeout\n        type: integer\n        description: timeout\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatetask\n      description: Update task status\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: netflix-conductor.updatetask\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: gettask\n      description: Get task details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: netflix-conductor.gettask\n      with:\n        taskId: tools.taskId\n      inputParameters:\n      - name: taskId\n        type: string\n        description: taskId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettaskqueuesizes\n      description: Get task queue sizes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: netflix-conductor.gettaskqueuesizes\n      with:\n        taskType: tools.taskType\n      inputParameters:\n      - name: taskType\n        type: array\n        description: taskType\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listeventhandlers\n      description: List event handlers\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: netflix-conductor.listeventhandlers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createeventhandler\n      description: Create event handler\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: netflix-conductor.createeventhandler\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/netflix-conductor/refs/heads/main/capabilities/netflix-conductor-capability.yaml
tags:
- Netflix
- Conductor
- API
tools:
- description: List workflow definitions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listworkflowdefinitions
- description: Register a workflow definition
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: registerworkflowdefinition
- description: Update workflow definitions
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateworkflowdefinitions
- description: Get workflow definition
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getworkflowdefinition
- description: Delete a workflow definition
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteworkflowdefinition
- description: List task definitions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtaskdefinitions
- description: Register task definitions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: registertaskdefinitions
- description: Get task definition
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettaskdefinition
- description: Delete a task definition
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetaskdefinition
- description: Start a workflow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: startworkflow
- description: Get workflow execution
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getworkflow
- description: Terminate a workflow
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: terminateworkflow
- description: Pause a workflow
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: pauseworkflow
- description: Resume a workflow
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: resumeworkflow
- description: Restart a workflow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: restartworkflow
- description: Retry a workflow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: retryworkflow
- description: Rerun a workflow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: rerunworkflow
- description: Skip a task
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: skiptask
- description: Search workflows
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchworkflows
- description: Poll for a task
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: polltask
- description: Batch poll for tasks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: batchpolltasks
- description: Update task status
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatetask
- description: Get task details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettask
- description: Get task queue sizes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettaskqueuesizes
- description: List event handlers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listeventhandlers
- description: Create event handler
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createeventhandler
---
