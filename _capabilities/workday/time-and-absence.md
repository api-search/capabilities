---
categories:
- payroll-hr
consumed_apis: []
description: Unified time and absence management combining Time Tracking and Absence Management APIs for HR operations to manage timesheets, time-off requests, and leave balances.
layout: capability
name: Workday Time and Absence
operations:
- description: List time entries
  method: GET
  name: list-time-entries
  path: /v1/time-entries
- description: List time-off balances
  method: GET
  name: list-balances
  path: /v1/time-off-balances
personas: []
provider_name: Workday
provider_slug: workday
search_terms:
- submit a time entry request
- list time clock events
- absence get balances
- enterprise software
- list balances
- time tracking
- get eligible absence types for a worker
- time list clock events
- workday
- time list timesheets
- saas
- hcm
- time request entry
- submit a leave of absence request
- cloud computing
- absence request time off
- financial management
- list time-off balances
- time entries
- absence get eligible types
- time-off balances
- absence management
- absence list leaves
- create a time clock event
- list time entries
- submit a time-off request
- time create clock event
- absence request leave
- list time-off entries
- list leaves of absence
- time list entries
- list timesheets
- absence list time off entries
- get time-off balances for a worker
slug: time-and-absence
source_filename: time-and-absence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Workday Time and Absence\n  description: Unified time and absence management combining Time Tracking and Absence Management APIs for HR operations to\n    manage timesheets, time-off requests, and leave balances.\n  tags:\n  - Workday\n  - Time Tracking\n  - Absence Management\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WORKDAY_OAUTH_TOKEN: WORKDAY_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: workday-time-tracking\n    baseUri: https://wd2-impl-services1.workday.com/ccx/api/v1/{tenant}/timeTracking\n    description: Workday Time Tracking REST API.\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_OAUTH_TOKEN}}'\n    resources:\n    - name: time-tracking\n      path: /\n      description: Time tracking operations\n      operations:\n      - name: get-time-clock-events\n        method: GET\n        description: Returns time clock events for workers.\n\
  \        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-time-clock-event\n        method: POST\n        description: Creates a time clock event.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            worker: '{{tools.worker}}'\n            type: '{{tools.type}}'\n      - name: get-time-entries\n        method: GET\n        description: Returns time entries.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: get-timesheets\n        method: GET\n        description: Returns timesheets.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: request-time-entry\n        method: POST\n        description: Submits a time entry request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            worker: '{{tools.worker}}'\n            hours: '{{tools.hours}}'\n  - type: http\n    namespace: workday-absence\n    baseUri: https://wd2-impl-services1.workday.com/ccx/api/v1/{tenant}/absenceManagement\n    description: Workday Absence Management REST API.\n    authentication:\n\
  \      type: bearer\n      token: '{{WORKDAY_OAUTH_TOKEN}}'\n    resources:\n    - name: absence\n      path: /\n      description: Absence management operations\n      operations:\n      - name: get-eligible-absence-types\n        method: GET\n        description: Returns eligible absence types for a worker.\n        inputParameters:\n        - name: worker\n          in: query\n          type: string\n          required: true\n          description: Worker ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: request-time-off\n        method: POST\n        description: Submits a time-off request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            worker: '{{tools.worker}}'\n            absenceType: '{{tools.absenceType}}'\n            startDate: '{{tools.startDate}}'\n\
  \      - name: get-time-off-entries\n        method: GET\n        description: Returns time-off entries.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-time-off-balances\n        method: GET\n        description: Returns time-off balances for a worker.\n        inputParameters:\n        - name: worker\n          in: query\n          type: string\n          required: true\n          description: Worker ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-leaves-of-absence\n        method: GET\n        description: Returns leaves of absence.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n\
  \          required: false\n          description: Maximum results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: request-leave-of-absence\n        method: POST\n        description: Submits a leave of absence request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            worker: '{{tools.worker}}'\n            leaveType: '{{tools.leaveType}}'\n  exposes:\n  - type: rest\n    port: 8083\n    namespace: time-absence-api\n    description: Unified REST API for time and absence management.\n    resources:\n    - path: /v1/time-entries\n      name: time-entries\n      description: Time entries\n      operations:\n      - method: GET\n        name: list-time-entries\n        description: List time entries\n        call: workday-time-tracking.get-time-entries\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/time-off-balances\n      name: balances\n      description: Time-off balances\n      operations:\n      - method: GET\n        name: list-balances\n        description: List time-off balances\n        call: workday-absence.get-time-off-balances\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9083\n    namespace: time-absence-mcp\n    transport: http\n    description: MCP server for AI-assisted time and absence management.\n    tools:\n    - name: time-list-clock-events\n      description: List time clock events\n      hints:\n        readOnly: true\n      call: workday-time-tracking.get-time-clock-events\n      with:\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: time-create-clock-event\n      description: Create a time clock event\n      hints:\n        readOnly: false\n      call: workday-time-tracking.create-time-clock-event\n\
  \      with:\n        worker: tools.worker\n        type: tools.type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: time-list-entries\n      description: List time entries\n      hints:\n        readOnly: true\n      call: workday-time-tracking.get-time-entries\n      with:\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: time-list-timesheets\n      description: List timesheets\n      hints:\n        readOnly: true\n      call: workday-time-tracking.get-timesheets\n      with:\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: time-request-entry\n      description: Submit a time entry request\n      hints:\n        readOnly: false\n      call: workday-time-tracking.request-time-entry\n      with:\n        worker: tools.worker\n        hours: tools.hours\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: absence-get-eligible-types\n\
  \      description: Get eligible absence types for a worker\n      hints:\n        readOnly: true\n      call: workday-absence.get-eligible-absence-types\n      with:\n        worker: tools.worker\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: absence-request-time-off\n      description: Submit a time-off request\n      hints:\n        readOnly: false\n      call: workday-absence.request-time-off\n      with:\n        worker: tools.worker\n        absenceType: tools.absenceType\n        startDate: tools.startDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: absence-list-time-off-entries\n      description: List time-off entries\n      hints:\n        readOnly: true\n      call: workday-absence.get-time-off-entries\n      with:\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: absence-get-balances\n      description: Get time-off balances for a worker\n      hints:\n\
  \        readOnly: true\n      call: workday-absence.get-time-off-balances\n      with:\n        worker: tools.worker\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: absence-list-leaves\n      description: List leaves of absence\n      hints:\n        readOnly: true\n      call: workday-absence.get-leaves-of-absence\n      with:\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: absence-request-leave\n      description: Submit a leave of absence request\n      hints:\n        readOnly: false\n      call: workday-absence.request-leave-of-absence\n      with:\n        worker: tools.worker\n        leaveType: tools.leaveType\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/workday/refs/heads/main/capabilities/time-and-absence.yaml
tags:
- Workday
- Time Tracking
- Absence Management
tools:
- description: List time clock events
  hints:
    readOnly: true
  name: time-list-clock-events
- description: Create a time clock event
  hints:
    readOnly: false
  name: time-create-clock-event
- description: List time entries
  hints:
    readOnly: true
  name: time-list-entries
- description: List timesheets
  hints:
    readOnly: true
  name: time-list-timesheets
- description: Submit a time entry request
  hints:
    readOnly: false
  name: time-request-entry
- description: Get eligible absence types for a worker
  hints:
    readOnly: true
  name: absence-get-eligible-types
- description: Submit a time-off request
  hints:
    readOnly: false
  name: absence-request-time-off
- description: List time-off entries
  hints:
    readOnly: true
  name: absence-list-time-off-entries
- description: Get time-off balances for a worker
  hints:
    readOnly: true
  name: absence-get-balances
- description: List leaves of absence
  hints:
    readOnly: true
  name: absence-list-leaves
- description: Submit a leave of absence request
  hints:
    readOnly: false
  name: absence-request-leave
---
