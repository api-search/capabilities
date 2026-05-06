---
categories: []
consumed_apis: []
description: The Orkes Conductor REST API provides endpoints for managing workflows, tasks, human tasks, secrets, schedules, and other resources in the Orkes workflow orchestration platform built on Netflix Conductor.
layout: capability
name: Orkes Conductor REST API
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
  name: getworkflowexecution
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
- description: Retry a workflow
  method: POST
  name: retryworkflow
  path: /workflow/{workflowId}/retry
- description: Restart a workflow
  method: POST
  name: restartworkflow
  path: /workflow/{workflowId}/restart
- description: Search workflows
  method: GET
  name: searchworkflows
  path: /workflow/search
- description: Poll for a task
  method: GET
  name: polltask
  path: /tasks/poll/{taskType}
- description: Update task
  method: POST
  name: updatetask
  path: /tasks
- description: Search human tasks
  method: GET
  name: searchhumantasks
  path: /human/tasks/search
- description: Get a human task
  method: GET
  name: gethumantask
  path: /human/tasks/{taskId}
- description: Claim a human task
  method: POST
  name: claimhumantask
  path: /human/tasks/{taskId}/claim/{userId}
- description: Release a human task
  method: POST
  name: releasehumantask
  path: /human/tasks/{taskId}/release
- description: Complete a human task
  method: POST
  name: completehumantask
  path: /human/tasks/{taskId}/complete
- description: Get a secret
  method: GET
  name: getsecret
  path: /secrets/{key}
- description: Create or update a secret
  method: PUT
  name: putsecret
  path: /secrets/{key}
- description: Delete a secret
  method: DELETE
  name: deletesecret
  path: /secrets/{key}
- description: List secret names
  method: GET
  name: listsecrets
  path: /secrets
- description: List schedules
  method: GET
  name: listschedules
  path: /scheduler/schedules
- description: Create a schedule
  method: POST
  name: createschedule
  path: /scheduler/schedules
- description: Get a schedule
  method: GET
  name: getschedule
  path: /scheduler/schedules/{name}
- description: Delete a schedule
  method: DELETE
  name: deleteschedule
  path: /scheduler/schedules/{name}
- description: Pause a schedule
  method: POST
  name: pauseschedule
  path: /scheduler/schedules/{name}/pause
- description: Resume a schedule
  method: POST
  name: resumeschedule
  path: /scheduler/schedules/{name}/resume
- description: Generate access token
  method: POST
  name: generatetoken
  path: /token
personas: []
provider_name: Orkes
provider_slug: orkes
search_terms:
- startworkflow
- listworkflowdefinitions
- start a workflow
- deletesecret
- searchworkflows
- releasehumantask
- create a schedule
- get a human task
- get a secret
- updatetask
- deletetaskdefinition
- getworkflowdefinition
- completehumantask
- get a schedule
- orkes
- search workflows
- updateworkflowdefinitions
- claimhumantask
- resume a schedule
- get task definition
- list task definitions
- pauseworkflow
- getschedule
- getsecret
- createschedule
- deleteschedule
- list workflow definitions
- update task
- get workflow definition
- delete a task definition
- complete a human task
- getworkflowexecution
- listsecrets
- gettaskdefinition
- pause a schedule
- update workflow definitions
- pauseschedule
- search human tasks
- restartworkflow
- pause a workflow
- claim a human task
- registertaskdefinitions
- restart a workflow
- api
- retry a workflow
- gethumantask
- list secret names
- create or update a secret
- putsecret
- searchhumantasks
- delete a workflow definition
- register task definitions
- polltask
- get workflow execution
- register a workflow definition
- resumeworkflow
- delete a secret
- delete a schedule
- poll for a task
- list schedules
- resumeschedule
- terminateworkflow
- terminate a workflow
- registerworkflowdefinition
- generate access token
- listtaskdefinitions
- listschedules
- generatetoken
- microservices
- deleteworkflowdefinition
- retryworkflow
- resume a workflow
- release a human task
slug: orkes-capability
source_filename: orkes-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Orkes Conductor REST API\n  description: The Orkes Conductor REST API provides endpoints for managing workflows, tasks, human tasks, secrets, schedules,\n    and other resources in the Orkes workflow orchestration platform built on Netflix Conductor.\n  tags:\n  - Orkes\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: orkes\n    baseUri: https://play.orkes.io/api\n    description: Orkes Conductor REST API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{ORKES_TOKEN}}'\n    resources:\n    - name: metadata-workflow\n      path: /metadata/workflow\n      operations:\n      - name: listworkflowdefinitions\n        method: GET\n        description: List workflow definitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: registerworkflowdefinition\n        method:\
  \ POST\n        description: Register a workflow definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateworkflowdefinitions\n        method: PUT\n        description: Update workflow definitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metadata-workflow-name\n      path: /metadata/workflow/{name}\n      operations:\n      - name: getworkflowdefinition\n        method: GET\n        description: Get workflow definition\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        - name: version\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteworkflowdefinition\n        method: DELETE\n\
  \        description: Delete a workflow definition\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        - name: version\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metadata-taskdefs\n      path: /metadata/taskdefs\n      operations:\n      - name: listtaskdefinitions\n        method: GET\n        description: List task definitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: registertaskdefinitions\n        method: POST\n        description: Register task definitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metadata-taskdefs-tasktype\n      path: /metadata/taskdefs/{taskType}\n   \
  \   operations:\n      - name: gettaskdefinition\n        method: GET\n        description: Get task definition\n        inputParameters:\n        - name: taskType\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetaskdefinition\n        method: DELETE\n        description: Delete a task definition\n        inputParameters:\n        - name: taskType\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflow\n      path: /workflow\n      operations:\n      - name: startworkflow\n        method: POST\n        description: Start a workflow\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: workflow-workflowid\n      path: /workflow/{workflowId}\n      operations:\n      - name: getworkflowexecution\n        method: GET\n        description: Get workflow execution\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n        - name: includeTasks\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: terminateworkflow\n        method: DELETE\n        description: Terminate a workflow\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n        - name: reason\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflow-workflowid-pause\n      path: /workflow/{workflowId}/pause\n\
  \      operations:\n      - name: pauseworkflow\n        method: PUT\n        description: Pause a workflow\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflow-workflowid-resume\n      path: /workflow/{workflowId}/resume\n      operations:\n      - name: resumeworkflow\n        method: PUT\n        description: Resume a workflow\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflow-workflowid-retry\n      path: /workflow/{workflowId}/retry\n      operations:\n      - name: retryworkflow\n        method: POST\n        description: Retry a workflow\n     \
  \   inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflow-workflowid-restart\n      path: /workflow/{workflowId}/restart\n      operations:\n      - name: restartworkflow\n        method: POST\n        description: Restart a workflow\n        inputParameters:\n        - name: workflowId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflow-search\n      path: /workflow/search\n      operations:\n      - name: searchworkflows\n        method: GET\n        description: Search workflows\n        inputParameters:\n        - name: start\n          in: query\n          type: integer\n        - name: size\n          in: query\n\
  \          type: integer\n        - name: sort\n          in: query\n          type: string\n        - name: freeText\n          in: query\n          type: string\n        - name: query\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tasks-poll-tasktype\n      path: /tasks/poll/{taskType}\n      operations:\n      - name: polltask\n        method: GET\n        description: Poll for a task\n        inputParameters:\n        - name: taskType\n          in: path\n          type: string\n          required: true\n        - name: workerid\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tasks\n      path: /tasks\n      operations:\n      - name: updatetask\n        method: POST\n        description: Update task\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: human-tasks-search\n      path: /human/tasks/search\n      operations:\n      - name: searchhumantasks\n        method: GET\n        description: Search human tasks\n        inputParameters:\n        - name: start\n          in: query\n          type: integer\n        - name: size\n          in: query\n          type: integer\n        - name: query\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: human-tasks-taskid\n      path: /human/tasks/{taskId}\n      operations:\n      - name: gethumantask\n        method: GET\n        description: Get a human task\n        inputParameters:\n        - name: taskId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n    - name: human-tasks-taskid-claim-userid\n      path: /human/tasks/{taskId}/claim/{userId}\n      operations:\n      - name: claimhumantask\n        method: POST\n        description: Claim a human task\n        inputParameters:\n        - name: taskId\n          in: path\n          type: string\n          required: true\n        - name: userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: human-tasks-taskid-release\n      path: /human/tasks/{taskId}/release\n      operations:\n      - name: releasehumantask\n        method: POST\n        description: Release a human task\n        inputParameters:\n        - name: taskId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: human-tasks-taskid-complete\n      path: /human/tasks/{taskId}/complete\n      operations:\n      - name: completehumantask\n        method: POST\n        description: Complete a human task\n        inputParameters:\n        - name: taskId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: secrets-key\n      path: /secrets/{key}\n      operations:\n      - name: getsecret\n        method: GET\n        description: Get a secret\n        inputParameters:\n        - name: key\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: putsecret\n        method: PUT\n        description: Create or update a secret\n   \
  \     inputParameters:\n        - name: key\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesecret\n        method: DELETE\n        description: Delete a secret\n        inputParameters:\n        - name: key\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: secrets\n      path: /secrets\n      operations:\n      - name: listsecrets\n        method: GET\n        description: List secret names\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scheduler-schedules\n      path: /scheduler/schedules\n      operations:\n      - name: listschedules\n        method: GET\n        description:\
  \ List schedules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createschedule\n        method: POST\n        description: Create a schedule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scheduler-schedules-name\n      path: /scheduler/schedules/{name}\n      operations:\n      - name: getschedule\n        method: GET\n        description: Get a schedule\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteschedule\n        method: DELETE\n        description: Delete a schedule\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scheduler-schedules-name-pause\n      path: /scheduler/schedules/{name}/pause\n      operations:\n      - name: pauseschedule\n        method: POST\n        description: Pause a schedule\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scheduler-schedules-name-resume\n      path: /scheduler/schedules/{name}/resume\n      operations:\n      - name: resumeschedule\n        method: POST\n        description: Resume a schedule\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: token\n      path: /token\n      operations:\n      - name: generatetoken\n        method: POST\n        description: Generate access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: orkes-rest\n    description: REST adapter for Orkes Conductor REST API.\n    resources:\n    - path: /metadata/workflow\n      name: listworkflowdefinitions\n      operations:\n      - method: GET\n        name: listworkflowdefinitions\n        description: List workflow definitions\n        call: orkes.listworkflowdefinitions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/workflow\n      name: registerworkflowdefinition\n      operations:\n      - method: POST\n        name: registerworkflowdefinition\n        description: Register a workflow definition\n        call: orkes.registerworkflowdefinition\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/workflow\n      name: updateworkflowdefinitions\n      operations:\n      - method: PUT\n        name: updateworkflowdefinitions\n        description: Update workflow definitions\n        call: orkes.updateworkflowdefinitions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/workflow/{name}\n      name: getworkflowdefinition\n      operations:\n      - method: GET\n        name: getworkflowdefinition\n        description: Get workflow definition\n        call: orkes.getworkflowdefinition\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/workflow/{name}\n      name: deleteworkflowdefinition\n      operations:\n      - method: DELETE\n        name: deleteworkflowdefinition\n        description: Delete a workflow definition\n        call: orkes.deleteworkflowdefinition\n\
  \        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/taskdefs\n      name: listtaskdefinitions\n      operations:\n      - method: GET\n        name: listtaskdefinitions\n        description: List task definitions\n        call: orkes.listtaskdefinitions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/taskdefs\n      name: registertaskdefinitions\n      operations:\n      - method: POST\n        name: registertaskdefinitions\n        description: Register task definitions\n        call: orkes.registertaskdefinitions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/taskdefs/{taskType}\n      name: gettaskdefinition\n      operations:\n      - method: GET\n        name: gettaskdefinition\n        description: Get task definition\n        call: orkes.gettaskdefinition\n        with:\n          taskType: rest.taskType\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metadata/taskdefs/{taskType}\n      name: deletetaskdefinition\n      operations:\n      - method: DELETE\n        name: deletetaskdefinition\n        description: Delete a task definition\n        call: orkes.deletetaskdefinition\n        with:\n          taskType: rest.taskType\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflow\n      name: startworkflow\n      operations:\n      - method: POST\n        name: startworkflow\n        description: Start a workflow\n        call: orkes.startworkflow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflow/{workflowId}\n      name: getworkflowexecution\n      operations:\n      - method: GET\n        name: getworkflowexecution\n        description: Get workflow execution\n        call: orkes.getworkflowexecution\n        with:\n          workflowId: rest.workflowId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflow/{workflowId}\n      name: terminateworkflow\n      operations:\n      - method: DELETE\n        name: terminateworkflow\n        description: Terminate a workflow\n        call: orkes.terminateworkflow\n        with:\n          workflowId: rest.workflowId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflow/{workflowId}/pause\n      name: pauseworkflow\n      operations:\n      - method: PUT\n        name: pauseworkflow\n        description: Pause a workflow\n        call: orkes.pauseworkflow\n        with:\n          workflowId: rest.workflowId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflow/{workflowId}/resume\n      name: resumeworkflow\n      operations:\n      - method: PUT\n        name: resumeworkflow\n        description: Resume a workflow\n        call: orkes.resumeworkflow\n        with:\n\
  \          workflowId: rest.workflowId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflow/{workflowId}/retry\n      name: retryworkflow\n      operations:\n      - method: POST\n        name: retryworkflow\n        description: Retry a workflow\n        call: orkes.retryworkflow\n        with:\n          workflowId: rest.workflowId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflow/{workflowId}/restart\n      name: restartworkflow\n      operations:\n      - method: POST\n        name: restartworkflow\n        description: Restart a workflow\n        call: orkes.restartworkflow\n        with:\n          workflowId: rest.workflowId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflow/search\n      name: searchworkflows\n      operations:\n      - method: GET\n        name: searchworkflows\n        description: Search workflows\n        call: orkes.searchworkflows\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tasks/poll/{taskType}\n      name: polltask\n      operations:\n      - method: GET\n        name: polltask\n        description: Poll for a task\n        call: orkes.polltask\n        with:\n          taskType: rest.taskType\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tasks\n      name: updatetask\n      operations:\n      - method: POST\n        name: updatetask\n        description: Update task\n        call: orkes.updatetask\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /human/tasks/search\n      name: searchhumantasks\n      operations:\n      - method: GET\n        name: searchhumantasks\n        description: Search human tasks\n        call: orkes.searchhumantasks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /human/tasks/{taskId}\n      name: gethumantask\n      operations:\n\
  \      - method: GET\n        name: gethumantask\n        description: Get a human task\n        call: orkes.gethumantask\n        with:\n          taskId: rest.taskId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /human/tasks/{taskId}/claim/{userId}\n      name: claimhumantask\n      operations:\n      - method: POST\n        name: claimhumantask\n        description: Claim a human task\n        call: orkes.claimhumantask\n        with:\n          taskId: rest.taskId\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /human/tasks/{taskId}/release\n      name: releasehumantask\n      operations:\n      - method: POST\n        name: releasehumantask\n        description: Release a human task\n        call: orkes.releasehumantask\n        with:\n          taskId: rest.taskId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /human/tasks/{taskId}/complete\n\
  \      name: completehumantask\n      operations:\n      - method: POST\n        name: completehumantask\n        description: Complete a human task\n        call: orkes.completehumantask\n        with:\n          taskId: rest.taskId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /secrets/{key}\n      name: getsecret\n      operations:\n      - method: GET\n        name: getsecret\n        description: Get a secret\n        call: orkes.getsecret\n        with:\n          key: rest.key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /secrets/{key}\n      name: putsecret\n      operations:\n      - method: PUT\n        name: putsecret\n        description: Create or update a secret\n        call: orkes.putsecret\n        with:\n          key: rest.key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /secrets/{key}\n      name: deletesecret\n      operations:\n      - method:\
  \ DELETE\n        name: deletesecret\n        description: Delete a secret\n        call: orkes.deletesecret\n        with:\n          key: rest.key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /secrets\n      name: listsecrets\n      operations:\n      - method: GET\n        name: listsecrets\n        description: List secret names\n        call: orkes.listsecrets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /scheduler/schedules\n      name: listschedules\n      operations:\n      - method: GET\n        name: listschedules\n        description: List schedules\n        call: orkes.listschedules\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /scheduler/schedules\n      name: createschedule\n      operations:\n      - method: POST\n        name: createschedule\n        description: Create a schedule\n        call: orkes.createschedule\n        outputParameters:\n  \
  \      - type: object\n          mapping: $.\n    - path: /scheduler/schedules/{name}\n      name: getschedule\n      operations:\n      - method: GET\n        name: getschedule\n        description: Get a schedule\n        call: orkes.getschedule\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /scheduler/schedules/{name}\n      name: deleteschedule\n      operations:\n      - method: DELETE\n        name: deleteschedule\n        description: Delete a schedule\n        call: orkes.deleteschedule\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /scheduler/schedules/{name}/pause\n      name: pauseschedule\n      operations:\n      - method: POST\n        name: pauseschedule\n        description: Pause a schedule\n        call: orkes.pauseschedule\n        with:\n          name: rest.name\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /scheduler/schedules/{name}/resume\n      name: resumeschedule\n      operations:\n      - method: POST\n        name: resumeschedule\n        description: Resume a schedule\n        call: orkes.resumeschedule\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /token\n      name: generatetoken\n      operations:\n      - method: POST\n        name: generatetoken\n        description: Generate access token\n        call: orkes.generatetoken\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: orkes-mcp\n    transport: http\n    description: MCP adapter for Orkes Conductor REST API for AI agent use.\n    tools:\n    - name: listworkflowdefinitions\n      description: List workflow definitions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: orkes.listworkflowdefinitions\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: registerworkflowdefinition\n      description: Register a workflow definition\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: orkes.registerworkflowdefinition\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateworkflowdefinitions\n      description: Update workflow definitions\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: orkes.updateworkflowdefinitions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getworkflowdefinition\n      description: Get workflow definition\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: orkes.getworkflowdefinition\n      with:\n        name: tools.name\n        version: tools.version\n      inputParameters:\n      - name: name\n        type:\
  \ string\n        description: name\n        required: true\n      - name: version\n        type: integer\n        description: version\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteworkflowdefinition\n      description: Delete a workflow definition\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: orkes.deleteworkflowdefinition\n      with:\n        name: tools.name\n        version: tools.version\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      - name: version\n        type: integer\n        description: version\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtaskdefinitions\n      description: List task definitions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: orkes.listtaskdefinitions\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: registertaskdefinitions\n      description: Register task definitions\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: orkes.registertaskdefinitions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettaskdefinition\n      description: Get task definition\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: orkes.gettaskdefinition\n      with:\n        taskType: tools.taskType\n      inputParameters:\n      - name: taskType\n        type: string\n        description: taskType\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletetaskdefinition\n      description: Delete a task definition\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: orkes.deletetaskdefinition\n      with:\n        taskType:\
  \ tools.taskType\n      inputParameters:\n      - name: taskType\n        type: string\n        description: taskType\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: startworkflow\n      description: Start a workflow\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: orkes.startworkflow\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getworkflowexecution\n      description: Get workflow execution\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: orkes.getworkflowexecution\n      with:\n        workflowId: tools.workflowId\n        includeTasks: tools.includeTasks\n      inputParameters:\n      - name: workflowId\n        type: string\n        description: workflowId\n        required: true\n      - name: includeTasks\n        type: boolean\n        description: includeTasks\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: terminateworkflow\n      description: Terminate a workflow\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: orkes.terminateworkflow\n      with:\n        workflowId: tools.workflowId\n        reason: tools.reason\n      inputParameters:\n      - name: workflowId\n        type: string\n        description: workflowId\n        required: true\n      - name: reason\n        type: string\n        description: reason\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: pauseworkflow\n      description: Pause a workflow\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: orkes.pauseworkflow\n      with:\n        workflowId: tools.workflowId\n      inputParameters:\n      - name: workflowId\n        type: string\n        description: workflowId\n        required: true\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: resumeworkflow\n      description: Resume a workflow\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: orkes.resumeworkflow\n      with:\n        workflowId: tools.workflowId\n      inputParameters:\n      - name: workflowId\n        type: string\n        description: workflowId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retryworkflow\n      description: Retry a workflow\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: orkes.retryworkflow\n      with:\n        workflowId: tools.workflowId\n      inputParameters:\n      - name: workflowId\n        type: string\n        description: workflowId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: restartworkflow\n      description: Restart a workflow\n      hints:\n      \
  \  readOnly: false\n        destructive: false\n        idempotent: false\n      call: orkes.restartworkflow\n      with:\n        workflowId: tools.workflowId\n      inputParameters:\n      - name: workflowId\n        type: string\n        description: workflowId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchworkflows\n      description: Search workflows\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: orkes.searchworkflows\n      with:\n        start: tools.start\n        size: tools.size\n        sort: tools.sort\n        freeText: tools.freeText\n        query: tools.query\n      inputParameters:\n      - name: start\n        type: integer\n        description: start\n      - name: size\n        type: integer\n        description: size\n      - name: sort\n        type: string\n        description: sort\n      - name: freeText\n        type: string\n        description:\
  \ freeText\n      - name: query\n        type: string\n        description: query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: polltask\n      description: Poll for a task\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: orkes.polltask\n      with:\n        taskType: tools.taskType\n        workerid: tools.workerid\n      inputParameters:\n      - name: taskType\n        type: string\n        description: taskType\n        required: true\n      - name: workerid\n        type: string\n        description: workerid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatetask\n      description: Update task\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: orkes.updatetask\n      output\n\n# --- truncated at 32 KB (38 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/orkes/refs/heads/main/capabilities/orkes-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/orkes/refs/heads/main/capabilities/orkes-capability.yaml
tags:
- Orkes
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
  name: getworkflowexecution
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
- description: Retry a workflow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: retryworkflow
- description: Restart a workflow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: restartworkflow
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
- description: Update task
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatetask
- description: Search human tasks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchhumantasks
- description: Get a human task
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethumantask
- description: Claim a human task
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: claimhumantask
- description: Release a human task
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: releasehumantask
- description: Complete a human task
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: completehumantask
- description: Get a secret
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsecret
- description: Create or update a secret
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putsecret
- description: Delete a secret
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesecret
- description: List secret names
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsecrets
- description: List schedules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listschedules
- description: Create a schedule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createschedule
- description: Get a schedule
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getschedule
- description: Delete a schedule
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteschedule
- description: Pause a schedule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: pauseschedule
- description: Resume a schedule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: resumeschedule
- description: Generate access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generatetoken
---
