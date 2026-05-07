---
categories: []
consumed_apis: []
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
- create a trouble ticket.
- generic table record operations for any servicenow table.
- create a task for a change request.
- update a trouble ticket.
- aggregate statistics on table data.
- delete record
- update a normal change request.
- update an existing trouble ticket.
- list trouble tickets.
- list records from any servicenow table.
- standard change operations.
- trouble ticket operations.
- itsm
- create a trouble ticket (case, incident, or service problem case).
- list tasks for a change request.
- get normal change
- list standard changes
- workflow automation
- create a new record in any servicenow table.
- list emergency changes
- get record
- create standard change
- update record
- create a new normal change request.
- digital workflows
- get a single record.
- workflows
- processes
- create a record in any table.
- create an emergency change for urgent situations.
- create trouble ticket
- create change task
- automation
- create record
- create emergency change
- update an existing record in a servicenow table.
- list trouble tickets
- retrieve a specific normal change request.
- update normal change
- get aggregate stats
- get trouble ticket
- it service management
- list standard changes.
- get a trouble ticket.
- list records
- list normal changes
- change management
- service desk
- list trouble tickets with filtering by severity, status, and type.
- delete a record.
- create an emergency change.
- create a standard change from a template.
- get a normal change request.
- create a normal change request.
- retrieve a single record by table name and sys_id.
- compute aggregate statistics on any servicenow table.
- single trouble ticket operations.
- update a record.
- normal change request management.
- retrieve a specific trouble ticket.
- create normal change
- single record operations.
- list emergency changes.
- list standard change requests.
- enterprise platform
- list normal change requests.
- t1
- update trouble ticket
- list emergency change requests.
- incident management
- single normal change operations.
- list records from any servicenow table with query filtering.
- cloud services
- servicenow
- compute aggregate statistics.
- emergency change operations.
- list change tasks
- permanently delete a record from a servicenow table.
slug: itsm-operations
source_filename: itsm-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: ServiceNow ITSM Operations\n  description: Unified workflow for IT Service Management operations combining table records, aggregate analytics, change\n    management, and trouble tickets. Used by ITSM administrators and service desk agents to manage incidents, changes, and\n    operational reporting.\n  tags:\n  - ServiceNow\n  - ITSM\n  - Change Management\n  - Incident Management\n  - Service Desk\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SERVICENOW_USERNAME: SERVICENOW_USERNAME\n    SERVICENOW_PASSWORD: SERVICENOW_PASSWORD\n    SERVICENOW_INSTANCE: SERVICENOW_INSTANCE\ncapability:\n  consumes:\n  - type: http\n    namespace: servicenow-table\n    baseUri: https://{{SERVICENOW_INSTANCE}}.service-now.com/api/now\n    description: ServiceNow Table API for CRUD operations on any table.\n    authentication:\n      type: basic\n      username: '{{SERVICENOW_USERNAME}}'\n      password: '{{SERVICENOW_PASSWORD}}'\n\
  \    resources:\n    - name: table-records\n      path: /table\n      description: Table record CRUD operations.\n      operations:\n      - name: list-records\n        method: GET\n        path: /{tableName}\n        description: List records from a ServiceNow table.\n        inputParameters:\n        - name: tableName\n          in: path\n          type: string\n          required: true\n          description: The name of the ServiceNow table.\n        - name: sysparm_query\n          in: query\n          type: string\n          required: false\n          description: Encoded query string to filter results.\n        - name: sysparm_fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return.\n        - name: sysparm_limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of records to return.\n        - name: sysparm_offset\n          in: query\n\
  \          type: integer\n          required: false\n          description: Starting record index for pagination.\n        - name: sysparm_display_value\n          in: query\n          type: string\n          required: false\n          description: Controls display vs actual values in response.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n      - name: create-record\n        method: POST\n        path: /{tableName}\n        description: Create a new record in a ServiceNow table.\n        inputParameters:\n        - name: tableName\n          in: path\n          type: string\n          required: true\n          description: The name of the ServiceNow table.\n        body:\n          type: json\n          data: '{{tools.record_data}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n      - name: get-record\n       \
  \ method: GET\n        path: /{tableName}/{sys_id}\n        description: Retrieve a single record by sys_id.\n        inputParameters:\n        - name: tableName\n          in: path\n          type: string\n          required: true\n          description: The name of the ServiceNow table.\n        - name: sys_id\n          in: path\n          type: string\n          required: true\n          description: The unique 32-character system identifier.\n        - name: sysparm_fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n      - name: update-record\n        method: PUT\n        path: /{tableName}/{sys_id}\n        description: Update an existing record.\n        inputParameters:\n        - name: tableName\n          in: path\n          type: string\n          required:\
  \ true\n          description: The name of the ServiceNow table.\n        - name: sys_id\n          in: path\n          type: string\n          required: true\n          description: The unique 32-character system identifier.\n        body:\n          type: json\n          data: '{{tools.record_data}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n      - name: patch-record\n        method: PATCH\n        path: /{tableName}/{sys_id}\n        description: Partially update an existing record.\n        inputParameters:\n        - name: tableName\n          in: path\n          type: string\n          required: true\n          description: The name of the ServiceNow table.\n        - name: sys_id\n          in: path\n          type: string\n          required: true\n          description: The unique 32-character system identifier.\n        body:\n          type: json\n          data: '{{tools.record_data}}'\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n      - name: delete-record\n        method: DELETE\n        path: /{tableName}/{sys_id}\n        description: Permanently delete a record.\n        inputParameters:\n        - name: tableName\n          in: path\n          type: string\n          required: true\n          description: The name of the ServiceNow table.\n        - name: sys_id\n          in: path\n          type: string\n          required: true\n          description: The unique 32-character system identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: servicenow-aggregate\n    baseUri: https://{{SERVICENOW_INSTANCE}}.service-now.com/api/now\n    description: ServiceNow Aggregate API for computing statistics on table records.\n    authentication:\n      type: basic\n      username:\
  \ '{{SERVICENOW_USERNAME}}'\n      password: '{{SERVICENOW_PASSWORD}}'\n    resources:\n    - name: aggregate-statistics\n      path: /stats\n      description: Aggregate statistics operations on ServiceNow tables.\n      operations:\n      - name: get-aggregate-stats\n        method: GET\n        path: /{tableName}\n        description: Computes aggregate statistics for records in the specified table.\n        inputParameters:\n        - name: tableName\n          in: path\n          type: string\n          required: true\n          description: The name of the ServiceNow table to compute statistics on.\n        - name: sysparm_query\n          in: query\n          type: string\n          required: false\n          description: Encoded query string to filter records before aggregation.\n        - name: sysparm_count\n          in: query\n          type: boolean\n          required: false\n          description: When true, returns the count of matching records.\n        - name: sysparm_sum_fields\n\
  \          in: query\n          type: string\n          required: false\n          description: Comma-separated list of numeric fields for sum calculation.\n        - name: sysparm_avg_fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of numeric fields for average calculation.\n        - name: sysparm_min_fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields for minimum value.\n        - name: sysparm_max_fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields for maximum value.\n        - name: sysparm_group_by\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to group results by.\n        - name: sysparm_order_by\n          in: query\n          type: string\n          required: false\n\
  \          description: Field by which to order grouped results.\n        - name: sysparm_having\n          in: query\n          type: string\n          required: false\n          description: Filter applied after aggregation to restrict groups.\n        - name: sysparm_display_value\n          in: query\n          type: string\n          required: false\n          description: Controls whether display values or actual values are returned.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n  - type: http\n    namespace: servicenow-change-management\n    baseUri: https://{{SERVICENOW_INSTANCE}}.service-now.com/api/sn_chg_rest/v1\n    description: ServiceNow Change Management API for managing change requests and tasks.\n    authentication:\n      type: basic\n      username: '{{SERVICENOW_USERNAME}}'\n      password: '{{SERVICENOW_PASSWORD}}'\n    resources:\n    - name: normal-changes\n      path: /change/normal\n\
  \      description: Normal change request operations.\n      operations:\n      - name: list-normal-changes\n        method: GET\n        description: List normal change requests with optional filtering.\n        inputParameters:\n        - name: sysparm_query\n          in: query\n          type: string\n          required: false\n          description: Encoded query string to filter results.\n        - name: sysparm_fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return.\n        - name: sysparm_limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of records to return.\n        - name: sysparm_offset\n          in: query\n          type: integer\n          required: false\n          description: Starting record index for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.result\n      - name: create-normal-change\n        method: POST\n        description: Create a new normal change request.\n        inputParameters:\n        - name: sysparm_fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return.\n        body:\n          type: json\n          data:\n            short_description: '{{tools.short_description}}'\n            description: '{{tools.description}}'\n            priority: '{{tools.priority}}'\n            risk: '{{tools.risk}}'\n            impact: '{{tools.impact}}'\n            category: '{{tools.category}}'\n            assigned_to: '{{tools.assigned_to}}'\n            assignment_group: '{{tools.assignment_group}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n      - name: get-normal-change\n        method: GET\n        path: /{sys_id}\n       \
  \ description: Retrieve a specific normal change request.\n        inputParameters:\n        - name: sys_id\n          in: path\n          type: string\n          required: true\n          description: The sys_id of the change request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n      - name: update-normal-change\n        method: PATCH\n        path: /{sys_id}\n        description: Update fields on a normal change request.\n        inputParameters:\n        - name: sys_id\n          in: path\n          type: string\n          required: true\n          description: The sys_id of the change request.\n        body:\n          type: json\n          data:\n            short_description: '{{tools.short_description}}'\n            description: '{{tools.description}}'\n            priority: '{{tools.priority}}'\n            state: '{{tools.state}}'\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.result\n    - name: standard-changes\n      path: /change/standard\n      description: Standard change request operations.\n      operations:\n      - name: list-standard-changes\n        method: GET\n        description: List standard change requests.\n        inputParameters:\n        - name: sysparm_query\n          in: query\n          type: string\n          required: false\n          description: Encoded query string to filter results.\n        - name: sysparm_limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of records to return.\n        - name: sysparm_offset\n          in: query\n          type: integer\n          required: false\n          description: Starting record index for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n      - name: create-standard-change\n\
  \        method: POST\n        path: /{standard_change_template_id}\n        description: Create a standard change from a pre-approved template.\n        inputParameters:\n        - name: standard_change_template_id\n          in: path\n          type: string\n          required: true\n          description: The sys_id of the standard change template.\n        body:\n          type: json\n          data:\n            short_description: '{{tools.short_description}}'\n            description: '{{tools.description}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n    - name: emergency-changes\n      path: /change/emergency\n      description: Emergency change request operations.\n      operations:\n      - name: list-emergency-changes\n        method: GET\n        description: List emergency change requests.\n        inputParameters:\n        - name: sysparm_query\n          in: query\n          type: string\n\
  \          required: false\n          description: Encoded query string to filter results.\n        - name: sysparm_limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of records to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n      - name: create-emergency-change\n        method: POST\n        description: Create an emergency change request.\n        body:\n          type: json\n          data:\n            short_description: '{{tools.short_description}}'\n            description: '{{tools.description}}'\n            priority: '{{tools.priority}}'\n            justification: '{{tools.justification}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n    - name: change-tasks\n      path: /change\n      description: Change task operations.\n  \
  \    operations:\n      - name: list-change-tasks\n        method: GET\n        path: /{sys_id}/task\n        description: List tasks for a change request.\n        inputParameters:\n        - name: sys_id\n          in: path\n          type: string\n          required: true\n          description: The sys_id of the change request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.result\n      - name: create-change-task\n        method: POST\n        path: /{sys_id}/task\n        description: Create a task for a change request.\n        inputParameters:\n        - name: sys_id\n          in: path\n          type: string\n          required: true\n          description: The sys_id of the change request.\n        body:\n          type: json\n          data:\n            short_description: '{{tools.short_description}}'\n            assigned_to: '{{tools.assigned_to}}'\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.result\n  - type: http\n    namespace: servicenow-trouble-ticket\n    baseUri: https://{{SERVICENOW_INSTANCE}}.servicenow.com/api/sn_ind_tsm_sdwan/ticket\n    description: ServiceNow Trouble Ticket Open API (TMF621) for managing tickets across Cases, Incidents, and Service Problem\n      Cases.\n    authentication:\n      type: basic\n      username: '{{SERVICENOW_USERNAME}}'\n      password: '{{SERVICENOW_PASSWORD}}'\n    resources:\n    - name: trouble-tickets\n      path: /troubleTicket\n      description: Trouble ticket operations.\n      operations:\n      - name: list-trouble-tickets\n        method: GET\n        description: Retrieve all trouble tickets.\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of fields to return.\n        - name: id\n          in: query\n          type: string\n       \
  \   required: false\n          description: Filter by sys_id.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum records to return.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Starting index for pagination.\n        - name: severity\n          in: query\n          type: string\n          required: false\n          description: Filter by severity.\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status.\n        - name: ticketType\n          in: query\n          type: string\n          required: false\n          description: Filter by ticket type (Case, Incident, Service Problem Case).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-trouble-ticket\n       \
  \ method: POST\n        description: Create a trouble ticket.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            severity: '{{tools.severity}}'\n            status: '{{tools.status}}'\n            ticketType: '{{tools.ticketType}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-trouble-ticket\n        method: GET\n        path: /{id}\n        description: Retrieve a specific trouble ticket.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The sys_id of the trouble ticket.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Fields to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n         \
  \ type: object\n          value: $.\n      - name: update-trouble-ticket\n        method: PATCH\n        path: /{id}\n        description: Update a trouble ticket.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The sys_id of the trouble ticket.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            severity: '{{tools.severity}}'\n            status: '{{tools.status}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: servicenow-itsm-operations-api\n    description: Unified REST API for ServiceNow ITSM operations including records, changes, and trouble tickets.\n    resources:\n    - path: /v1/records/{tableName}\n      name: table-records\n      description: Generic\
  \ table record operations for any ServiceNow table.\n      operations:\n      - method: GET\n        name: list-records\n        description: List records from any ServiceNow table.\n        call: servicenow-table.list-records\n        with:\n          tableName: rest.tableName\n          sysparm_query: rest.sysparm_query\n          sysparm_fields: rest.sysparm_fields\n          sysparm_limit: rest.sysparm_limit\n          sysparm_offset: rest.sysparm_offset\n        outputParameters:\n        - type: object\n          mapping: $.result\n      - method: POST\n        name: create-record\n        description: Create a record in any table.\n        call: servicenow-table.create-record\n        with:\n          tableName: rest.tableName\n          record_data: rest.body\n        outputParameters:\n        - type: object\n          mapping: $.result\n    - path: /v1/records/{tableName}/{sys_id}\n      name: table-record-detail\n      description: Single record operations.\n      operations:\n\
  \      - method: GET\n        name: get-record\n        description: Get a single record.\n        call: servicenow-table.get-record\n        with:\n          tableName: rest.tableName\n          sys_id: rest.sys_id\n        outputParameters:\n        - type: object\n          mapping: $.result\n      - method: PUT\n        name: update-record\n        description: Update a record.\n        call: servicenow-table.update-record\n        with:\n          tableName: rest.tableName\n          sys_id: rest.sys_id\n          record_data: rest.body\n        outputParameters:\n        - type: object\n          mapping: $.result\n      - method: DELETE\n        name: delete-record\n        description: Delete a record.\n        call: servicenow-table.delete-record\n        with:\n          tableName: rest.tableName\n          sys_id: rest.sys_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/aggregate-stats/{tableName}\n      name: aggregate-statistics\n\
  \      description: Aggregate statistics on table data.\n      operations:\n      - method: GET\n        name: get-aggregate-stats\n        description: Compute aggregate statistics.\n        call: servicenow-aggregate.get-aggregate-stats\n        with:\n          tableName: rest.tableName\n          sysparm_query: rest.sysparm_query\n          sysparm_count: rest.sysparm_count\n          sysparm_sum_fields: rest.sysparm_sum_fields\n          sysparm_group_by: rest.sysparm_group_by\n        outputParameters:\n        - type: object\n          mapping: $.result\n    - path: /v1/normal-changes\n      name: normal-changes\n      description: Normal change request management.\n      operations:\n      - method: GET\n        name: list-normal-changes\n        description: List normal change requests.\n        call: servicenow-change-management.list-normal-changes\n        with:\n          sysparm_query: rest.sysparm_query\n          sysparm_limit: rest.sysparm_limit\n        outputParameters:\n\
  \        - type: object\n          mapping: $.result\n      - method: POST\n        name: create-normal-change\n        description: Create a normal change request.\n        call: servicenow-change-management.create-normal-change\n        with:\n          short_description: rest.short_description\n          description: rest.description\n          priority: rest.priority\n        outputParameters:\n        - type: object\n          mapping: $.result\n    - path: /v1/normal-changes/{sys_id}\n      name: normal-change-detail\n      description: Single normal change operations.\n      operations:\n      - method: GET\n        name: get-normal-change\n        description: Get a normal change request.\n        call: servicenow-change-management.get-normal-change\n        with:\n          sys_id: rest.sys_id\n        outputParameters:\n        - type: object\n          mapping: $.result\n      - method: PATCH\n        name: update-normal-change\n        description: Update a normal change request.\n\
  \        call: servicenow-change-management.update-normal-change\n        with:\n          sys_id: rest.sys_id\n        outputParameters:\n        - type: object\n          mapping: $.result\n    - path: /v1/emergency-changes\n      name: emergency-changes\n      description: Emergency change operations.\n      operations:\n      - method: GET\n        name: list-emergency-changes\n        description: List emergency changes.\n        call: servicenow-change-management.list-emergency-changes\n        with:\n          sysparm_query: rest.sysparm_query\n        outputParameters:\n        - type: object\n          mapping: $.result\n      - method: POST\n        name: create-emergency-change\n        description: Create an emergency change.\n        call: servicenow-change-management.create-emergency-change\n        with:\n          short_description: rest.short_description\n          description: rest.description\n        outputParameters:\n        - type: object\n          mapping: $.result\n\
  \    - path: /v1/standard-changes\n      name: standard-changes\n      description: Standard change operations.\n      operations:\n      - method: GET\n        name: list-standard-changes\n        description: List standard changes.\n        call: servicenow-change-management.list-standard-changes\n        with:\n          sysparm_query: rest.sysparm_query\n        outputParameters:\n        - type: object\n          mapping: $.result\n    - path: /v1/trouble-tickets\n      name: trouble-tickets\n      description: Trouble ticket operations.\n      operations:\n      - method: GET\n        name: list-trouble-tickets\n        description: List trouble tickets.\n        call: servicenow-trouble-ticket.list-trouble-tickets\n        with:\n          limit: rest.limit\n          severity: rest.severity\n          status: rest.status\n          ticketType: rest.ticketType\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-trouble-ticket\n\
  \        description: Create a trouble ticket.\n        call: servicenow-trouble-ticket.create-trouble-ticket\n        with:\n          name: rest.name\n          description: rest.description\n          severity: rest.severity\n          status: rest.status\n          ticketType: rest.ticketType\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/trouble-tickets/{id}\n      name: trouble-ticket-detail\n      description: Single trouble ticket operations.\n      operations:\n      - method: GET\n        name: get-trouble-ticket\n        description: Get a trouble ticket.\n        call: servicenow-trouble-ticket.get-trouble-ticket\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-trouble-ticket\n        description: Update a trouble ticket.\n        call: servicenow-trouble-ticket.update-trouble-ticket\n        with:\n          id: rest.id\n \
  \       outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: servicenow-itsm-operations-mcp\n    transport: http\n    description: MCP server for AI-assisted ServiceNow ITSM operations.\n    tools:\n    - name: list-records\n      description: List records from any ServiceNow table with query filtering.\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: servicenow-table.list-records\n      with:\n        tableName: tools.tableName\n        sysparm_query: tools.sysparm_query\n        sysparm_fields: tools.sysparm_fields\n        sysparm_limit: tools.sysparm_limit\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: create-record\n      description: Create a new record in any ServiceNow table.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: servicenow-table.create-record\n      with:\n        tableName: tools.tableName\n\
  \        record_data: tools.record_data\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: get-record\n      description: Retrieve a single record by table name and sys_id.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: servicenow-table.get-record\n      with:\n        tableName: tools.tableName\n        sys_id: tools.sys_id\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: update-record\n      description: Update an existing record in a ServiceNow table.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: servicenow-table.update-record\n      with:\n        tableName: tools.tableName\n        sys_id: tools.sys_id\n        record_data: tools.record_data\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: delete-record\n      description: Permanently delete a record from a ServiceNow table.\n      hints:\n        destructive:\
  \ true\n        idempotent: true\n      call: servicenow-table.delete-record\n      with:\n        tableName: tools.tableName\n        sys_id: tools.sys_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-aggregate-stats\n      description: Compute aggregate statistics on any ServiceNow table.\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: servicenow-aggregate.get-aggregate-stats\n      with:\n        tableName: tools.tableName\n        sysparm_query: tools.sysparm_query\n        sysparm_count: tools.sysparm_count\n        sysparm_sum_fields: tools.sysparm_sum_fields\n        sysparm_group_by: tools.sysparm_group_by\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: list-normal-changes\n      description: List normal change requests.\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: servicenow-change-management.list-normal-changes\n\
  \      with:\n        sysparm_query: tools.sysparm_query\n        sysparm_limit: tools.sysparm_limit\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: create-normal-change\n      description: Create a new normal change request.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: servicenow-change-management.create-normal-change\n      with:\n        short_description: tools.short_description\n        description: tools.description\n        priority: tools.priority\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: get-normal-change\n      description: Retrieve a specific normal change request.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: servicenow-change-management.get-normal-change\n      with:\n        sys_id: tools.sys_id\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: update-normal-change\n      description: Update\
  \ a normal change request.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: servicenow-change-management.update-normal-change\n      with:\n        sys_id: tools.sys_id\n        short_description: tools.short_description\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: list-standard-changes\n      description: List standard change requests.\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: servicenow-change-management.list-standard-changes\n      with:\n        sysparm_query: tools.sysparm_query\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: create-standard-change\n      description: Create a standard change from a template.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: servicenow-change-management.create-standard-change\n      with:\n        standard_change_template_id: tools.standard_change_template_id\n\
  \      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: list-emergency-changes\n      description: List emergency change requests.\n      hints:\n        readOnly: true\n        idempotent: true\n        openWorld: true\n      call: servicenow-change-management.list-emergency-changes\n      with:\n        sysparm_query: tools.sysparm_query\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: create-emergency-change\n      description: Create an emergency change for urgent situations.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: servicenow-change-management.create-emergency-change\n      with:\n        short_description: tools.short_description\n        description: tools.description\n        priority: tools.priority\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: list-change-tasks\n      description: List tasks for a change request.\n      hints:\n \
  \       readOnly: true\n        idempotent: true\n      call: servicenow-change-management.list-change-tasks\n      with:\n        sys_id: tools.sys_id\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: create-change-task\n      description: Create a task for a change request.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: servicenow-change-management.create-change-task\n      with:\n        sys_id: tools.sys_id\n        short_description: tools.short_description\n      outputParameters:\n      - type: object\n        mapping: $.result\n    - name: list-trouble-tickets\n      d\n\n# --- truncated at 32 KB (33 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/servicenow/refs/heads/main/capabilities/itsm-operations.yaml\n"
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
