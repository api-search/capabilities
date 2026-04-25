---
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
- idmc
- individual connection management.
- get activity log
- list all data source connections.
- list all data mappings.
- get mapping details by id.
- create a new schedule.
- informatica
- start a job.
- list all mapping tasks.
- create mapping task
- data governance
- login
- get mapping task details by id.
- reference data management
- list all task schedules.
- delete a mapping task.
- list schedules
- delete a schedule.
- list all connections.
- mapping task management.
- list mapping tasks
- data quality
- create a new mapping task.
- enterprise software
- update a mapping task.
- get schedule
- master data management
- update connection
- update an existing connection.
- update mapping task
- job execution management.
- get connection details.
- delete connection
- pipeline management
- create schedule
- data profiling
- b2b gateway
- address verification
- get mapping
- list connections
- data mapping management.
- update a connection.
- delete a connection.
- data integration
- list mappings
- list all mappings.
- get connection
- start job
- get mapping task
- get schedule details by id.
- update schedule
- authenticate and obtain a session id.
- etl
- retrieve the activity log.
- create a new data source connection.
- update a schedule.
- delete schedule
- stop job
- data source connection management.
- create a new connection.
- cloud services
- iics
- delete mapping task
- get connection details by id.
- create connection
- stop a running job.
- start a job for a task or taskflow.
slug: data-integration
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
