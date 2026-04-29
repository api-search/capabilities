---
api_specs:
- filename: trouble-ticket-openapi.yaml
  format: yaml
  label: servicenow-trouble-ticket
  slug: servicenow-trouble-ticket
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/servicenow/refs/heads/main/openapi/trouble-ticket-openapi.yaml
categories: []
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
- list emergency changes.
- create emergency change
- get record
- compute aggregate statistics.
- single record operations.
- get a normal change request.
- list emergency change requests.
- create a normal change request.
- automation
- create change task
- update a trouble ticket.
- list standard change requests.
- aggregate statistics on table data.
- create standard change
- enterprise platform
- normal change request management.
- create trouble ticket
- update an existing record in a servicenow table.
- single normal change operations.
- workflows
- create a trouble ticket (case, incident, or service problem case).
- update trouble ticket
- update an existing trouble ticket.
- list records from any servicenow table with query filtering.
- create an emergency change for urgent situations.
- create a trouble ticket.
- workflow automation
- itsm
- retrieve a single record by table name and sys_id.
- create a record in any table.
- list normal change requests.
- permanently delete a record from a servicenow table.
- get trouble ticket
- create an emergency change.
- processes
- get a single record.
- update a normal change request.
- create record
- list tasks for a change request.
- create a new normal change request.
- delete record
- update a record.
- change management
- list change tasks
- servicenow
- create normal change
- list records
- create a new record in any servicenow table.
- retrieve a specific normal change request.
- trouble ticket operations.
- list records from any servicenow table.
- digital workflows
- update normal change
- t1
- list standard changes.
- create a standard change from a template.
- list standard changes
- list trouble tickets with filtering by severity, status, and type.
- list normal changes
- delete a record.
- single trouble ticket operations.
- retrieve a specific trouble ticket.
- cloud services
- create a task for a change request.
- list emergency changes
- standard change operations.
- update record
- get normal change
- get aggregate stats
- list trouble tickets
- compute aggregate statistics on any servicenow table.
- list trouble tickets.
- it service management
- incident management
- generic table record operations for any servicenow table.
- emergency change operations.
- get a trouble ticket.
- service desk
slug: itsm-operations
source_filename: itsm-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"ServiceNow ITSM Operations\"\n  description: \"Unified workflow for IT Service Management operations combining table records, aggregate analytics, change management, and trouble tickets. Used by ITSM administrators and service desk agents to manage incidents, changes, and operational reporting.\"\n  tags:\n    - ServiceNow\n    - ITSM\n    - Change Management\n    - Incident Management\n    - Service Desk\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      SERVICENOW_USERNAME: SERVICENOW_USERNAME\n      SERVICENOW_PASSWORD: SERVICENOW_PASSWORD\n      SERVICENOW_INSTANCE: SERVICENOW_INSTANCE\n\ncapability:\n  consumes:\n    - import: servicenow-table\n      location: ./shared/table.yaml\n    - import: servicenow-aggregate\n      location: ./shared/aggregate.yaml\n    - import: servicenow-change-management\n      location: ./shared/change-management.yaml\n    - import: servicenow-trouble-ticket\n\
  \      location: ./shared/trouble-ticket.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: servicenow-itsm-operations-api\n      description: \"Unified REST API for ServiceNow ITSM operations including records, changes, and trouble tickets.\"\n      resources:\n        - path: /v1/records/{tableName}\n          name: table-records\n          description: \"Generic table record operations for any ServiceNow table.\"\n          operations:\n            - method: GET\n              name: list-records\n              description: \"List records from any ServiceNow table.\"\n              call: \"servicenow-table.list-records\"\n              with:\n                tableName: \"rest.tableName\"\n                sysparm_query: \"rest.sysparm_query\"\n                sysparm_fields: \"rest.sysparm_fields\"\n                sysparm_limit: \"rest.sysparm_limit\"\n                sysparm_offset: \"rest.sysparm_offset\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.result\"\n            - method: POST\n              name: create-record\n              description: \"Create a record in any table.\"\n              call: \"servicenow-table.create-record\"\n              with:\n                tableName: \"rest.tableName\"\n                record_data: \"rest.body\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.result\"\n        - path: /v1/records/{tableName}/{sys_id}\n          name: table-record-detail\n          description: \"Single record operations.\"\n          operations:\n            - method: GET\n              name: get-record\n              description: \"Get a single record.\"\n              call: \"servicenow-table.get-record\"\n              with:\n                tableName: \"rest.tableName\"\n                sys_id: \"rest.sys_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.result\"\n     \
  \       - method: PUT\n              name: update-record\n              description: \"Update a record.\"\n              call: \"servicenow-table.update-record\"\n              with:\n                tableName: \"rest.tableName\"\n                sys_id: \"rest.sys_id\"\n                record_data: \"rest.body\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.result\"\n            - method: DELETE\n              name: delete-record\n              description: \"Delete a record.\"\n              call: \"servicenow-table.delete-record\"\n              with:\n                tableName: \"rest.tableName\"\n                sys_id: \"rest.sys_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/aggregate-stats/{tableName}\n          name: aggregate-statistics\n          description: \"Aggregate statistics on table data.\"\n          operations:\n            - method: GET\n\
  \              name: get-aggregate-stats\n              description: \"Compute aggregate statistics.\"\n              call: \"servicenow-aggregate.get-aggregate-stats\"\n              with:\n                tableName: \"rest.tableName\"\n                sysparm_query: \"rest.sysparm_query\"\n                sysparm_count: \"rest.sysparm_count\"\n                sysparm_sum_fields: \"rest.sysparm_sum_fields\"\n                sysparm_group_by: \"rest.sysparm_group_by\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.result\"\n        - path: /v1/normal-changes\n          name: normal-changes\n          description: \"Normal change request management.\"\n          operations:\n            - method: GET\n              name: list-normal-changes\n              description: \"List normal change requests.\"\n              call: \"servicenow-change-management.list-normal-changes\"\n              with:\n                sysparm_query: \"rest.sysparm_query\"\
  \n                sysparm_limit: \"rest.sysparm_limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.result\"\n            - method: POST\n              name: create-normal-change\n              description: \"Create a normal change request.\"\n              call: \"servicenow-change-management.create-normal-change\"\n              with:\n                short_description: \"rest.short_description\"\n                description: \"rest.description\"\n                priority: \"rest.priority\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.result\"\n        - path: /v1/normal-changes/{sys_id}\n          name: normal-change-detail\n          description: \"Single normal change operations.\"\n          operations:\n            - method: GET\n              name: get-normal-change\n              description: \"Get a normal change request.\"\n              call: \"servicenow-change-management.get-normal-change\"\
  \n              with:\n                sys_id: \"rest.sys_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.result\"\n            - method: PATCH\n              name: update-normal-change\n              description: \"Update a normal change request.\"\n              call: \"servicenow-change-management.update-normal-change\"\n              with:\n                sys_id: \"rest.sys_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.result\"\n        - path: /v1/emergency-changes\n          name: emergency-changes\n          description: \"Emergency change operations.\"\n          operations:\n            - method: GET\n              name: list-emergency-changes\n              description: \"List emergency changes.\"\n              call: \"servicenow-change-management.list-emergency-changes\"\n              with:\n                sysparm_query: \"rest.sysparm_query\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.result\"\n            - method: POST\n              name: create-emergency-change\n              description: \"Create an emergency change.\"\n              call: \"servicenow-change-management.create-emergency-change\"\n              with:\n                short_description: \"rest.short_description\"\n                description: \"rest.description\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.result\"\n        - path: /v1/standard-changes\n          name: standard-changes\n          description: \"Standard change operations.\"\n          operations:\n            - method: GET\n              name: list-standard-changes\n              description: \"List standard changes.\"\n              call: \"servicenow-change-management.list-standard-changes\"\n              with:\n                sysparm_query: \"rest.sysparm_query\"\n              outputParameters:\n            \
  \    - type: object\n                  mapping: \"$.result\"\n        - path: /v1/trouble-tickets\n          name: trouble-tickets\n          description: \"Trouble ticket operations.\"\n          operations:\n            - method: GET\n              name: list-trouble-tickets\n              description: \"List trouble tickets.\"\n              call: \"servicenow-trouble-ticket.list-trouble-tickets\"\n              with:\n                limit: \"rest.limit\"\n                severity: \"rest.severity\"\n                status: \"rest.status\"\n                ticketType: \"rest.ticketType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-trouble-ticket\n              description: \"Create a trouble ticket.\"\n              call: \"servicenow-trouble-ticket.create-trouble-ticket\"\n              with:\n                name: \"rest.name\"\n                description: \"rest.description\"\
  \n                severity: \"rest.severity\"\n                status: \"rest.status\"\n                ticketType: \"rest.ticketType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/trouble-tickets/{id}\n          name: trouble-ticket-detail\n          description: \"Single trouble ticket operations.\"\n          operations:\n            - method: GET\n              name: get-trouble-ticket\n              description: \"Get a trouble ticket.\"\n              call: \"servicenow-trouble-ticket.get-trouble-ticket\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-trouble-ticket\n              description: \"Update a trouble ticket.\"\n              call: \"servicenow-trouble-ticket.update-trouble-ticket\"\n              with:\n                id: \"rest.id\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: servicenow-itsm-operations-mcp\n      transport: http\n      description: \"MCP server for AI-assisted ServiceNow ITSM operations.\"\n      tools:\n        - name: list-records\n          description: \"List records from any ServiceNow table with query filtering.\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"servicenow-table.list-records\"\n          with:\n            tableName: \"tools.tableName\"\n            sysparm_query: \"tools.sysparm_query\"\n            sysparm_fields: \"tools.sysparm_fields\"\n            sysparm_limit: \"tools.sysparm_limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n        - name: create-record\n          description: \"Create a new record in any ServiceNow table.\"\n   \
  \       hints:\n            readOnly: false\n            idempotent: false\n          call: \"servicenow-table.create-record\"\n          with:\n            tableName: \"tools.tableName\"\n            record_data: \"tools.record_data\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n        - name: get-record\n          description: \"Retrieve a single record by table name and sys_id.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"servicenow-table.get-record\"\n          with:\n            tableName: \"tools.tableName\"\n            sys_id: \"tools.sys_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n        - name: update-record\n          description: \"Update an existing record in a ServiceNow table.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"servicenow-table.update-record\"\n      \
  \    with:\n            tableName: \"tools.tableName\"\n            sys_id: \"tools.sys_id\"\n            record_data: \"tools.record_data\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n        - name: delete-record\n          description: \"Permanently delete a record from a ServiceNow table.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"servicenow-table.delete-record\"\n          with:\n            tableName: \"tools.tableName\"\n            sys_id: \"tools.sys_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-aggregate-stats\n          description: \"Compute aggregate statistics on any ServiceNow table.\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"servicenow-aggregate.get-aggregate-stats\"\n          with:\n            tableName: \"tools.tableName\"\
  \n            sysparm_query: \"tools.sysparm_query\"\n            sysparm_count: \"tools.sysparm_count\"\n            sysparm_sum_fields: \"tools.sysparm_sum_fields\"\n            sysparm_group_by: \"tools.sysparm_group_by\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n        - name: list-normal-changes\n          description: \"List normal change requests.\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"servicenow-change-management.list-normal-changes\"\n          with:\n            sysparm_query: \"tools.sysparm_query\"\n            sysparm_limit: \"tools.sysparm_limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n        - name: create-normal-change\n          description: \"Create a new normal change request.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call:\
  \ \"servicenow-change-management.create-normal-change\"\n          with:\n            short_description: \"tools.short_description\"\n            description: \"tools.description\"\n            priority: \"tools.priority\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n        - name: get-normal-change\n          description: \"Retrieve a specific normal change request.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"servicenow-change-management.get-normal-change\"\n          with:\n            sys_id: \"tools.sys_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n        - name: update-normal-change\n          description: \"Update a normal change request.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"servicenow-change-management.update-normal-change\"\n          with:\n            sys_id:\
  \ \"tools.sys_id\"\n            short_description: \"tools.short_description\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n        - name: list-standard-changes\n          description: \"List standard change requests.\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"servicenow-change-management.list-standard-changes\"\n          with:\n            sysparm_query: \"tools.sysparm_query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n        - name: create-standard-change\n          description: \"Create a standard change from a template.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"servicenow-change-management.create-standard-change\"\n          with:\n            standard_change_template_id: \"tools.standard_change_template_id\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.result\"\n        - name: list-emergency-changes\n          description: \"List emergency change requests.\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"servicenow-change-management.list-emergency-changes\"\n          with:\n            sysparm_query: \"tools.sysparm_query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n        - name: create-emergency-change\n          description: \"Create an emergency change for urgent situations.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"servicenow-change-management.create-emergency-change\"\n          with:\n            short_description: \"tools.short_description\"\n            description: \"tools.description\"\n            priority: \"tools.priority\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.result\"\n        - name: list-change-tasks\n          description: \"List tasks for a change request.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"servicenow-change-management.list-change-tasks\"\n          with:\n            sys_id: \"tools.sys_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n        - name: create-change-task\n          description: \"Create a task for a change request.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"servicenow-change-management.create-change-task\"\n          with:\n            sys_id: \"tools.sys_id\"\n            short_description: \"tools.short_description\"\n          outputParameters:\n            - type: object\n              mapping: \"$.result\"\n        - name: list-trouble-tickets\n          description: \"List trouble tickets with filtering by severity, status,\
  \ and type.\"\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: \"servicenow-trouble-ticket.list-trouble-tickets\"\n          with:\n            limit: \"tools.limit\"\n            severity: \"tools.severity\"\n            status: \"tools.status\"\n            ticketType: \"tools.ticketType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-trouble-ticket\n          description: \"Create a trouble ticket (Case, Incident, or Service Problem Case).\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"servicenow-trouble-ticket.create-trouble-ticket\"\n          with:\n            name: \"tools.name\"\n            description: \"tools.description\"\n            severity: \"tools.severity\"\n            status: \"tools.status\"\n            ticketType: \"tools.ticketType\"\n          outputParameters:\n         \
  \   - type: object\n              mapping: \"$.\"\n        - name: get-trouble-ticket\n          description: \"Retrieve a specific trouble ticket.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"servicenow-trouble-ticket.get-trouble-ticket\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-trouble-ticket\n          description: \"Update an existing trouble ticket.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"servicenow-trouble-ticket.update-trouble-ticket\"\n          with:\n            id: \"tools.id\"\n            name: \"tools.name\"\n            severity: \"tools.severity\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/servicenow/refs/heads/main/capabilities/itsm-operations.yaml
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
