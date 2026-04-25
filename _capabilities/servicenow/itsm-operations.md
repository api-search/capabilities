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
- create a standard change from a template.
- list emergency change requests.
- automation
- change management
- update an existing record in a servicenow table.
- list trouble tickets
- list records from any servicenow table.
- create standard change
- update record
- list standard changes
- list standard change requests.
- create an emergency change.
- compute aggregate statistics.
- update trouble ticket
- update an existing trouble ticket.
- permanently delete a record from a servicenow table.
- standard change operations.
- single trouble ticket operations.
- list standard changes.
- itsm
- create change task
- list emergency changes
- update a trouble ticket.
- retrieve a specific trouble ticket.
- list tasks for a change request.
- update a normal change request.
- processes
- digital workflows
- list records from any servicenow table with query filtering.
- cloud services
- create normal change
- get a trouble ticket.
- list trouble tickets.
- incident management
- single normal change operations.
- service desk
- retrieve a specific normal change request.
- enterprise platform
- list change tasks
- get trouble ticket
- list normal change requests.
- create a trouble ticket.
- update a record.
- create a trouble ticket (case, incident, or service problem case).
- get a single record.
- create a new normal change request.
- trouble ticket operations.
- list normal changes
- get record
- create trouble ticket
- workflow automation
- compute aggregate statistics on any servicenow table.
- create record
- normal change request management.
- create emergency change
- create an emergency change for urgent situations.
- create a task for a change request.
- generic table record operations for any servicenow table.
- create a normal change request.
- workflows
- delete a record.
- get aggregate stats
- aggregate statistics on table data.
- create a record in any table.
- t1
- update normal change
- delete record
- single record operations.
- get normal change
- list emergency changes.
- it service management
- list records
- list trouble tickets with filtering by severity, status, and type.
- retrieve a single record by table name and sys_id.
- get a normal change request.
- create a new record in any servicenow table.
- emergency change operations.
- servicenow
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
