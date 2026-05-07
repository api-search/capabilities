---
categories: []
consumed_apis: []
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
- list leaves of absence for a worker
- get the current work schedule assigned to a worker
- work schedule for a worker
- get the work schedule for a worker
- assign schedule
- delete a reported time block
- request leave
- list clock events
- time blocks recorded by a worker
- list time off requests for a worker
- time tracking
- list time clock events for a worker
- request time off
- delete a time block
- delete time block
- list leave of absence records for a worker
- list accrual balance overrides for a worker
- workday
- assign a work schedule to a worker
- attendance
- request leave of absence
- timesheets
- list time blocks recorded by a workday worker in a date range
- list time blocks
- hcm
- get time off plan balances for a worker
- list time blocks for a worker
- hr
- update time block
- a specific time block
- create clock event
- create time block
- payroll
- list time off
- update a time block
- request time off for a worker
- record a clock-in or clock-out event
- submit a time off request for a worker
- list leaves
- list time off for a worker
- submit a leave of absence request for a worker
- request a leave of absence
- enterprise
- list timesheets for a worker
- time off requests for a worker
- assign work schedule
- list time off balances
- absence management
- get time off balances for a worker
- get a specific time block
- list timesheets for a worker for a period
- list accrual overrides
- get work schedule
- time clock events for a worker
- workforce management
- time off plan balances for a worker
- get schedule
- get details of a specific time block
- create a new time block entry for a worker
- record a clock-in or clock-out event from a time device
- scheduling
- list leaves of absence
- human capital management
- list timesheets
- update an existing time block
- timesheets for a worker
- leave of absence records for a worker
- get time block
- list time clock events (punches) for a worker
- create a new time block for a worker
slug: workforce-time-management
source_filename: workforce-time-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Workday Workforce Time Management\n  description: Unified capability for managing the complete employee time lifecycle in Workday, combining Time Tracking and\n    Absence Management APIs. Used by HR managers, payroll teams, and workforce administrators to track attendance, process\n    time off, manage schedules, and ensure accurate time records for payroll processing.\n  tags:\n  - Workday\n  - Time Tracking\n  - Absence Management\n  - Workforce Management\n  - HR\n  - Payroll\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WORKDAY_BEARER_TOKEN: WORKDAY_BEARER_TOKEN\n    WORKDAY_TENANT: WORKDAY_TENANT\ncapability:\n  consumes:\n  - type: http\n    namespace: workday-time-tracking\n    baseUri: https://{{WORKDAY_TENANT}}.workday.com/api/time-tracking/v1\n    description: Workday Time Tracking REST API for managing employee time data\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_BEARER_TOKEN}}'\n\
  \    resources:\n    - name: time-blocks\n      path: /workers/{workerId}/timeBlocks\n      description: Time blocks for a specific worker\n      operations:\n      - name: list-time-blocks\n        method: GET\n        description: List time blocks for a worker in a date range\n        inputParameters:\n        - name: workerId\n          in: path\n          type: string\n          required: true\n          description: The Workday ID of the worker\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Start date (YYYY-MM-DD)\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: End date (YYYY-MM-DD)\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: create-time-block\n        method: POST\n        description: Create a new reported time block for a worker\n        inputParameters:\n        - name: workerId\n          in: path\n          type: string\n          required: true\n          description: The Workday ID of the worker\n        body:\n          type: json\n          data:\n            date: '{{tools.date}}'\n            hours: '{{tools.hours}}'\n            type: '{{tools.type}}'\n            startTime: '{{tools.startTime}}'\n            endTime: '{{tools.endTime}}'\n            comment: '{{tools.comment}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: time-block-by-id\n      path: /workers/{workerId}/timeBlocks/{timeBlockId}\n      description: A specific time block\n      operations:\n      - name: get-time-block\n        method: GET\n        description: Get a specific time block by ID\n        inputParameters:\n\
  \        - name: workerId\n          in: path\n          type: string\n          required: true\n          description: The Workday ID of the worker\n        - name: timeBlockId\n          in: path\n          type: string\n          required: true\n          description: The Workday ID of the time block\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-time-block\n        method: PUT\n        description: Update an existing time block\n        inputParameters:\n        - name: workerId\n          in: path\n          type: string\n          required: true\n          description: The Workday ID of the worker\n        - name: timeBlockId\n          in: path\n          type: string\n          required: true\n          description: The time block ID\n        body:\n          type: json\n          data:\n            date: '{{tools.date}}'\n            hours: '{{tools.hours}}'\n            type:\
  \ '{{tools.type}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-time-block\n        method: DELETE\n        description: Delete a reported time block\n        inputParameters:\n        - name: workerId\n          in: path\n          type: string\n          required: true\n          description: The Workday ID of the worker\n        - name: timeBlockId\n          in: path\n          type: string\n          required: true\n          description: The time block ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: time-clock-events\n      path: /workers/{workerId}/timeClockEvents\n      description: Time clock events for a worker\n      operations:\n      - name: list-time-clock-events\n        method: GET\n        description: List time clock events for a worker\n        inputParameters:\n        -\
  \ name: workerId\n          in: path\n          type: string\n          required: true\n          description: Worker ID\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Start date filter\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: End date filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-time-clock-event\n        method: POST\n        description: Record a time clock event (punch-in or punch-out)\n        inputParameters:\n        - name: workerId\n          in: path\n          type: string\n          required: true\n          description: Worker ID\n        body:\n          type: json\n          data:\n            eventType: '{{tools.eventType}}'\n            eventDateTime: '{{tools.eventDateTime}}'\n            deviceId: '{{tools.deviceId}}'\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: work-schedule\n      path: /workers/{workerId}/workSchedule\n      description: Work schedule for a worker\n      operations:\n      - name: get-work-schedule\n        method: GET\n        description: Get the work schedule for a worker\n        inputParameters:\n        - name: workerId\n          in: path\n          type: string\n          required: true\n          description: Worker ID\n        - name: asOfDate\n          in: query\n          type: string\n          required: false\n          description: Effective date for the schedule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: assign-work-schedule\n        method: PUT\n        description: Assign a work schedule to a worker\n        inputParameters:\n        - name: workerId\n          in: path\n\
  \          type: string\n          required: true\n          description: Worker ID\n        body:\n          type: json\n          data:\n            scheduleId: '{{tools.scheduleId}}'\n            effectiveDate: '{{tools.effectiveDate}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: timesheets\n      path: /workers/{workerId}/timesheets\n      description: Timesheets for a worker\n      operations:\n      - name: list-timesheets\n        method: GET\n        description: List timesheets for a worker\n        inputParameters:\n        - name: workerId\n          in: path\n          type: string\n          required: true\n          description: Worker ID\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Start date filter\n        - name: endDate\n          in: query\n          type: string\n          required: false\n   \
  \       description: End date filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: workday-absence-management\n    baseUri: https://{{WORKDAY_TENANT}}.workday.com/api/absence-management/v1\n    description: Workday Absence Management REST API\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_BEARER_TOKEN}}'\n    resources:\n    - name: time-off\n      path: /workers/{workerId}/timeOff\n      description: Time off entries for a worker\n      operations:\n      - name: list-time-off\n        method: GET\n        description: List time off entries for a worker\n        inputParameters:\n        - name: workerId\n          in: path\n          type: string\n          required: true\n          description: Worker ID\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Start date filter\n        -\
  \ name: endDate\n          in: query\n          type: string\n          required: false\n          description: End date filter\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Status filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: request-time-off\n        method: POST\n        description: Submit a time off request for a worker\n        inputParameters:\n        - name: workerId\n          in: path\n          type: string\n          required: true\n          description: Worker ID\n        body:\n          type: json\n          data:\n            timeOffType: '{{tools.timeOffType}}'\n            startDate: '{{tools.startDate}}'\n            endDate: '{{tools.endDate}}'\n            comment: '{{tools.comment}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: time-off-balances\n      path: /workers/{workerId}/timeOffBalances\n      description: Time off plan balances for a worker\n      operations:\n      - name: list-time-off-balances\n        method: GET\n        description: Get time off plan balances for a worker\n        inputParameters:\n        - name: workerId\n          in: path\n          type: string\n          required: true\n          description: Worker ID\n        - name: asOfDate\n          in: query\n          type: string\n          required: false\n          description: Balance as-of date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: leave-of-absence\n      path: /workers/{workerId}/leaveOfAbsence\n      description: Leave of absence records for a worker\n      operations:\n      - name: list-leaves-of-absence\n        method: GET\n        description: List leave of absence records for a worker\n\
  \        inputParameters:\n        - name: workerId\n          in: path\n          type: string\n          required: true\n          description: Worker ID\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Status filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: request-leave-of-absence\n        method: POST\n        description: Submit a leave of absence request\n        inputParameters:\n        - name: workerId\n          in: path\n          type: string\n          required: true\n          description: Worker ID\n        body:\n          type: json\n          data:\n            leaveType: '{{tools.leaveType}}'\n            startDate: '{{tools.startDate}}'\n            expectedEndDate: '{{tools.expectedEndDate}}'\n            reason: '{{tools.reason}}'\n        outputRawFormat: json\n        outputParameters:\n     \
  \   - name: result\n          type: object\n          value: $.\n    - name: accrual-overrides\n      path: /workers/{workerId}/accrualOverrides\n      description: Accrual overrides for a worker\n      operations:\n      - name: list-accrual-overrides\n        method: GET\n        description: List accrual overrides for a worker\n        inputParameters:\n        - name: workerId\n          in: path\n          type: string\n          required: true\n          description: Worker ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: workforce-time-management-api\n    description: Unified REST API for complete workforce time management.\n    resources:\n    - path: /v1/workers/{workerId}/time-blocks\n      name: time-blocks\n      description: Time blocks recorded by a worker\n      operations:\n      - method: GET\n        name: list-time-blocks\n    \
  \    description: List time blocks for a worker\n        call: workday-time-tracking.list-time-blocks\n        with:\n          workerId: rest.workerId\n          startDate: rest.startDate\n          endDate: rest.endDate\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-time-block\n        description: Create a new time block for a worker\n        call: workday-time-tracking.create-time-block\n        with:\n          workerId: rest.workerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workers/{workerId}/time-blocks/{timeBlockId}\n      name: time-block\n      description: A specific time block\n      operations:\n      - method: GET\n        name: get-time-block\n        description: Get a specific time block\n        call: workday-time-tracking.get-time-block\n        with:\n          workerId: rest.workerId\n          timeBlockId: rest.timeBlockId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-time-block\n        description: Update a time block\n        call: workday-time-tracking.update-time-block\n        with:\n          workerId: rest.workerId\n          timeBlockId: rest.timeBlockId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-time-block\n        description: Delete a time block\n        call: workday-time-tracking.delete-time-block\n        with:\n          workerId: rest.workerId\n          timeBlockId: rest.timeBlockId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workers/{workerId}/clock-events\n      name: clock-events\n      description: Time clock events for a worker\n      operations:\n      - method: GET\n        name: list-clock-events\n        description: List time clock events for a worker\n        call: workday-time-tracking.list-time-clock-events\n\
  \        with:\n          workerId: rest.workerId\n          startDate: rest.startDate\n          endDate: rest.endDate\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-clock-event\n        description: Record a clock-in or clock-out event\n        call: workday-time-tracking.create-time-clock-event\n        with:\n          workerId: rest.workerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workers/{workerId}/schedule\n      name: schedule\n      description: Work schedule for a worker\n      operations:\n      - method: GET\n        name: get-schedule\n        description: Get the work schedule for a worker\n        call: workday-time-tracking.get-work-schedule\n        with:\n          workerId: rest.workerId\n          asOfDate: rest.asOfDate\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: assign-schedule\n\
  \        description: Assign a work schedule to a worker\n        call: workday-time-tracking.assign-work-schedule\n        with:\n          workerId: rest.workerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workers/{workerId}/timesheets\n      name: timesheets\n      description: Timesheets for a worker\n      operations:\n      - method: GET\n        name: list-timesheets\n        description: List timesheets for a worker\n        call: workday-time-tracking.list-timesheets\n        with:\n          workerId: rest.workerId\n          startDate: rest.startDate\n          endDate: rest.endDate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workers/{workerId}/time-off\n      name: time-off\n      description: Time off requests for a worker\n      operations:\n      - method: GET\n        name: list-time-off\n        description: List time off for a worker\n        call: workday-absence-management.list-time-off\n\
  \        with:\n          workerId: rest.workerId\n          startDate: rest.startDate\n          endDate: rest.endDate\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: request-time-off\n        description: Request time off for a worker\n        call: workday-absence-management.request-time-off\n        with:\n          workerId: rest.workerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workers/{workerId}/time-off-balances\n      name: time-off-balances\n      description: Time off plan balances for a worker\n      operations:\n      - method: GET\n        name: list-time-off-balances\n        description: Get time off balances for a worker\n        call: workday-absence-management.list-time-off-balances\n        with:\n          workerId: rest.workerId\n          asOfDate: rest.asOfDate\n        outputParameters:\n        - type: object\n       \
  \   mapping: $.\n    - path: /v1/workers/{workerId}/leaves\n      name: leaves\n      description: Leave of absence records for a worker\n      operations:\n      - method: GET\n        name: list-leaves\n        description: List leaves of absence for a worker\n        call: workday-absence-management.list-leaves-of-absence\n        with:\n          workerId: rest.workerId\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: request-leave\n        description: Request a leave of absence\n        call: workday-absence-management.request-leave-of-absence\n        with:\n          workerId: rest.workerId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: workforce-time-management-mcp\n    transport: http\n    description: MCP server for AI-assisted workforce time management in Workday.\n    tools:\n    - name: list-time-blocks\n  \
  \    description: List time blocks recorded by a Workday worker in a date range\n      hints:\n        readOnly: true\n        openWorld: true\n      call: workday-time-tracking.list-time-blocks\n      with:\n        workerId: tools.workerId\n        startDate: tools.startDate\n        endDate: tools.endDate\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-time-block\n      description: Create a new time block entry for a worker\n      hints:\n        readOnly: false\n      call: workday-time-tracking.create-time-block\n      with:\n        workerId: tools.workerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-time-block\n      description: Get details of a specific time block\n      hints:\n        readOnly: true\n        openWorld: true\n      call: workday-time-tracking.get-time-block\n      with:\n        workerId: tools.workerId\n        timeBlockId: tools.timeBlockId\n    \
  \  outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-time-block\n      description: Update an existing time block\n      hints:\n        readOnly: false\n        idempotent: true\n      call: workday-time-tracking.update-time-block\n      with:\n        workerId: tools.workerId\n        timeBlockId: tools.timeBlockId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-time-block\n      description: Delete a reported time block\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: workday-time-tracking.delete-time-block\n      with:\n        workerId: tools.workerId\n        timeBlockId: tools.timeBlockId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-clock-events\n      description: List time clock events (punches) for a worker\n      hints:\n        readOnly: true\n        openWorld: true\n      call: workday-time-tracking.list-time-clock-events\n\
  \      with:\n        workerId: tools.workerId\n        startDate: tools.startDate\n        endDate: tools.endDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-clock-event\n      description: Record a clock-in or clock-out event from a time device\n      hints:\n        readOnly: false\n      call: workday-time-tracking.create-time-clock-event\n      with:\n        workerId: tools.workerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-work-schedule\n      description: Get the current work schedule assigned to a worker\n      hints:\n        readOnly: true\n        openWorld: true\n      call: workday-time-tracking.get-work-schedule\n      with:\n        workerId: tools.workerId\n        asOfDate: tools.asOfDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: assign-work-schedule\n      description: Assign a work schedule to a worker\n      hints:\n        readOnly: false\n\
  \        idempotent: true\n      call: workday-time-tracking.assign-work-schedule\n      with:\n        workerId: tools.workerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-timesheets\n      description: List timesheets for a worker for a period\n      hints:\n        readOnly: true\n        openWorld: true\n      call: workday-time-tracking.list-timesheets\n      with:\n        workerId: tools.workerId\n        startDate: tools.startDate\n        endDate: tools.endDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-time-off\n      description: List time off requests for a worker\n      hints:\n        readOnly: true\n        openWorld: true\n      call: workday-absence-management.list-time-off\n      with:\n        workerId: tools.workerId\n        startDate: tools.startDate\n        endDate: tools.endDate\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: request-time-off\n      description: Submit a time off request for a worker\n      hints:\n        readOnly: false\n      call: workday-absence-management.request-time-off\n      with:\n        workerId: tools.workerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-time-off-balances\n      description: Get time off plan balances for a worker\n      hints:\n        readOnly: true\n        openWorld: true\n      call: workday-absence-management.list-time-off-balances\n      with:\n        workerId: tools.workerId\n        asOfDate: tools.asOfDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-leaves-of-absence\n      description: List leave of absence records for a worker\n      hints:\n        readOnly: true\n        openWorld: true\n      call: workday-absence-management.list-leaves-of-absence\n      with:\n        workerId: tools.workerId\n        status: tools.status\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: request-leave-of-absence\n      description: Submit a leave of absence request for a worker\n      hints:\n        readOnly: false\n      call: workday-absence-management.request-leave-of-absence\n      with:\n        workerId: tools.workerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-accrual-overrides\n      description: List accrual balance overrides for a worker\n      hints:\n        readOnly: true\n        openWorld: true\n      call: workday-absence-management.list-accrual-overrides\n      with:\n        workerId: tools.workerId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
