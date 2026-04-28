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
- get connection details by id.
- list all task schedules.
- list connections
- update schedule
- delete schedule
- update a schedule.
- data governance
- data integration
- list all connections.
- list all mappings.
- authenticate and obtain a session id.
- reference data management
- get mapping task details by id.
- master data management
- data mapping management.
- login
- delete mapping task
- data quality
- mapping task management.
- list mappings
- list all data source connections.
- start a job.
- list schedules
- create a new schedule.
- get schedule
- data profiling
- get connection details.
- create a new data source connection.
- b2b gateway
- create connection
- update mapping task
- informatica
- list all data mappings.
- list all mapping tasks.
- get mapping
- iics
- job execution management.
- address verification
- delete a schedule.
- start a job for a task or taskflow.
- create a new connection.
- get connection
- update connection
- create mapping task
- individual connection management.
- enterprise software
- idmc
- delete connection
- create schedule
- pipeline management
- update a mapping task.
- update a connection.
- etl
- start job
- update an existing connection.
- get mapping task
- delete a mapping task.
- stop job
- data source connection management.
- retrieve the activity log.
- get activity log
- create a new mapping task.
- stop a running job.
- list mapping tasks
- cloud services
- delete a connection.
- get mapping details by id.
- get schedule details by id.
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
