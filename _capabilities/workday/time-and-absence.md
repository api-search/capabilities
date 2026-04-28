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
- absence request time off
- submit a time entry request
- cloud computing
- absence request leave
- create a time clock event
- list time-off balances
- get eligible absence types for a worker
- list timesheets
- list balances
- time tracking
- time create clock event
- time-off balances
- absence list time off entries
- time list entries
- hcm
- absence get balances
- time request entry
- workday
- time list clock events
- list time-off entries
- saas
- absence get eligible types
- enterprise software
- submit a leave of absence request
- get time-off balances for a worker
- list leaves of absence
- list time clock events
- financial management
- absence management
- absence list leaves
- list time entries
- time entries
- time list timesheets
- submit a time-off request
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
