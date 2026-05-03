---
categories:
- payroll-hr
consumed_apis:
- workday-time-tracking
- workday-absence
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
- list time clock events
- submit a time-off request
- absence get balances
- time list clock events
- create a time clock event
- workday
- get time-off balances for a worker
- saas
- time list timesheets
- hcm
- list time-off balances
- absence management
- list time entries
- time request entry
- enterprise software
- absence request leave
- list balances
- absence request time off
- time tracking
- submit a time entry request
- submit a leave of absence request
- time entries
- financial management
- absence list leaves
- list leaves of absence
- time list entries
- absence get eligible types
- list time-off entries
- time-off balances
- time create clock event
- list timesheets
- get eligible absence types for a worker
- cloud computing
- absence list time off entries
slug: time-and-absence
source_filename: time-and-absence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Workday Time and Absence\"\n  description: \"Unified time and absence management combining Time Tracking and Absence Management APIs for HR operations to manage timesheets, time-off requests, and leave balances.\"\n  tags:\n    - Workday\n    - Time Tracking\n    - Absence Management\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      WORKDAY_OAUTH_TOKEN: WORKDAY_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: workday-time-tracking\n      location: ./shared/time-tracking.yaml\n    - import: workday-absence\n      location: ./shared/absence-management.yaml\n\n  exposes:\n    - type: rest\n      port: 8083\n      namespace: time-absence-api\n      description: \"Unified REST API for time and absence management.\"\n      resources:\n        - path: /v1/time-entries\n          name: time-entries\n          description: \"Time entries\"\n          operations:\n            - method:\
  \ GET\n              name: list-time-entries\n              description: \"List time entries\"\n              call: \"workday-time-tracking.get-time-entries\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/time-off-balances\n          name: balances\n          description: \"Time-off balances\"\n          operations:\n            - method: GET\n              name: list-balances\n              description: \"List time-off balances\"\n              call: \"workday-absence.get-time-off-balances\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9083\n      namespace: time-absence-mcp\n      transport: http\n      description: \"MCP server for AI-assisted time and absence management.\"\n      tools:\n        - name: time-list-clock-events\n          description: \"List time clock events\"\n          hints:\n            readOnly: true\n\
  \          call: \"workday-time-tracking.get-time-clock-events\"\n          with:\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: time-create-clock-event\n          description: \"Create a time clock event\"\n          hints:\n            readOnly: false\n          call: \"workday-time-tracking.create-time-clock-event\"\n          with:\n            worker: \"tools.worker\"\n            type: \"tools.type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: time-list-entries\n          description: \"List time entries\"\n          hints:\n            readOnly: true\n          call: \"workday-time-tracking.get-time-entries\"\n          with:\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: time-list-timesheets\n          description: \"List timesheets\"\
  \n          hints:\n            readOnly: true\n          call: \"workday-time-tracking.get-timesheets\"\n          with:\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: time-request-entry\n          description: \"Submit a time entry request\"\n          hints:\n            readOnly: false\n          call: \"workday-time-tracking.request-time-entry\"\n          with:\n            worker: \"tools.worker\"\n            hours: \"tools.hours\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: absence-get-eligible-types\n          description: \"Get eligible absence types for a worker\"\n          hints:\n            readOnly: true\n          call: \"workday-absence.get-eligible-absence-types\"\n          with:\n            worker: \"tools.worker\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n       \
  \ - name: absence-request-time-off\n          description: \"Submit a time-off request\"\n          hints:\n            readOnly: false\n          call: \"workday-absence.request-time-off\"\n          with:\n            worker: \"tools.worker\"\n            absenceType: \"tools.absenceType\"\n            startDate: \"tools.startDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: absence-list-time-off-entries\n          description: \"List time-off entries\"\n          hints:\n            readOnly: true\n          call: \"workday-absence.get-time-off-entries\"\n          with:\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: absence-get-balances\n          description: \"Get time-off balances for a worker\"\n          hints:\n            readOnly: true\n          call: \"workday-absence.get-time-off-balances\"\n          with:\n        \
  \    worker: \"tools.worker\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: absence-list-leaves\n          description: \"List leaves of absence\"\n          hints:\n            readOnly: true\n          call: \"workday-absence.get-leaves-of-absence\"\n          with:\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: absence-request-leave\n          description: \"Submit a leave of absence request\"\n          hints:\n            readOnly: false\n          call: \"workday-absence.request-leave-of-absence\"\n          with:\n            worker: \"tools.worker\"\n            leaveType: \"tools.leaveType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
