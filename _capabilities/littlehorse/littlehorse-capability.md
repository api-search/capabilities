---
categories: []
consumed_apis: []
description: The LittleHorse REST API provides HTTP endpoints for managing workflow specifications (WfSpec), workflow runs (WfRun), task definitions (TaskDef), external event definitions, user tasks, and other resources in the LittleHorse workflow engine.
layout: capability
name: LittleHorse REST API
operations:
- description: List workflow specifications
  method: GET
  name: listwfspecs
  path: /wfSpec
- description: Create or update a workflow specification
  method: POST
  name: putwfspec
  path: /wfSpec
- description: Get a workflow specification
  method: GET
  name: getwfspec
  path: /wfSpec/{name}
- description: Delete a workflow specification
  method: DELETE
  name: deletewfspec
  path: /wfSpec/{name}
- description: Run a workflow
  method: POST
  name: runwf
  path: /wfRun
- description: Get a workflow run
  method: GET
  name: getwfrun
  path: /wfRun/{wfRunId}
- description: Delete a workflow run
  method: DELETE
  name: deletewfrun
  path: /wfRun/{wfRunId}
- description: Stop a workflow run
  method: POST
  name: stopwfrun
  path: /wfRun/{wfRunId}/stop
- description: Resume a workflow run
  method: POST
  name: resumewfrun
  path: /wfRun/{wfRunId}/resume
- description: Search workflow runs
  method: GET
  name: searchwfruns
  path: /wfRun/search
- description: List task definitions
  method: GET
  name: listtaskdefs
  path: /taskDef
- description: Create or update a task definition
  method: POST
  name: puttaskdef
  path: /taskDef
- description: Get a task definition
  method: GET
  name: gettaskdef
  path: /taskDef/{name}
- description: Delete a task definition
  method: DELETE
  name: deletetaskdef
  path: /taskDef/{name}
- description: List external event definitions
  method: GET
  name: listexternaleventdefs
  path: /externalEventDef
- description: Create an external event definition
  method: POST
  name: putexternaleventdef
  path: /externalEventDef
- description: Get an external event definition
  method: GET
  name: getexternaleventdef
  path: /externalEventDef/{name}
- description: Post an external event
  method: POST
  name: postexternalevent
  path: /wfRun/{wfRunId}/externalEvent/{externalEventDefName}
- description: Get a user task run
  method: GET
  name: getusertaskrun
  path: /wfRun/{wfRunId}/userTaskRun/{userTaskRunId}
- description: Assign a user task
  method: POST
  name: assignusertask
  path: /wfRun/{wfRunId}/userTaskRun/{userTaskRunId}/assign
- description: Complete a user task
  method: POST
  name: completeusertask
  path: /wfRun/{wfRunId}/userTaskRun/{userTaskRunId}/complete
- description: Get a node run
  method: GET
  name: getnoderun
  path: /nodeRun/{wfRunId}/{threadRunNumber}/{position}
personas: []
provider_name: LittleHorse
provider_slug: littlehorse
search_terms:
- assignusertask
- getexternaleventdef
- get an external event definition
- postexternalevent
- completeusertask
- resumewfrun
- putwfspec
- create an external event definition
- searchwfruns
- getwfspec
- listtaskdefs
- get a user task run
- create or update a workflow specification
- deletetaskdef
- puttaskdef
- getnoderun
- get a workflow specification
- delete a workflow specification
- list task definitions
- resume a workflow run
- runwf
- post an external event
- delete a task definition
- listwfspecs
- littlehorse
- list workflow specifications
- getwfrun
- delete a workflow run
- stop a workflow run
- stopwfrun
- putexternaleventdef
- create or update a task definition
- api
- get a node run
- complete a user task
- get a workflow run
- listexternaleventdefs
- deletewfspec
- get a task definition
- list external event definitions
- search workflow runs
- gettaskdef
- deletewfrun
- microservices
- run a workflow
- getusertaskrun
- assign a user task
slug: littlehorse-capability
source_filename: littlehorse-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: LittleHorse REST API\n  description: The LittleHorse REST API provides HTTP endpoints for managing workflow specifications (WfSpec), workflow runs\n    (WfRun), task definitions (TaskDef), external event definitions, user tasks, and other resources in the LittleHorse workflow\n    engine.\n  tags:\n  - Littlehorse\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: littlehorse\n    baseUri: http://localhost:2023\n    description: LittleHorse REST API HTTP API.\n    resources:\n    - name: wfspec\n      path: /wfSpec\n      operations:\n      - name: listwfspecs\n        method: GET\n        description: List workflow specifications\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: putwfspec\n        method: POST\n        description: Create or update a workflow specification\n   \
  \     outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wfspec-name\n      path: /wfSpec/{name}\n      operations:\n      - name: getwfspec\n        method: GET\n        description: Get a workflow specification\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        - name: majorVersion\n          in: query\n          type: integer\n        - name: revision\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletewfspec\n        method: DELETE\n        description: Delete a workflow specification\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        - name: majorVersion\n          in: query\n          type: integer\n          required:\
  \ true\n        - name: revision\n          in: query\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wfrun\n      path: /wfRun\n      operations:\n      - name: runwf\n        method: POST\n        description: Run a workflow\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wfrun-wfrunid\n      path: /wfRun/{wfRunId}\n      operations:\n      - name: getwfrun\n        method: GET\n        description: Get a workflow run\n        inputParameters:\n        - name: wfRunId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletewfrun\n        method: DELETE\n        description: Delete a workflow run\n\
  \        inputParameters:\n        - name: wfRunId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wfrun-wfrunid-stop\n      path: /wfRun/{wfRunId}/stop\n      operations:\n      - name: stopwfrun\n        method: POST\n        description: Stop a workflow run\n        inputParameters:\n        - name: wfRunId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wfrun-wfrunid-resume\n      path: /wfRun/{wfRunId}/resume\n      operations:\n      - name: resumewfrun\n        method: POST\n        description: Resume a workflow run\n        inputParameters:\n        - name: wfRunId\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wfrun-search\n      path: /wfRun/search\n      operations:\n      - name: searchwfruns\n        method: GET\n        description: Search workflow runs\n        inputParameters:\n        - name: wfSpecName\n          in: query\n          type: string\n        - name: status\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n        - name: bookmark\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: taskdef\n      path: /taskDef\n      operations:\n      - name: listtaskdefs\n        method: GET\n        description: List task definitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: puttaskdef\n\
  \        method: POST\n        description: Create or update a task definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: taskdef-name\n      path: /taskDef/{name}\n      operations:\n      - name: gettaskdef\n        method: GET\n        description: Get a task definition\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetaskdef\n        method: DELETE\n        description: Delete a task definition\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: externaleventdef\n      path:\
  \ /externalEventDef\n      operations:\n      - name: listexternaleventdefs\n        method: GET\n        description: List external event definitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: putexternaleventdef\n        method: POST\n        description: Create an external event definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: externaleventdef-name\n      path: /externalEventDef/{name}\n      operations:\n      - name: getexternaleventdef\n        method: GET\n        description: Get an external event definition\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wfrun-wfrunid-externalevent-externaleventdefname\n\
  \      path: /wfRun/{wfRunId}/externalEvent/{externalEventDefName}\n      operations:\n      - name: postexternalevent\n        method: POST\n        description: Post an external event\n        inputParameters:\n        - name: wfRunId\n          in: path\n          type: string\n          required: true\n        - name: externalEventDefName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wfrun-wfrunid-usertaskrun-usertaskrunid\n      path: /wfRun/{wfRunId}/userTaskRun/{userTaskRunId}\n      operations:\n      - name: getusertaskrun\n        method: GET\n        description: Get a user task run\n        inputParameters:\n        - name: wfRunId\n          in: path\n          type: string\n          required: true\n        - name: userTaskRunId\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wfrun-wfrunid-usertaskrun-usertaskrunid-assign\n      path: /wfRun/{wfRunId}/userTaskRun/{userTaskRunId}/assign\n      operations:\n      - name: assignusertask\n        method: POST\n        description: Assign a user task\n        inputParameters:\n        - name: wfRunId\n          in: path\n          type: string\n          required: true\n        - name: userTaskRunId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wfrun-wfrunid-usertaskrun-usertaskrunid-complete\n      path: /wfRun/{wfRunId}/userTaskRun/{userTaskRunId}/complete\n      operations:\n      - name: completeusertask\n        method: POST\n        description: Complete a user task\n        inputParameters:\n        - name: wfRunId\n          in:\
  \ path\n          type: string\n          required: true\n        - name: userTaskRunId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: noderun-wfrunid-threadrunnumber-position\n      path: /nodeRun/{wfRunId}/{threadRunNumber}/{position}\n      operations:\n      - name: getnoderun\n        method: GET\n        description: Get a node run\n        inputParameters:\n        - name: wfRunId\n          in: path\n          type: string\n          required: true\n        - name: threadRunNumber\n          in: path\n          type: integer\n          required: true\n        - name: position\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n  \
  \  namespace: littlehorse-rest\n    description: REST adapter for LittleHorse REST API.\n    resources:\n    - path: /wfSpec\n      name: listwfspecs\n      operations:\n      - method: GET\n        name: listwfspecs\n        description: List workflow specifications\n        call: littlehorse.listwfspecs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wfSpec\n      name: putwfspec\n      operations:\n      - method: POST\n        name: putwfspec\n        description: Create or update a workflow specification\n        call: littlehorse.putwfspec\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wfSpec/{name}\n      name: getwfspec\n      operations:\n      - method: GET\n        name: getwfspec\n        description: Get a workflow specification\n        call: littlehorse.getwfspec\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wfSpec/{name}\n\
  \      name: deletewfspec\n      operations:\n      - method: DELETE\n        name: deletewfspec\n        description: Delete a workflow specification\n        call: littlehorse.deletewfspec\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wfRun\n      name: runwf\n      operations:\n      - method: POST\n        name: runwf\n        description: Run a workflow\n        call: littlehorse.runwf\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wfRun/{wfRunId}\n      name: getwfrun\n      operations:\n      - method: GET\n        name: getwfrun\n        description: Get a workflow run\n        call: littlehorse.getwfrun\n        with:\n          wfRunId: rest.wfRunId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wfRun/{wfRunId}\n      name: deletewfrun\n      operations:\n      - method: DELETE\n        name: deletewfrun\n      \
  \  description: Delete a workflow run\n        call: littlehorse.deletewfrun\n        with:\n          wfRunId: rest.wfRunId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wfRun/{wfRunId}/stop\n      name: stopwfrun\n      operations:\n      - method: POST\n        name: stopwfrun\n        description: Stop a workflow run\n        call: littlehorse.stopwfrun\n        with:\n          wfRunId: rest.wfRunId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wfRun/{wfRunId}/resume\n      name: resumewfrun\n      operations:\n      - method: POST\n        name: resumewfrun\n        description: Resume a workflow run\n        call: littlehorse.resumewfrun\n        with:\n          wfRunId: rest.wfRunId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wfRun/search\n      name: searchwfruns\n      operations:\n      - method: GET\n        name: searchwfruns\n        description:\
  \ Search workflow runs\n        call: littlehorse.searchwfruns\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /taskDef\n      name: listtaskdefs\n      operations:\n      - method: GET\n        name: listtaskdefs\n        description: List task definitions\n        call: littlehorse.listtaskdefs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /taskDef\n      name: puttaskdef\n      operations:\n      - method: POST\n        name: puttaskdef\n        description: Create or update a task definition\n        call: littlehorse.puttaskdef\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /taskDef/{name}\n      name: gettaskdef\n      operations:\n      - method: GET\n        name: gettaskdef\n        description: Get a task definition\n        call: littlehorse.gettaskdef\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /taskDef/{name}\n      name: deletetaskdef\n      operations:\n      - method: DELETE\n        name: deletetaskdef\n        description: Delete a task definition\n        call: littlehorse.deletetaskdef\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /externalEventDef\n      name: listexternaleventdefs\n      operations:\n      - method: GET\n        name: listexternaleventdefs\n        description: List external event definitions\n        call: littlehorse.listexternaleventdefs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /externalEventDef\n      name: putexternaleventdef\n      operations:\n      - method: POST\n        name: putexternaleventdef\n        description: Create an external event definition\n        call: littlehorse.putexternaleventdef\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /externalEventDef/{name}\n\
  \      name: getexternaleventdef\n      operations:\n      - method: GET\n        name: getexternaleventdef\n        description: Get an external event definition\n        call: littlehorse.getexternaleventdef\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wfRun/{wfRunId}/externalEvent/{externalEventDefName}\n      name: postexternalevent\n      operations:\n      - method: POST\n        name: postexternalevent\n        description: Post an external event\n        call: littlehorse.postexternalevent\n        with:\n          wfRunId: rest.wfRunId\n          externalEventDefName: rest.externalEventDefName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wfRun/{wfRunId}/userTaskRun/{userTaskRunId}\n      name: getusertaskrun\n      operations:\n      - method: GET\n        name: getusertaskrun\n        description: Get a user task run\n        call: littlehorse.getusertaskrun\n\
  \        with:\n          wfRunId: rest.wfRunId\n          userTaskRunId: rest.userTaskRunId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wfRun/{wfRunId}/userTaskRun/{userTaskRunId}/assign\n      name: assignusertask\n      operations:\n      - method: POST\n        name: assignusertask\n        description: Assign a user task\n        call: littlehorse.assignusertask\n        with:\n          wfRunId: rest.wfRunId\n          userTaskRunId: rest.userTaskRunId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wfRun/{wfRunId}/userTaskRun/{userTaskRunId}/complete\n      name: completeusertask\n      operations:\n      - method: POST\n        name: completeusertask\n        description: Complete a user task\n        call: littlehorse.completeusertask\n        with:\n          wfRunId: rest.wfRunId\n          userTaskRunId: rest.userTaskRunId\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /nodeRun/{wfRunId}/{threadRunNumber}/{position}\n      name: getnoderun\n      operations:\n      - method: GET\n        name: getnoderun\n        description: Get a node run\n        call: littlehorse.getnoderun\n        with:\n          wfRunId: rest.wfRunId\n          threadRunNumber: rest.threadRunNumber\n          position: rest.position\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: littlehorse-mcp\n    transport: http\n    description: MCP adapter for LittleHorse REST API for AI agent use.\n    tools:\n    - name: listwfspecs\n      description: List workflow specifications\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: littlehorse.listwfspecs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: putwfspec\n      description: Create or update a workflow specification\n      hints:\n        readOnly: false\n\
  \        destructive: false\n        idempotent: false\n      call: littlehorse.putwfspec\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getwfspec\n      description: Get a workflow specification\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: littlehorse.getwfspec\n      with:\n        name: tools.name\n        majorVersion: tools.majorVersion\n        revision: tools.revision\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      - name: majorVersion\n        type: integer\n        description: majorVersion\n      - name: revision\n        type: integer\n        description: revision\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletewfspec\n      description: Delete a workflow specification\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call:\
  \ littlehorse.deletewfspec\n      with:\n        name: tools.name\n        majorVersion: tools.majorVersion\n        revision: tools.revision\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      - name: majorVersion\n        type: integer\n        description: majorVersion\n        required: true\n      - name: revision\n        type: integer\n        description: revision\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: runwf\n      description: Run a workflow\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: littlehorse.runwf\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getwfrun\n      description: Get a workflow run\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: littlehorse.getwfrun\n      with:\n        wfRunId:\
  \ tools.wfRunId\n      inputParameters:\n      - name: wfRunId\n        type: string\n        description: wfRunId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletewfrun\n      description: Delete a workflow run\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: littlehorse.deletewfrun\n      with:\n        wfRunId: tools.wfRunId\n      inputParameters:\n      - name: wfRunId\n        type: string\n        description: wfRunId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stopwfrun\n      description: Stop a workflow run\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: littlehorse.stopwfrun\n      with:\n        wfRunId: tools.wfRunId\n      inputParameters:\n      - name: wfRunId\n        type: string\n        description: wfRunId\n        required: true\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: resumewfrun\n      description: Resume a workflow run\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: littlehorse.resumewfrun\n      with:\n        wfRunId: tools.wfRunId\n      inputParameters:\n      - name: wfRunId\n        type: string\n        description: wfRunId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchwfruns\n      description: Search workflow runs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: littlehorse.searchwfruns\n      with:\n        wfSpecName: tools.wfSpecName\n        status: tools.status\n        limit: tools.limit\n        bookmark: tools.bookmark\n      inputParameters:\n      - name: wfSpecName\n        type: string\n        description: wfSpecName\n      - name: status\n        type: string\n       \
  \ description: status\n      - name: limit\n        type: integer\n        description: limit\n      - name: bookmark\n        type: string\n        description: bookmark\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtaskdefs\n      description: List task definitions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: littlehorse.listtaskdefs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: puttaskdef\n      description: Create or update a task definition\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: littlehorse.puttaskdef\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettaskdef\n      description: Get a task definition\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: littlehorse.gettaskdef\n      with:\n        name:\
  \ tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletetaskdef\n      description: Delete a task definition\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: littlehorse.deletetaskdef\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listexternaleventdefs\n      description: List external event definitions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: littlehorse.listexternaleventdefs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: putexternaleventdef\n      description: Create an external event definition\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: littlehorse.putexternaleventdef\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getexternaleventdef\n      description: Get an external event definition\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: littlehorse.getexternaleventdef\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: postexternalevent\n      description: Post an external event\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: littlehorse.postexternalevent\n      with:\n        wfRunId: tools.wfRunId\n        externalEventDefName: tools.externalEventDefName\n      inputParameters:\n      -\
  \ name: wfRunId\n        type: string\n        description: wfRunId\n        required: true\n      - name: externalEventDefName\n        type: string\n        description: externalEventDefName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getusertaskrun\n      description: Get a user task run\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: littlehorse.getusertaskrun\n      with:\n        wfRunId: tools.wfRunId\n        userTaskRunId: tools.userTaskRunId\n      inputParameters:\n      - name: wfRunId\n        type: string\n        description: wfRunId\n        required: true\n      - name: userTaskRunId\n        type: string\n        description: userTaskRunId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: assignusertask\n      description: Assign a user task\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: littlehorse.assignusertask\n      with:\n        wfRunId: tools.wfRunId\n        userTaskRunId: tools.userTaskRunId\n      inputParameters:\n      - name: wfRunId\n        type: string\n        description: wfRunId\n        required: true\n      - name: userTaskRunId\n        type: string\n        description: userTaskRunId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: completeusertask\n      description: Complete a user task\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: littlehorse.completeusertask\n      with:\n        wfRunId: tools.wfRunId\n        userTaskRunId: tools.userTaskRunId\n      inputParameters:\n      - name: wfRunId\n        type: string\n        description: wfRunId\n        required: true\n      - name: userTaskRunId\n        type: string\n        description: userTaskRunId\n        required: true\n  \
  \    outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnoderun\n      description: Get a node run\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: littlehorse.getnoderun\n      with:\n        wfRunId: tools.wfRunId\n        threadRunNumber: tools.threadRunNumber\n        position: tools.position\n      inputParameters:\n      - name: wfRunId\n        type: string\n        description: wfRunId\n        required: true\n      - name: threadRunNumber\n        type: integer\n        description: threadRunNumber\n        required: true\n      - name: position\n        type: integer\n        description: position\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/littlehorse/refs/heads/main/capabilities/littlehorse-capability.yaml
tags:
- Littlehorse
- API
tools:
- description: List workflow specifications
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listwfspecs
- description: Create or update a workflow specification
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: putwfspec
- description: Get a workflow specification
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getwfspec
- description: Delete a workflow specification
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletewfspec
- description: Run a workflow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: runwf
- description: Get a workflow run
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getwfrun
- description: Delete a workflow run
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletewfrun
- description: Stop a workflow run
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: stopwfrun
- description: Resume a workflow run
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: resumewfrun
- description: Search workflow runs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchwfruns
- description: List task definitions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtaskdefs
- description: Create or update a task definition
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: puttaskdef
- description: Get a task definition
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettaskdef
- description: Delete a task definition
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetaskdef
- description: List external event definitions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listexternaleventdefs
- description: Create an external event definition
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: putexternaleventdef
- description: Get an external event definition
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getexternaleventdef
- description: Post an external event
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: postexternalevent
- description: Get a user task run
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getusertaskrun
- description: Assign a user task
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: assignusertask
- description: Complete a user task
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: completeusertask
- description: Get a node run
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnoderun
---
