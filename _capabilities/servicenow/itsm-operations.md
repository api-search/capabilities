---
consumed_apis:
- servicenow-table
- servicenow-aggregate
- servicenow-change-management
- servicenow-trouble-ticket
description: Unified workflow for IT Service Management operations combining table records, aggregate analytics, change management, and trouble tickets. Used by ITSM administrators and service desk agents to manage incidents, changes, and operational reporting.
layout: capability
name: ServiceNow ITSM Operations
operations:
- description: List records from any ServiceNow table.
  method: GET
  name: list-records
  path: /v1/records/{tableName}
- description: Create a record in any table.
  method: POST
  name: create-record
  path: /v1/records/{tableName}
- description: Get a single record.
  method: GET
  name: get-record
  path: /v1/records/{tableName}/{sys_id}
- description: Update a record.
  method: PUT
  name: update-record
  path: /v1/records/{tableName}/{sys_id}
- description: Delete a record.
  method: DELETE
  name: delete-record
  path: /v1/records/{tableName}/{sys_id}
- description: Compute aggregate statistics.
  method: GET
  name: get-aggregate-stats
  path: /v1/aggregate-stats/{tableName}
- description: List normal change requests.
  method: GET
  name: list-normal-changes
  path: /v1/normal-changes
- description: Create a normal change request.
  method: POST
  name: create-normal-change
  path: /v1/normal-changes
- description: Get a normal change request.
  method: GET
  name: get-normal-change
  path: /v1/normal-changes/{sys_id}
- description: Update a normal change request.
  method: PATCH
  name: update-normal-change
  path: /v1/normal-changes/{sys_id}
- description: List emergency changes.
  method: GET
  name: list-emergency-changes
  path: /v1/emergency-changes
- description: Create an emergency change.
  method: POST
  name: create-emergency-change
  path: /v1/emergency-changes
- description: List standard changes.
  method: GET
  name: list-standard-changes
  path: /v1/standard-changes
- description: List trouble tickets.
  method: GET
  name: list-trouble-tickets
  path: /v1/trouble-tickets
- description: Create a trouble ticket.
  method: POST
  name: create-trouble-ticket
  path: /v1/trouble-tickets
- description: Get a trouble ticket.
  method: GET
  name: get-trouble-ticket
  path: /v1/trouble-tickets/{id}
- description: Update a trouble ticket.
  method: PATCH
  name: update-trouble-ticket
  path: /v1/trouble-tickets/{id}
personas: []
provider_name: ServiceNow
provider_slug: servicenow
search_terms:
- retrieve a single record by table name and sys_id.
- create a trouble ticket (case, incident, or service problem case).
- cloud services
- workflow automation
- get aggregate stats
- emergency change operations.
- create a new normal change request.
- change management
- create a trouble ticket.
- get a normal change request.
- create standard change
- delete a record.
- create change task
- update an existing record in a servicenow table.
- retrieve a specific trouble ticket.
- servicenow
- delete record
- workflows
- permanently delete a record from a servicenow table.
- t1
- update a trouble ticket.
- list emergency changes
- trouble ticket operations.
- list trouble tickets.
- digital workflows
- compute aggregate statistics on any servicenow table.
- list normal change requests.
- it service management
- update trouble ticket
- update a normal change request.
- retrieve a specific normal change request.
- create normal change
- list change tasks
- create a new record in any servicenow table.
- normal change request management.
- list standard changes.
- incident management
- single trouble ticket operations.
- update an existing trouble ticket.
- get record
- create an emergency change for urgent situations.
- service desk
- list normal changes
- create a record in any table.
- processes
- get a trouble ticket.
- update a record.
- list records
- list standard change requests.
- list tasks for a change request.
- create a normal change request.
- list emergency changes.
- standard change operations.
- list standard changes
- aggregate statistics on table data.
- list emergency change requests.
- get normal change
- generic table record operations for any servicenow table.
- get trouble ticket
- list trouble tickets with filtering by severity, status, and type.
- create trouble ticket
- compute aggregate statistics.
- update record
- create a task for a change request.
- enterprise platform
- create emergency change
- single normal change operations.
- create a standard change from a template.
- automation
- itsm
- single record operations.
- create record
- list trouble tickets
- list records from any servicenow table with query filtering.
- create an emergency change.
- update normal change
- list records from any servicenow table.
- get a single record.
slug: itsm-operations
tags:
- ServiceNow
- ITSM
- Change Management
- Incident Management
- Service Desk
tools:
- description: List records from any ServiceNow table with query filtering.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-records
- description: Create a new record in any ServiceNow table.
  hints:
    idempotent: false
    readOnly: false
  name: create-record
- description: Retrieve a single record by table name and sys_id.
  hints:
    idempotent: true
    readOnly: true
  name: get-record
- description: Update an existing record in a ServiceNow table.
  hints:
    idempotent: true
    readOnly: false
  name: update-record
- description: Permanently delete a record from a ServiceNow table.
  hints:
    destructive: true
    idempotent: true
  name: delete-record
- description: Compute aggregate statistics on any ServiceNow table.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-aggregate-stats
- description: List normal change requests.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-normal-changes
- description: Create a new normal change request.
  hints:
    idempotent: false
    readOnly: false
  name: create-normal-change
- description: Retrieve a specific normal change request.
  hints:
    idempotent: true
    readOnly: true
  name: get-normal-change
- description: Update a normal change request.
  hints:
    idempotent: true
    readOnly: false
  name: update-normal-change
- description: List standard change requests.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-standard-changes
- description: Create a standard change from a template.
  hints:
    idempotent: false
    readOnly: false
  name: create-standard-change
- description: List emergency change requests.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-emergency-changes
- description: Create an emergency change for urgent situations.
  hints:
    idempotent: false
    readOnly: false
  name: create-emergency-change
- description: List tasks for a change request.
  hints:
    idempotent: true
    readOnly: true
  name: list-change-tasks
- description: Create a task for a change request.
  hints:
    idempotent: false
    readOnly: false
  name: create-change-task
- description: List trouble tickets with filtering by severity, status, and type.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-trouble-tickets
- description: Create a trouble ticket (Case, Incident, or Service Problem Case).
  hints:
    idempotent: false
    readOnly: false
  name: create-trouble-ticket
- description: Retrieve a specific trouble ticket.
  hints:
    idempotent: true
    readOnly: true
  name: get-trouble-ticket
- description: Update an existing trouble ticket.
  hints:
    idempotent: true
    readOnly: false
  name: update-trouble-ticket
---
