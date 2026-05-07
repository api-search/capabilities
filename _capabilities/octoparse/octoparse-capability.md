---
categories: []
consumed_apis: []
description: Octoparse is your no-coding solution for web scraping to turn pages into structured data within clicks.
layout: capability
name: Octoparse
operations:
- description: Octoparse getToken
  method: POST
  name: post-token
  path: token
- description: Octoparse SubtasksStatus
  method: GET
  name: get-cloudextraction-task-subtasks
  path: cloudextraction/task/subtasks
- description: Octoparse TaskStatus
  method: POST
  name: post-cloudextraction-statuses
  path: cloudextraction/statuses
- description: Octoparse TaskStatusV2
  method: POST
  name: post-cloudextraction-statuses-v2
  path: cloudextraction/statuses/v2
- description: Octoparse cloudextractionStart
  method: POST
  name: post-cloudextraction-start
  path: cloudextraction/start
- description: Octoparse cloudextractionStop
  method: POST
  name: post-cloudextraction-stop
  path: cloudextraction/stop
- description: Octoparse cloudextractionSubtasksStart
  method: POST
  name: post-cloudextraction-subtasks-start
  path: cloudextraction/subtasks{start}
- description: Octoparse cloudextractionSubtasksStop
  method: POST
  name: post-cloudextraction-subtasks-stop
  path: cloudextraction/subtasks{stop}
- description: Octoparse all
  method: GET
  name: get-data-all
  path: data/all
- description: Octoparse lotnoAll
  method: GET
  name: get-data-lotno-all
  path: data/lotno/all
- description: Octoparse markexported
  method: POST
  name: post-data-markexported
  path: data/markexported
- description: Octoparse notexported
  method: GET
  name: get-data-notexported
  path: data/notexported
- description: Octoparse remove
  method: POST
  name: post-data-remove
  path: data/remove
- description: Octoparse Copy
  method: POST
  name: post-task-copy
  path: task/copy
- description: Octoparse MoveToGroup
  method: POST
  name: post-task-movetogroup
  path: task/moveToGroup
- description: Octoparse Search
  method: GET
  name: get-task-search
  path: task/search
- description: Octoparse UpdateUrls
  method: POST
  name: post-task-urls-file
  path: task/urls{file}
- description: Octoparse taskGroup
  method: GET
  name: get-taskgroup
  path: taskGroup
- description: Octoparse getActions
  method: POST
  name: post-task-getactions
  path: task/getActions
- description: Octoparse updateActionProperties
  method: POST
  name: post-task-updateactionproperties
  path: task/updateActionProperties
- description: Octoparse updateLoopItems
  method: POST
  name: post-task-updateloopitems
  path: task/updateLoopItems
personas: []
provider_name: Octoparse
provider_slug: octoparse
search_terms:
- harvesting
- octoparse gettoken
- octoparse notexported
- octoparse copy
- octoparse movetogroup
- post task copy
- octoparse lotnoall
- api
- octoparse
- octoparse taskstatus
- post cloudextraction statuses
- post task movetogroup
- octoparse cloudextractionstart
- octoparse cloudextractionsubtasksstart
- post cloudextraction subtasks stop
- octoparse all
- octoparse markexported
- post task getactions
- get data lotno all
- octoparse taskgroup
- octoparse search
- scraping
- octoparse cloudextractionstop
- get cloudextraction task subtasks
- octoparse subtasksstatus
- octoparse updateactionproperties
- post data markexported
- post cloudextraction start
- octoparse updateloopitems
- post data remove
- get data notexported
- post task updateloopitems
- octoparse remove
- octoparse taskstatusv2
- post cloudextraction statuses v2
- post task urls file
- post cloudextraction subtasks start
- octoparse getactions
- post token
- get data all
- post cloudextraction stop
- get task search
- get taskgroup
- octoparse updateurls
- post task updateactionproperties
- octoparse cloudextractionsubtasksstop
slug: octoparse-capability
source_filename: octoparse-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Octoparse\n  description: Octoparse is your no-coding solution for web scraping to turn pages into structured data within clicks.\n  tags:\n  - Octoparse\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: octoparse\n    baseUri: https://openapi.octoparse.com\n    description: Octoparse HTTP API.\n    resources:\n    - name: token\n      path: token\n      operations:\n      - name: post-token\n        method: POST\n        description: Octoparse getToken\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloudextraction-task-subtasks\n      path: cloudextraction/task/subtasks\n      operations:\n      - name: get-cloudextraction-task-subtasks\n        method: GET\n        description: Octoparse SubtasksStatus\n        inputParameters:\n        - name: taskId\n          in: query\n \
  \         type: string\n          required: true\n          description: Task ID\n        - name: page\n          in: query\n          type: string\n          required: true\n          description: Page number\n        - name: size\n          in: query\n          type: string\n          required: true\n          description: Number of subtasks a page (1 to 20)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloudextraction-statuses\n      path: cloudextraction/statuses\n      operations:\n      - name: post-cloudextraction-statuses\n        method: POST\n        description: Octoparse TaskStatus\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloudextraction-statuses-v2\n      path: cloudextraction/statuses/v2\n      operations:\n      - name: post-cloudextraction-statuses-v2\n        method: POST\n     \
  \   description: Octoparse TaskStatusV2\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloudextraction-start\n      path: cloudextraction/start\n      operations:\n      - name: post-cloudextraction-start\n        method: POST\n        description: Octoparse cloudextractionStart\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloudextraction-stop\n      path: cloudextraction/stop\n      operations:\n      - name: post-cloudextraction-stop\n        method: POST\n        description: Octoparse cloudextractionStop\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloudextraction-subtasks-start\n      path: cloudextraction/subtasks{start}\n      operations:\n      - name: post-cloudextraction-subtasks-start\n        method:\
  \ POST\n        description: Octoparse cloudextractionSubtasksStart\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloudextraction-subtasks-stop\n      path: cloudextraction/subtasks{stop}\n      operations:\n      - name: post-cloudextraction-subtasks-stop\n        method: POST\n        description: Octoparse cloudextractionSubtasksStop\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-all\n      path: data/all\n      operations:\n      - name: get-data-all\n        method: GET\n        description: Octoparse all\n        inputParameters:\n        - name: taskId\n          in: query\n          type: string\n          required: true\n          description: Task ID\n        - name: offset\n          in: query\n          type: string\n          required: true\n          description: Data offset. When offset=0,\
  \ you can get data from the first data row.\n        - name: size\n          in: query\n          type: string\n          required: true\n          description: The amount of data rows(range from 1 to 1000).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-lotno-all\n      path: data/lotno/all\n      operations:\n      - name: get-data-lotno-all\n        method: GET\n        description: Octoparse lotnoAll\n        inputParameters:\n        - name: taskId\n          in: query\n          type: string\n          required: true\n          description: Task Id\n        - name: lotno\n          in: query\n          type: string\n          required: true\n          description: Batch ID\n        - name: offset\n          in: query\n          type: string\n          required: true\n          description: Data offset. When offset=0, you can get data from the first data row.\n        - name: size\n \
  \         in: query\n          type: string\n          required: true\n          description: The amount of data rows (range from 1 to 1000).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-markexported\n      path: data/markexported\n      operations:\n      - name: post-data-markexported\n        method: POST\n        description: Octoparse markexported\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-notexported\n      path: data/notexported\n      operations:\n      - name: get-data-notexported\n        method: GET\n        description: Octoparse notexported\n        inputParameters:\n        - name: taskId\n          in: query\n          type: string\n          required: true\n          description: Task ID\n        - name: size\n          in: query\n          type: string\n          required:\
  \ true\n          description: The amount of data rows(range from 1 to 1000)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-remove\n      path: data/remove\n      operations:\n      - name: post-data-remove\n        method: POST\n        description: Octoparse remove\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: task-copy\n      path: task/copy\n      operations:\n      - name: post-task-copy\n        method: POST\n        description: Octoparse Copy\n        inputParameters:\n        - name: taskGroupId\n          in: query\n          type: string\n          required: true\n          description: Task group ID (If not specified, the task will be duplicated to the current task group)\n        - name: taskId\n          in: query\n          type: string\n          required: true\n          description:\
  \ Task ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: task-movetogroup\n      path: task/moveToGroup\n      operations:\n      - name: post-task-movetogroup\n        method: POST\n        description: Octoparse MoveToGroup\n        inputParameters:\n        - name: taskGroupId\n          in: query\n          type: string\n          required: true\n          description: Task group ID\n        - name: taskId\n          in: query\n          type: string\n          required: true\n          description: Task ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: task-search\n      path: task/search\n      operations:\n      - name: get-task-search\n        method: GET\n        description: Octoparse Search\n        inputParameters:\n        - name: taskGroupId\n          in: query\n          type: string\n \
  \         required: true\n          description: Task group ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: task-urls-file\n      path: task/urls{file}\n      operations:\n      - name: post-task-urls-file\n        method: POST\n        description: Octoparse UpdateUrls\n        inputParameters:\n        - name: taskId\n          in: query\n          type: string\n          required: true\n          description: Task ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: taskgroup\n      path: taskGroup\n      operations:\n      - name: get-taskgroup\n        method: GET\n        description: Octoparse taskGroup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: task-getactions\n      path: task/getActions\n      operations:\n\
  \      - name: post-task-getactions\n        method: POST\n        description: Octoparse getActions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: task-updateactionproperties\n      path: task/updateActionProperties\n      operations:\n      - name: post-task-updateactionproperties\n        method: POST\n        description: Octoparse updateActionProperties\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: task-updateloopitems\n      path: task/updateLoopItems\n      operations:\n      - name: post-task-updateloopitems\n        method: POST\n        description: Octoparse updateLoopItems\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: octoparse-rest\n    description: REST\
  \ adapter for Octoparse.\n    resources:\n    - path: token\n      name: post-token\n      operations:\n      - method: POST\n        name: post-token\n        description: Octoparse getToken\n        call: octoparse.post-token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: cloudextraction/task/subtasks\n      name: get-cloudextraction-task-subtasks\n      operations:\n      - method: GET\n        name: get-cloudextraction-task-subtasks\n        description: Octoparse SubtasksStatus\n        call: octoparse.get-cloudextraction-task-subtasks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: cloudextraction/statuses\n      name: post-cloudextraction-statuses\n      operations:\n      - method: POST\n        name: post-cloudextraction-statuses\n        description: Octoparse TaskStatus\n        call: octoparse.post-cloudextraction-statuses\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: cloudextraction/statuses/v2\n      name: post-cloudextraction-statuses-v2\n      operations:\n      - method: POST\n        name: post-cloudextraction-statuses-v2\n        description: Octoparse TaskStatusV2\n        call: octoparse.post-cloudextraction-statuses-v2\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: cloudextraction/start\n      name: post-cloudextraction-start\n      operations:\n      - method: POST\n        name: post-cloudextraction-start\n        description: Octoparse cloudextractionStart\n        call: octoparse.post-cloudextraction-start\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: cloudextraction/stop\n      name: post-cloudextraction-stop\n      operations:\n      - method: POST\n        name: post-cloudextraction-stop\n        description: Octoparse cloudextractionStop\n        call: octoparse.post-cloudextraction-stop\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: cloudextraction/subtasks{start}\n      name: post-cloudextraction-subtasks-start\n      operations:\n      - method: POST\n        name: post-cloudextraction-subtasks-start\n        description: Octoparse cloudextractionSubtasksStart\n        call: octoparse.post-cloudextraction-subtasks-start\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: cloudextraction/subtasks{stop}\n      name: post-cloudextraction-subtasks-stop\n      operations:\n      - method: POST\n        name: post-cloudextraction-subtasks-stop\n        description: Octoparse cloudextractionSubtasksStop\n        call: octoparse.post-cloudextraction-subtasks-stop\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: data/all\n      name: get-data-all\n      operations:\n      - method: GET\n        name: get-data-all\n        description: Octoparse all\n        call: octoparse.get-data-all\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: data/lotno/all\n      name: get-data-lotno-all\n      operations:\n      - method: GET\n        name: get-data-lotno-all\n        description: Octoparse lotnoAll\n        call: octoparse.get-data-lotno-all\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: data/markexported\n      name: post-data-markexported\n      operations:\n      - method: POST\n        name: post-data-markexported\n        description: Octoparse markexported\n        call: octoparse.post-data-markexported\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: data/notexported\n      name: get-data-notexported\n      operations:\n      - method: GET\n        name: get-data-notexported\n        description: Octoparse notexported\n        call: octoparse.get-data-notexported\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: data/remove\n      name: post-data-remove\n\
  \      operations:\n      - method: POST\n        name: post-data-remove\n        description: Octoparse remove\n        call: octoparse.post-data-remove\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: task/copy\n      name: post-task-copy\n      operations:\n      - method: POST\n        name: post-task-copy\n        description: Octoparse Copy\n        call: octoparse.post-task-copy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: task/moveToGroup\n      name: post-task-movetogroup\n      operations:\n      - method: POST\n        name: post-task-movetogroup\n        description: Octoparse MoveToGroup\n        call: octoparse.post-task-movetogroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: task/search\n      name: get-task-search\n      operations:\n      - method: GET\n        name: get-task-search\n        description: Octoparse Search\n        call: octoparse.get-task-search\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: task/urls{file}\n      name: post-task-urls-file\n      operations:\n      - method: POST\n        name: post-task-urls-file\n        description: Octoparse UpdateUrls\n        call: octoparse.post-task-urls-file\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: taskGroup\n      name: get-taskgroup\n      operations:\n      - method: GET\n        name: get-taskgroup\n        description: Octoparse taskGroup\n        call: octoparse.get-taskgroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: task/getActions\n      name: post-task-getactions\n      operations:\n      - method: POST\n        name: post-task-getactions\n        description: Octoparse getActions\n        call: octoparse.post-task-getactions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: task/updateActionProperties\n      name:\
  \ post-task-updateactionproperties\n      operations:\n      - method: POST\n        name: post-task-updateactionproperties\n        description: Octoparse updateActionProperties\n        call: octoparse.post-task-updateactionproperties\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: task/updateLoopItems\n      name: post-task-updateloopitems\n      operations:\n      - method: POST\n        name: post-task-updateloopitems\n        description: Octoparse updateLoopItems\n        call: octoparse.post-task-updateloopitems\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: octoparse-mcp\n    transport: http\n    description: MCP adapter for Octoparse for AI agent use.\n    tools:\n    - name: post-token\n      description: Octoparse getToken\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: octoparse.post-token\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-cloudextraction-task-subtasks\n      description: Octoparse SubtasksStatus\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: octoparse.get-cloudextraction-task-subtasks\n      with:\n        taskId: tools.taskId\n        page: tools.page\n        size: tools.size\n      inputParameters:\n      - name: taskId\n        type: string\n        description: Task ID\n        required: true\n      - name: page\n        type: string\n        description: Page number\n        required: true\n      - name: size\n        type: string\n        description: Number of subtasks a page (1 to 20)\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-cloudextraction-statuses\n      description: Octoparse TaskStatus\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: octoparse.post-cloudextraction-statuses\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-cloudextraction-statuses-v2\n      description: Octoparse TaskStatusV2\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: octoparse.post-cloudextraction-statuses-v2\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-cloudextraction-start\n      description: Octoparse cloudextractionStart\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: octoparse.post-cloudextraction-start\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-cloudextraction-stop\n      description: Octoparse cloudextractionStop\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: octoparse.post-cloudextraction-stop\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-cloudextraction-subtasks-start\n\
  \      description: Octoparse cloudextractionSubtasksStart\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: octoparse.post-cloudextraction-subtasks-start\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-cloudextraction-subtasks-stop\n      description: Octoparse cloudextractionSubtasksStop\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: octoparse.post-cloudextraction-subtasks-stop\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-data-all\n      description: Octoparse all\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: octoparse.get-data-all\n      with:\n        taskId: tools.taskId\n        offset: tools.offset\n        size: tools.size\n      inputParameters:\n      - name: taskId\n        type: string\n        description: Task ID\n       \
  \ required: true\n      - name: offset\n        type: string\n        description: Data offset. When offset=0, you can get data from the first data row.\n        required: true\n      - name: size\n        type: string\n        description: The amount of data rows(range from 1 to 1000).\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-data-lotno-all\n      description: Octoparse lotnoAll\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: octoparse.get-data-lotno-all\n      with:\n        taskId: tools.taskId\n        lotno: tools.lotno\n        offset: tools.offset\n        size: tools.size\n      inputParameters:\n      - name: taskId\n        type: string\n        description: Task Id\n        required: true\n      - name: lotno\n        type: string\n        description: Batch ID\n        required: true\n      - name: offset\n        type: string\n        description: Data\
  \ offset. When offset=0, you can get data from the first data row.\n        required: true\n      - name: size\n        type: string\n        description: The amount of data rows (range from 1 to 1000).\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-data-markexported\n      description: Octoparse markexported\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: octoparse.post-data-markexported\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-data-notexported\n      description: Octoparse notexported\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: octoparse.get-data-notexported\n      with:\n        taskId: tools.taskId\n        size: tools.size\n      inputParameters:\n      - name: taskId\n        type: string\n        description: Task ID\n        required: true\n      - name:\
  \ size\n        type: string\n        description: The amount of data rows(range from 1 to 1000)\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-data-remove\n      description: Octoparse remove\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: octoparse.post-data-remove\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-task-copy\n      description: Octoparse Copy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: octoparse.post-task-copy\n      with:\n        taskGroupId: tools.taskGroupId\n        taskId: tools.taskId\n      inputParameters:\n      - name: taskGroupId\n        type: string\n        description: Task group ID (If not specified, the task will be duplicated to the current task group)\n        required: true\n      - name: taskId\n        type: string\n        description:\
  \ Task ID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-task-movetogroup\n      description: Octoparse MoveToGroup\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: octoparse.post-task-movetogroup\n      with:\n        taskGroupId: tools.taskGroupId\n        taskId: tools.taskId\n      inputParameters:\n      - name: taskGroupId\n        type: string\n        description: Task group ID\n        required: true\n      - name: taskId\n        type: string\n        description: Task ID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-task-search\n      description: Octoparse Search\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: octoparse.get-task-search\n      with:\n        taskGroupId: tools.taskGroupId\n      inputParameters:\n      - name: taskGroupId\n\
  \        type: string\n        description: Task group ID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-task-urls-file\n      description: Octoparse UpdateUrls\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: octoparse.post-task-urls-file\n      with:\n        taskId: tools.taskId\n      inputParameters:\n      - name: taskId\n        type: string\n        description: Task ID\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-taskgroup\n      description: Octoparse taskGroup\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: octoparse.get-taskgroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-task-getactions\n      description: Octoparse getActions\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: false\n      call: octoparse.post-task-getactions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-task-updateactionproperties\n      description: Octoparse updateActionProperties\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: octoparse.post-task-updateactionproperties\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-task-updateloopitems\n      description: Octoparse updateLoopItems\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: octoparse.post-task-updateloopitems\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/octoparse/refs/heads/main/capabilities/octoparse-capability.yaml
tags:
- Octoparse
- API
tools:
- description: Octoparse getToken
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-token
- description: Octoparse SubtasksStatus
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloudextraction-task-subtasks
- description: Octoparse TaskStatus
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-cloudextraction-statuses
- description: Octoparse TaskStatusV2
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-cloudextraction-statuses-v2
- description: Octoparse cloudextractionStart
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-cloudextraction-start
- description: Octoparse cloudextractionStop
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-cloudextraction-stop
- description: Octoparse cloudextractionSubtasksStart
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-cloudextraction-subtasks-start
- description: Octoparse cloudextractionSubtasksStop
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-cloudextraction-subtasks-stop
- description: Octoparse all
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-data-all
- description: Octoparse lotnoAll
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-data-lotno-all
- description: Octoparse markexported
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-data-markexported
- description: Octoparse notexported
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-data-notexported
- description: Octoparse remove
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-data-remove
- description: Octoparse Copy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-task-copy
- description: Octoparse MoveToGroup
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-task-movetogroup
- description: Octoparse Search
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-task-search
- description: Octoparse UpdateUrls
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-task-urls-file
- description: Octoparse taskGroup
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-taskgroup
- description: Octoparse getActions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-task-getactions
- description: Octoparse updateActionProperties
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-task-updateactionproperties
- description: Octoparse updateLoopItems
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-task-updateloopitems
---
