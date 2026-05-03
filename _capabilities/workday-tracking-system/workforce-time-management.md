---
categories: []
consumed_apis:
- workday-time-tracking
- workday-absence-management
description: Unified capability for managing the complete employee time lifecycle in Workday, combining Time Tracking and Absence Management APIs. Used by HR managers, payroll teams, and workforce administrators to track attendance, process time off, manage schedules, and ensure accurate time records for payroll processing.
layout: capability
name: Workday Workforce Time Management
operations:
- description: List time blocks for a worker
  method: GET
  name: list-time-blocks
  path: /v1/workers/{workerId}/time-blocks
- description: Create a new time block for a worker
  method: POST
  name: create-time-block
  path: /v1/workers/{workerId}/time-blocks
- description: Get a specific time block
  method: GET
  name: get-time-block
  path: /v1/workers/{workerId}/time-blocks/{timeBlockId}
- description: Update a time block
  method: PUT
  name: update-time-block
  path: /v1/workers/{workerId}/time-blocks/{timeBlockId}
- description: Delete a time block
  method: DELETE
  name: delete-time-block
  path: /v1/workers/{workerId}/time-blocks/{timeBlockId}
- description: List time clock events for a worker
  method: GET
  name: list-clock-events
  path: /v1/workers/{workerId}/clock-events
- description: Record a clock-in or clock-out event
  method: POST
  name: create-clock-event
  path: /v1/workers/{workerId}/clock-events
- description: Get the work schedule for a worker
  method: GET
  name: get-schedule
  path: /v1/workers/{workerId}/schedule
- description: Assign a work schedule to a worker
  method: PUT
  name: assign-schedule
  path: /v1/workers/{workerId}/schedule
- description: List timesheets for a worker
  method: GET
  name: list-timesheets
  path: /v1/workers/{workerId}/timesheets
- description: List time off for a worker
  method: GET
  name: list-time-off
  path: /v1/workers/{workerId}/time-off
- description: Request time off for a worker
  method: POST
  name: request-time-off
  path: /v1/workers/{workerId}/time-off
- description: Get time off balances for a worker
  method: GET
  name: list-time-off-balances
  path: /v1/workers/{workerId}/time-off-balances
- description: List leaves of absence for a worker
  method: GET
  name: list-leaves
  path: /v1/workers/{workerId}/leaves
- description: Request a leave of absence
  method: POST
  name: request-leave
  path: /v1/workers/{workerId}/leaves
personas: []
provider_name: Workday Tracking System
provider_slug: workday-tracking-system
search_terms:
- timesheets for a worker
- list leave of absence records for a worker
- request time off
- get the work schedule for a worker
- get the current work schedule assigned to a worker
- list accrual balance overrides for a worker
- assign work schedule
- assign a work schedule to a worker
- workday
- work schedule for a worker
- time off requests for a worker
- list time blocks for a worker
- create clock event
- hr
- request leave
- submit a time off request for a worker
- get schedule
- hcm
- workforce management
- absence management
- list leaves
- list timesheets for a worker for a period
- get details of a specific time block
- request time off for a worker
- a specific time block
- update time block
- timesheets
- leave of absence records for a worker
- request a leave of absence
- list timesheets for a worker
- record a clock-in or clock-out event
- list leaves of absence for a worker
- delete a time block
- get work schedule
- get a specific time block
- get time off plan balances for a worker
- list time off balances
- list accrual overrides
- create a new time block entry for a worker
- create time block
- submit a leave of absence request for a worker
- get time block
- delete time block
- get time off balances for a worker
- time off plan balances for a worker
- record a clock-in or clock-out event from a time device
- assign schedule
- list time clock events (punches) for a worker
- enterprise
- list time clock events for a worker
- time clock events for a worker
- create a new time block for a worker
- time tracking
- delete a reported time block
- scheduling
- payroll
- list time off for a worker
- list time blocks recorded by a workday worker in a date range
- attendance
- list time off
- list leaves of absence
- request leave of absence
- list time blocks
- list clock events
- update an existing time block
- human capital management
- list timesheets
- update a time block
- time blocks recorded by a worker
- list time off requests for a worker
slug: workforce-time-management
source_filename: workforce-time-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Workday Workforce Time Management\"\n  description: >-\n    Unified capability for managing the complete employee time lifecycle in Workday,\n    combining Time Tracking and Absence Management APIs. Used by HR managers, payroll\n    teams, and workforce administrators to track attendance, process time off, manage\n    schedules, and ensure accurate time records for payroll processing.\n  tags:\n    - Workday\n    - Time Tracking\n    - Absence Management\n    - Workforce Management\n    - HR\n    - Payroll\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WORKDAY_BEARER_TOKEN: WORKDAY_BEARER_TOKEN\n      WORKDAY_TENANT: WORKDAY_TENANT\n\ncapability:\n  consumes:\n    - import: workday-time-tracking\n      location: ./shared/time-tracking.yaml\n    - import: workday-absence-management\n      location: ./shared/absence-management.yaml\n\n  exposes:\n    - type: rest\n      port:\
  \ 8080\n      namespace: workforce-time-management-api\n      description: \"Unified REST API for complete workforce time management.\"\n      resources:\n        - path: /v1/workers/{workerId}/time-blocks\n          name: time-blocks\n          description: \"Time blocks recorded by a worker\"\n          operations:\n            - method: GET\n              name: list-time-blocks\n              description: \"List time blocks for a worker\"\n              call: \"workday-time-tracking.list-time-blocks\"\n              with:\n                workerId: \"rest.workerId\"\n                startDate: \"rest.startDate\"\n                endDate: \"rest.endDate\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-time-block\n              description: \"Create a new time block for a worker\"\n              call: \"workday-time-tracking.create-time-block\"\
  \n              with:\n                workerId: \"rest.workerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workers/{workerId}/time-blocks/{timeBlockId}\n          name: time-block\n          description: \"A specific time block\"\n          operations:\n            - method: GET\n              name: get-time-block\n              description: \"Get a specific time block\"\n              call: \"workday-time-tracking.get-time-block\"\n              with:\n                workerId: \"rest.workerId\"\n                timeBlockId: \"rest.timeBlockId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-time-block\n              description: \"Update a time block\"\n              call: \"workday-time-tracking.update-time-block\"\n              with:\n                workerId: \"rest.workerId\"\n               \
  \ timeBlockId: \"rest.timeBlockId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-time-block\n              description: \"Delete a time block\"\n              call: \"workday-time-tracking.delete-time-block\"\n              with:\n                workerId: \"rest.workerId\"\n                timeBlockId: \"rest.timeBlockId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workers/{workerId}/clock-events\n          name: clock-events\n          description: \"Time clock events for a worker\"\n          operations:\n            - method: GET\n              name: list-clock-events\n              description: \"List time clock events for a worker\"\n              call: \"workday-time-tracking.list-time-clock-events\"\n              with:\n                workerId: \"rest.workerId\"\n                startDate:\
  \ \"rest.startDate\"\n                endDate: \"rest.endDate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-clock-event\n              description: \"Record a clock-in or clock-out event\"\n              call: \"workday-time-tracking.create-time-clock-event\"\n              with:\n                workerId: \"rest.workerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workers/{workerId}/schedule\n          name: schedule\n          description: \"Work schedule for a worker\"\n          operations:\n            - method: GET\n              name: get-schedule\n              description: \"Get the work schedule for a worker\"\n              call: \"workday-time-tracking.get-work-schedule\"\n              with:\n                workerId: \"rest.workerId\"\n                asOfDate: \"rest.asOfDate\"\n   \
  \           outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: assign-schedule\n              description: \"Assign a work schedule to a worker\"\n              call: \"workday-time-tracking.assign-work-schedule\"\n              with:\n                workerId: \"rest.workerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workers/{workerId}/timesheets\n          name: timesheets\n          description: \"Timesheets for a worker\"\n          operations:\n            - method: GET\n              name: list-timesheets\n              description: \"List timesheets for a worker\"\n              call: \"workday-time-tracking.list-timesheets\"\n              with:\n                workerId: \"rest.workerId\"\n                startDate: \"rest.startDate\"\n                endDate: \"rest.endDate\"\n              outputParameters:\n     \
  \           - type: object\n                  mapping: \"$.\"\n        - path: /v1/workers/{workerId}/time-off\n          name: time-off\n          description: \"Time off requests for a worker\"\n          operations:\n            - method: GET\n              name: list-time-off\n              description: \"List time off for a worker\"\n              call: \"workday-absence-management.list-time-off\"\n              with:\n                workerId: \"rest.workerId\"\n                startDate: \"rest.startDate\"\n                endDate: \"rest.endDate\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: request-time-off\n              description: \"Request time off for a worker\"\n              call: \"workday-absence-management.request-time-off\"\n              with:\n                workerId: \"rest.workerId\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workers/{workerId}/time-off-balances\n          name: time-off-balances\n          description: \"Time off plan balances for a worker\"\n          operations:\n            - method: GET\n              name: list-time-off-balances\n              description: \"Get time off balances for a worker\"\n              call: \"workday-absence-management.list-time-off-balances\"\n              with:\n                workerId: \"rest.workerId\"\n                asOfDate: \"rest.asOfDate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workers/{workerId}/leaves\n          name: leaves\n          description: \"Leave of absence records for a worker\"\n          operations:\n            - method: GET\n              name: list-leaves\n              description: \"List leaves of absence for a worker\"\n              call: \"workday-absence-management.list-leaves-of-absence\"\
  \n              with:\n                workerId: \"rest.workerId\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: request-leave\n              description: \"Request a leave of absence\"\n              call: \"workday-absence-management.request-leave-of-absence\"\n              with:\n                workerId: \"rest.workerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: workforce-time-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted workforce time management in Workday.\"\n      tools:\n        - name: list-time-blocks\n          description: \"List time blocks recorded by a Workday worker in a date range\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call:\
  \ \"workday-time-tracking.list-time-blocks\"\n          with:\n            workerId: \"tools.workerId\"\n            startDate: \"tools.startDate\"\n            endDate: \"tools.endDate\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-time-block\n          description: \"Create a new time block entry for a worker\"\n          hints:\n            readOnly: false\n          call: \"workday-time-tracking.create-time-block\"\n          with:\n            workerId: \"tools.workerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-time-block\n          description: \"Get details of a specific time block\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"workday-time-tracking.get-time-block\"\n          with:\n            workerId: \"tools.workerId\"\n            timeBlockId: \"tools.timeBlockId\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-time-block\n          description: \"Update an existing time block\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"workday-time-tracking.update-time-block\"\n          with:\n            workerId: \"tools.workerId\"\n            timeBlockId: \"tools.timeBlockId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-time-block\n          description: \"Delete a reported time block\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"workday-time-tracking.delete-time-block\"\n          with:\n            workerId: \"tools.workerId\"\n            timeBlockId: \"tools.timeBlockId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-clock-events\n\
  \          description: \"List time clock events (punches) for a worker\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"workday-time-tracking.list-time-clock-events\"\n          with:\n            workerId: \"tools.workerId\"\n            startDate: \"tools.startDate\"\n            endDate: \"tools.endDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-clock-event\n          description: \"Record a clock-in or clock-out event from a time device\"\n          hints:\n            readOnly: false\n          call: \"workday-time-tracking.create-time-clock-event\"\n          with:\n            workerId: \"tools.workerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-work-schedule\n          description: \"Get the current work schedule assigned to a worker\"\n          hints:\n            readOnly: true\n           \
  \ openWorld: true\n          call: \"workday-time-tracking.get-work-schedule\"\n          with:\n            workerId: \"tools.workerId\"\n            asOfDate: \"tools.asOfDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: assign-work-schedule\n          description: \"Assign a work schedule to a worker\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"workday-time-tracking.assign-work-schedule\"\n          with:\n            workerId: \"tools.workerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-timesheets\n          description: \"List timesheets for a worker for a period\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"workday-time-tracking.list-timesheets\"\n          with:\n            workerId: \"tools.workerId\"\n            startDate: \"tools.startDate\"\n \
  \           endDate: \"tools.endDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-time-off\n          description: \"List time off requests for a worker\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"workday-absence-management.list-time-off\"\n          with:\n            workerId: \"tools.workerId\"\n            startDate: \"tools.startDate\"\n            endDate: \"tools.endDate\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: request-time-off\n          description: \"Submit a time off request for a worker\"\n          hints:\n            readOnly: false\n          call: \"workday-absence-management.request-time-off\"\n          with:\n            workerId: \"tools.workerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name:\
  \ list-time-off-balances\n          description: \"Get time off plan balances for a worker\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"workday-absence-management.list-time-off-balances\"\n          with:\n            workerId: \"tools.workerId\"\n            asOfDate: \"tools.asOfDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-leaves-of-absence\n          description: \"List leave of absence records for a worker\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"workday-absence-management.list-leaves-of-absence\"\n          with:\n            workerId: \"tools.workerId\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: request-leave-of-absence\n          description: \"Submit a leave of absence request for a worker\"\n          hints:\n\
  \            readOnly: false\n          call: \"workday-absence-management.request-leave-of-absence\"\n          with:\n            workerId: \"tools.workerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-accrual-overrides\n          description: \"List accrual balance overrides for a worker\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"workday-absence-management.list-accrual-overrides\"\n          with:\n            workerId: \"tools.workerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/workday-tracking-system/refs/heads/main/capabilities/workforce-time-management.yaml
tags:
- Workday
- Time Tracking
- Absence Management
- Workforce Management
- HR
- Payroll
tools:
- description: List time blocks recorded by a Workday worker in a date range
  hints:
    openWorld: true
    readOnly: true
  name: list-time-blocks
- description: Create a new time block entry for a worker
  hints:
    readOnly: false
  name: create-time-block
- description: Get details of a specific time block
  hints:
    openWorld: true
    readOnly: true
  name: get-time-block
- description: Update an existing time block
  hints:
    idempotent: true
    readOnly: false
  name: update-time-block
- description: Delete a reported time block
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-time-block
- description: List time clock events (punches) for a worker
  hints:
    openWorld: true
    readOnly: true
  name: list-clock-events
- description: Record a clock-in or clock-out event from a time device
  hints:
    readOnly: false
  name: create-clock-event
- description: Get the current work schedule assigned to a worker
  hints:
    openWorld: true
    readOnly: true
  name: get-work-schedule
- description: Assign a work schedule to a worker
  hints:
    idempotent: true
    readOnly: false
  name: assign-work-schedule
- description: List timesheets for a worker for a period
  hints:
    openWorld: true
    readOnly: true
  name: list-timesheets
- description: List time off requests for a worker
  hints:
    openWorld: true
    readOnly: true
  name: list-time-off
- description: Submit a time off request for a worker
  hints:
    readOnly: false
  name: request-time-off
- description: Get time off plan balances for a worker
  hints:
    openWorld: true
    readOnly: true
  name: list-time-off-balances
- description: List leave of absence records for a worker
  hints:
    openWorld: true
    readOnly: true
  name: list-leaves-of-absence
- description: Submit a leave of absence request for a worker
  hints:
    readOnly: false
  name: request-leave-of-absence
- description: List accrual balance overrides for a worker
  hints:
    openWorld: true
    readOnly: true
  name: list-accrual-overrides
---
