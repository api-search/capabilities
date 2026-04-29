---
categories:
- data-engineering
consumed_apis:
- informatica-platform
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
- update a schedule.
- stop a running job.
- list all mapping tasks.
- address verification
- list connections
- start a job for a task or taskflow.
- job execution management.
- login
- create a new data source connection.
- list schedules
- create a new mapping task.
- update an existing connection.
- list all task schedules.
- update mapping task
- authenticate and obtain a session id.
- enterprise software
- get mapping details by id.
- start a job.
- get mapping task
- stop job
- mapping task management.
- pipeline management
- update a mapping task.
- b2b gateway
- create a new connection.
- list all data source connections.
- delete a mapping task.
- data profiling
- data quality
- get mapping task details by id.
- get schedule
- reference data management
- cloud services
- get connection details by id.
- get connection
- create connection
- iics
- update connection
- retrieve the activity log.
- list all mappings.
- create schedule
- master data management
- update schedule
- delete a connection.
- informatica
- list all data mappings.
- get activity log
- start job
- data integration
- list mappings
- delete a schedule.
- list all connections.
- update a connection.
- create mapping task
- etl
- delete schedule
- individual connection management.
- data source connection management.
- data mapping management.
- list mapping tasks
- idmc
- get mapping
- delete connection
- create a new schedule.
- get connection details.
- get schedule details by id.
- delete mapping task
- data governance
slug: data-integration
source_filename: data-integration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Informatica Data Integration\"\n  description: \"Unified workflow for managing data integration pipelines including connections, mappings, mapping tasks, job execution, scheduling, and activity monitoring. Used by data engineers and ETL developers.\"\n  tags:\n    - Informatica\n    - Data Integration\n    - ETL\n    - Pipeline Management\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      INFORMATICA_USERNAME: INFORMATICA_USERNAME\n      INFORMATICA_PASSWORD: INFORMATICA_PASSWORD\n\ncapability:\n  consumes:\n    - import: informatica-platform\n      location: ./shared/platform-rest-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: informatica-integration-api\n      description: \"Unified REST API for Informatica data integration management.\"\n      resources:\n        - path: /v1/connections\n          name: connections\n          description: \"Data\
  \ source connection management.\"\n          operations:\n            - method: GET\n              name: list-connections\n              description: \"List all connections.\"\n              call: \"informatica-platform.list-connections\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-connection\n              description: \"Create a new connection.\"\n              call: \"informatica-platform.create-connection\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/connections/{id}\n          name: connection-details\n          description: \"Individual connection management.\"\n          operations:\n            - method: GET\n              name: get-connection\n              description: \"Get connection details.\"\n              call: \"informatica-platform.get-connection\"\n              with:\n           \
  \     connectionId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-connection\n              description: \"Update a connection.\"\n              call: \"informatica-platform.update-connection\"\n              with:\n                connectionId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-connection\n              description: \"Delete a connection.\"\n              call: \"informatica-platform.delete-connection\"\n              with:\n                connectionId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/mappings\n          name: mappings\n          description: \"Data mapping management.\"\n          operations:\n            - method: GET\n          \
  \    name: list-mappings\n              description: \"List all mappings.\"\n              call: \"informatica-platform.list-mappings\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/mapping-tasks\n          name: mapping-tasks\n          description: \"Mapping task management.\"\n          operations:\n            - method: GET\n              name: list-mapping-tasks\n              description: \"List all mapping tasks.\"\n              call: \"informatica-platform.list-mapping-tasks\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-mapping-task\n              description: \"Create a new mapping task.\"\n              call: \"informatica-platform.create-mapping-task\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/jobs\n          name:\
  \ jobs\n          description: \"Job execution management.\"\n          operations:\n            - method: POST\n              name: start-job\n              description: \"Start a job.\"\n              call: \"informatica-platform.start-job\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: informatica-integration-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Informatica data integration management.\"\n      tools:\n        - name: login\n          description: \"Authenticate and obtain a session ID.\"\n          hints:\n            readOnly: false\n          call: \"informatica-platform.login\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-connections\n          description: \"List all data source connections.\"\n          hints:\n            readOnly: true\n          call: \"informatica-platform.list-connections\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-connection\n          description: \"Get connection details by ID.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"informatica-platform.get-connection\"\n          with:\n            connectionId: \"tools.connectionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-connection\n          description: \"Create a new data source connection.\"\n          hints:\n            readOnly: false\n          call: \"informatica-platform.create-connection\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-connection\n          description: \"Update an existing connection.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"informatica-platform.update-connection\"\n     \
  \     with:\n            connectionId: \"tools.connectionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-connection\n          description: \"Delete a connection.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"informatica-platform.delete-connection\"\n          with:\n            connectionId: \"tools.connectionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-mappings\n          description: \"List all data mappings.\"\n          hints:\n            readOnly: true\n          call: \"informatica-platform.list-mappings\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-mapping\n          description: \"Get mapping details by ID.\"\n          hints:\n            readOnly: true\n            idempotent: true\n        \
  \  call: \"informatica-platform.get-mapping\"\n          with:\n            mappingId: \"tools.mappingId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-mapping-tasks\n          description: \"List all mapping tasks.\"\n          hints:\n            readOnly: true\n          call: \"informatica-platform.list-mapping-tasks\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-mapping-task\n          description: \"Create a new mapping task.\"\n          hints:\n            readOnly: false\n          call: \"informatica-platform.create-mapping-task\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-mapping-task\n          description: \"Get mapping task details by ID.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"informatica-platform.get-mapping-task\"\n  \
  \        with:\n            taskId: \"tools.taskId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-mapping-task\n          description: \"Update a mapping task.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"informatica-platform.update-mapping-task\"\n          with:\n            taskId: \"tools.taskId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-mapping-task\n          description: \"Delete a mapping task.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"informatica-platform.delete-mapping-task\"\n          with:\n            taskId: \"tools.taskId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: start-job\n          description: \"Start a job for a task or taskflow.\"\
  \n          hints:\n            readOnly: false\n          call: \"informatica-platform.start-job\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: stop-job\n          description: \"Stop a running job.\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"informatica-platform.stop-job\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-activity-log\n          description: \"Retrieve the activity log.\"\n          hints:\n            readOnly: true\n          call: \"informatica-platform.get-activity-log\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-schedules\n          description: \"List all task schedules.\"\n          hints:\n            readOnly: true\n          call: \"informatica-platform.list-schedules\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: create-schedule\n          description: \"Create a new schedule.\"\n          hints:\n            readOnly: false\n          call: \"informatica-platform.create-schedule\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-schedule\n          description: \"Get schedule details by ID.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"informatica-platform.get-schedule\"\n          with:\n            scheduleId: \"tools.scheduleId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-schedule\n          description: \"Update a schedule.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"informatica-platform.update-schedule\"\n          with:\n            scheduleId: \"tools.scheduleId\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: delete-schedule\n          description: \"Delete a schedule.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"informatica-platform.delete-schedule\"\n          with:\n            scheduleId: \"tools.scheduleId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
