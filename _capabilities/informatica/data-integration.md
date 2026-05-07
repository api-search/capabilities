---
categories:
- data-engineering
consumed_apis: []
description: Unified workflow for managing data integration pipelines including connections, mappings, mapping tasks, job execution, scheduling, and activity monitoring. Used by data engineers and ETL developers.
layout: capability
name: Informatica Data Integration
operations:
- description: List all connections.
  method: GET
  name: list-connections
  path: /v1/connections
- description: Create a new connection.
  method: POST
  name: create-connection
  path: /v1/connections
- description: Get connection details.
  method: GET
  name: get-connection
  path: /v1/connections/{id}
- description: Update a connection.
  method: PUT
  name: update-connection
  path: /v1/connections/{id}
- description: Delete a connection.
  method: DELETE
  name: delete-connection
  path: /v1/connections/{id}
- description: List all mappings.
  method: GET
  name: list-mappings
  path: /v1/mappings
- description: List all mapping tasks.
  method: GET
  name: list-mapping-tasks
  path: /v1/mapping-tasks
- description: Create a new mapping task.
  method: POST
  name: create-mapping-task
  path: /v1/mapping-tasks
- description: Start a job.
  method: POST
  name: start-job
  path: /v1/jobs
personas: []
provider_name: Informatica
provider_slug: informatica
search_terms:
- data source connection management.
- delete connection
- mapping task management.
- get schedule details by id.
- create a new mapping task.
- update schedule
- b2b gateway
- list mapping tasks
- delete schedule
- enterprise software
- list connections
- create a new data source connection.
- update a schedule.
- create mapping task
- stop job
- individual connection management.
- get mapping task
- stop a running job.
- retrieve the activity log.
- data quality
- delete a mapping task.
- get mapping task details by id.
- reference data management
- list all data mappings.
- idmc
- list all task schedules.
- create connection
- data profiling
- create a new schedule.
- list all mapping tasks.
- login
- update a mapping task.
- get activity log
- delete a schedule.
- get connection details.
- authenticate and obtain a session id.
- get connection details by id.
- list schedules
- master data management
- pipeline management
- start job
- delete mapping task
- update a connection.
- delete a connection.
- address verification
- informatica
- update an existing connection.
- update connection
- get mapping
- cloud services
- start a job for a task or taskflow.
- list all connections.
- etl
- get connection
- get schedule
- data governance
- iics
- list all mappings.
- list all data source connections.
- data integration
- job execution management.
- start a job.
- get mapping details by id.
- update mapping task
- data mapping management.
- list mappings
- create a new connection.
- create schedule
slug: data-integration
source_filename: data-integration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Informatica Data Integration\n  description: Unified workflow for managing data integration pipelines including connections, mappings, mapping tasks, job\n    execution, scheduling, and activity monitoring. Used by data engineers and ETL developers.\n  tags:\n  - Informatica\n  - Data Integration\n  - ETL\n  - Pipeline Management\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    INFORMATICA_USERNAME: INFORMATICA_USERNAME\n    INFORMATICA_PASSWORD: INFORMATICA_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: informatica-platform\n    baseUri: https://dm-us.informaticacloud.com\n    description: Informatica IICS Platform REST API for data integration management.\n    authentication:\n      type: apikey\n      key: icSessionId\n      value: '{{INFORMATICA_SESSION_ID}}'\n      placement: header\n    resources:\n    - name: authentication\n      path: /ma/api/v2/user\n      description:\
  \ Authentication and session management.\n      operations:\n      - name: login\n        method: POST\n        description: Authenticate and obtain a session ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            '@type': login\n            username: '{{tools.username}}'\n            password: '{{tools.password}}'\n      - name: logout\n        method: POST\n        description: End the current REST API session.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: connections\n      path: /saas/api/v2/connection\n      description: Manage data source connections.\n      operations:\n      - name: list-connections\n        method: GET\n        description: Retrieve all connections in the organization.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: create-connection\n        method: POST\n        description: Create a new connection.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            '@type': connection\n            name: '{{tools.name}}'\n            type: '{{tools.type}}'\n    - name: connection-details\n      path: /saas/api/v2/connection/{connectionId}\n      description: Manage individual connections.\n      operations:\n      - name: get-connection\n        method: GET\n        description: Retrieve a connection by ID.\n        inputParameters:\n        - name: connectionId\n          in: path\n          type: string\n          required: true\n          description: Connection ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: update-connection\n        method: PUT\n        description: Update an existing connection.\n        inputParameters:\n        - name: connectionId\n          in: path\n          type: string\n          required: true\n          description: Connection ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: delete-connection\n        method: DELETE\n        description: Delete a connection.\n        inputParameters:\n        - name: connectionId\n          in: path\n          type: string\n          required: true\n          description: Connection ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mappings\n      path: /saas/api/v2/mapping\n      description: Manage data integration mappings.\n  \
  \    operations:\n      - name: list-mappings\n        method: GET\n        description: Retrieve all mappings in the organization.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mapping-details\n      path: /saas/api/v2/mapping/{mappingId}\n      description: Manage individual mappings.\n      operations:\n      - name: get-mapping\n        method: GET\n        description: Retrieve a mapping by ID.\n        inputParameters:\n        - name: mappingId\n          in: path\n          type: string\n          required: true\n          description: Mapping ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mapping-tasks\n      path: /saas/api/v2/mttask\n      description: Manage mapping tasks.\n      operations:\n      - name: list-mapping-tasks\n        method: GET\n        description: Retrieve all mapping\
  \ tasks.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-mapping-task\n        method: POST\n        description: Create a new mapping task.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            '@type': mtTask\n            name: '{{tools.name}}'\n    - name: mapping-task-details\n      path: /saas/api/v2/mttask/{taskId}\n      description: Manage individual mapping tasks.\n      operations:\n      - name: get-mapping-task\n        method: GET\n        description: Retrieve a mapping task by ID.\n        inputParameters:\n        - name: taskId\n          in: path\n          type: string\n          required: true\n          description: Task ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: update-mapping-task\n        method: PUT\n        description: Update a mapping task.\n        inputParameters:\n        - name: taskId\n          in: path\n          type: string\n          required: true\n          description: Task ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: delete-mapping-task\n        method: DELETE\n        description: Delete a mapping task.\n        inputParameters:\n        - name: taskId\n          in: path\n          type: string\n          required: true\n          description: Task ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs\n      path: /saas/api/v2/job\n      description: Manage job execution.\n      operations:\n      - name:\
  \ start-job\n        method: POST\n        description: Start a job for a task or taskflow.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            '@type': job\n            taskId: '{{tools.taskId}}'\n            taskType: '{{tools.taskType}}'\n      - name: stop-job\n        method: POST\n        description: Stop a running job.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            '@type': job\n            taskId: '{{tools.taskId}}'\n    - name: activity-log\n      path: /saas/api/v2/activity/activityLog\n      description: View activity logs.\n      operations:\n      - name: get-activity-log\n        method: GET\n        description: Retrieve the activity log.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: schedules\n      path: /saas/api/v2/schedule\n      description: Manage task schedules.\n      operations:\n      - name: list-schedules\n        method: GET\n        description: List all schedules.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-schedule\n        method: POST\n        description: Create a new schedule.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            '@type': schedule\n            name: '{{tools.name}}'\n    - name: schedule-details\n      path: /saas/api/v2/schedule/{scheduleId}\n      description: Manage individual schedules.\n      operations:\n      - name: get-schedule\n        method: GET\n        description: Retrieve a schedule by ID.\n\
  \        inputParameters:\n        - name: scheduleId\n          in: path\n          type: string\n          required: true\n          description: Schedule ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-schedule\n        method: PUT\n        description: Update a schedule.\n        inputParameters:\n        - name: scheduleId\n          in: path\n          type: string\n          required: true\n          description: Schedule ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: delete-schedule\n        method: DELETE\n        description: Delete a schedule.\n        inputParameters:\n        - name: scheduleId\n          in: path\n          type: string\n          required: true\n          description:\
  \ Schedule ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: informatica-integration-api\n    description: Unified REST API for Informatica data integration management.\n    resources:\n    - path: /v1/connections\n      name: connections\n      description: Data source connection management.\n      operations:\n      - method: GET\n        name: list-connections\n        description: List all connections.\n        call: informatica-platform.list-connections\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-connection\n        description: Create a new connection.\n        call: informatica-platform.create-connection\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/connections/{id}\n      name: connection-details\n      description: Individual\
  \ connection management.\n      operations:\n      - method: GET\n        name: get-connection\n        description: Get connection details.\n        call: informatica-platform.get-connection\n        with:\n          connectionId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-connection\n        description: Update a connection.\n        call: informatica-platform.update-connection\n        with:\n          connectionId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-connection\n        description: Delete a connection.\n        call: informatica-platform.delete-connection\n        with:\n          connectionId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/mappings\n      name: mappings\n      description: Data mapping management.\n      operations:\n      - method: GET\n  \
  \      name: list-mappings\n        description: List all mappings.\n        call: informatica-platform.list-mappings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/mapping-tasks\n      name: mapping-tasks\n      description: Mapping task management.\n      operations:\n      - method: GET\n        name: list-mapping-tasks\n        description: List all mapping tasks.\n        call: informatica-platform.list-mapping-tasks\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-mapping-task\n        description: Create a new mapping task.\n        call: informatica-platform.create-mapping-task\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobs\n      name: jobs\n      description: Job execution management.\n      operations:\n      - method: POST\n        name: start-job\n        description: Start a job.\n        call: informatica-platform.start-job\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: informatica-integration-mcp\n    transport: http\n    description: MCP server for AI-assisted Informatica data integration management.\n    tools:\n    - name: login\n      description: Authenticate and obtain a session ID.\n      hints:\n        readOnly: false\n      call: informatica-platform.login\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-connections\n      description: List all data source connections.\n      hints:\n        readOnly: true\n      call: informatica-platform.list-connections\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-connection\n      description: Get connection details by ID.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: informatica-platform.get-connection\n      with:\n        connectionId: tools.connectionId\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: create-connection\n      description: Create a new data source connection.\n      hints:\n        readOnly: false\n      call: informatica-platform.create-connection\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-connection\n      description: Update an existing connection.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: informatica-platform.update-connection\n      with:\n        connectionId: tools.connectionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-connection\n      description: Delete a connection.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: informatica-platform.delete-connection\n      with:\n        connectionId: tools.connectionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-mappings\n      description: List\
  \ all data mappings.\n      hints:\n        readOnly: true\n      call: informatica-platform.list-mappings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-mapping\n      description: Get mapping details by ID.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: informatica-platform.get-mapping\n      with:\n        mappingId: tools.mappingId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-mapping-tasks\n      description: List all mapping tasks.\n      hints:\n        readOnly: true\n      call: informatica-platform.list-mapping-tasks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-mapping-task\n      description: Create a new mapping task.\n      hints:\n        readOnly: false\n      call: informatica-platform.create-mapping-task\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-mapping-task\n      description:\
  \ Get mapping task details by ID.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: informatica-platform.get-mapping-task\n      with:\n        taskId: tools.taskId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-mapping-task\n      description: Update a mapping task.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: informatica-platform.update-mapping-task\n      with:\n        taskId: tools.taskId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-mapping-task\n      description: Delete a mapping task.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: informatica-platform.delete-mapping-task\n      with:\n        taskId: tools.taskId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-job\n      description: Start a job for a task or taskflow.\n      hints:\n      \
  \  readOnly: false\n      call: informatica-platform.start-job\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stop-job\n      description: Stop a running job.\n      hints:\n        readOnly: false\n        destructive: true\n      call: informatica-platform.stop-job\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-activity-log\n      description: Retrieve the activity log.\n      hints:\n        readOnly: true\n      call: informatica-platform.get-activity-log\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-schedules\n      description: List all task schedules.\n      hints:\n        readOnly: true\n      call: informatica-platform.list-schedules\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-schedule\n      description: Create a new schedule.\n      hints:\n        readOnly: false\n      call: informatica-platform.create-schedule\n     \
  \ outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-schedule\n      description: Get schedule details by ID.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: informatica-platform.get-schedule\n      with:\n        scheduleId: tools.scheduleId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-schedule\n      description: Update a schedule.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: informatica-platform.update-schedule\n      with:\n        scheduleId: tools.scheduleId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-schedule\n      description: Delete a schedule.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: informatica-platform.delete-schedule\n      with:\n        scheduleId: tools.scheduleId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/informatica/refs/heads/main/capabilities/data-integration.yaml
tags:
- Informatica
- Data Integration
- ETL
- Pipeline Management
tools:
- description: Authenticate and obtain a session ID.
  hints:
    readOnly: false
  name: login
- description: List all data source connections.
  hints:
    readOnly: true
  name: list-connections
- description: Get connection details by ID.
  hints:
    idempotent: true
    readOnly: true
  name: get-connection
- description: Create a new data source connection.
  hints:
    readOnly: false
  name: create-connection
- description: Update an existing connection.
  hints:
    idempotent: true
    readOnly: false
  name: update-connection
- description: Delete a connection.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-connection
- description: List all data mappings.
  hints:
    readOnly: true
  name: list-mappings
- description: Get mapping details by ID.
  hints:
    idempotent: true
    readOnly: true
  name: get-mapping
- description: List all mapping tasks.
  hints:
    readOnly: true
  name: list-mapping-tasks
- description: Create a new mapping task.
  hints:
    readOnly: false
  name: create-mapping-task
- description: Get mapping task details by ID.
  hints:
    idempotent: true
    readOnly: true
  name: get-mapping-task
- description: Update a mapping task.
  hints:
    idempotent: true
    readOnly: false
  name: update-mapping-task
- description: Delete a mapping task.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-mapping-task
- description: Start a job for a task or taskflow.
  hints:
    readOnly: false
  name: start-job
- description: Stop a running job.
  hints:
    destructive: true
    readOnly: false
  name: stop-job
- description: Retrieve the activity log.
  hints:
    readOnly: true
  name: get-activity-log
- description: List all task schedules.
  hints:
    readOnly: true
  name: list-schedules
- description: Create a new schedule.
  hints:
    readOnly: false
  name: create-schedule
- description: Get schedule details by ID.
  hints:
    idempotent: true
    readOnly: true
  name: get-schedule
- description: Update a schedule.
  hints:
    idempotent: true
    readOnly: false
  name: update-schedule
- description: Delete a schedule.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-schedule
---
