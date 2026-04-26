---
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
- submit a time-off request
- list time entries
- list balances
- time request entry
- absence management
- time tracking
- submit a leave of absence request
- time entries
- time-off balances
- absence get eligible types
- time list timesheets
- time create clock event
- create a time clock event
- submit a time entry request
- absence request time off
- list time-off entries
- absence get balances
- cloud computing
- time list clock events
- financial management
- get time-off balances for a worker
- time list entries
- get eligible absence types for a worker
- list leaves of absence
- absence list time off entries
- saas
- list timesheets
- list time-off balances
- workday
- hcm
- list time clock events
- enterprise software
- absence list leaves
- absence request leave
slug: time-and-absence
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
