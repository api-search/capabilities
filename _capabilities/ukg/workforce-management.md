---
categories: []
consumed_apis: []
description: Workforce management workflow combining timekeeping, scheduling, and accrual capabilities for hourly and salaried employees.
layout: capability
name: UKG Workforce Management
operations:
- description: List WFM employees
  method: GET
  name: list-employees
  path: /v1/employees
- description: Get employee timecards
  method: GET
  name: get-timecards
  path: /v1/employees/{employeeId}/timecards
- description: Get employee accruals
  method: GET
  name: get-accruals
  path: /v1/employees/{employeeId}/accruals
personas: []
provider_name: UKG
provider_slug: ukg
search_terms:
- vacation, sick, and pto accrual policy management
- clock punches, timecards, and time approval workflows
- get accruals
- employee accrual balances
- list all wfm employee records
- list employees
- get timecards
- list schedules
- get employee pay statement history
- hcm
- hr
- list pay statements
- manages benefits enrollment, plan administration, and compliance
- get employee timecards
- scheduling
- ukg
- create punch
- timekeeping
- core hr functions including employee records, hiring, and organizational management
- pay processing, compensation management, and pay statement history
- benefits
- payroll
- workforce schedules, shift management, and coverage planning
- list wfm employees
- get employee punches
- employee records
- human capital management
- manages employee schedules, timecards, and attendance
- get hcm employee
- employee records, benefits, payroll, and organizational management
- time and attendance
- get clock punch records for an employee
- employee timecards
- list workforce schedules for a location and date range
- processes payroll, manages pay rates, and reviews pay statements
- creates and manages workforce schedules and shift assignments
- workforce management
- submit a clock punch for an employee
- get hcm employee record with full demographic and job data
- views own records, timecards, benefits, and pay statements
- get employee shifts
- get vacation, sick, and pto accrual balances for an employee
- benefits enrollment, elections, and plan administration
- get timecard records for an employee within a date range
- timekeeping, scheduling, and accrual management for hourly and salaried employees
- get employee accruals
- manages employee records, org structure, and hr transactions
- accruals
- get scheduled shifts for a specific employee
slug: workforce-management
source_filename: workforce-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"UKG Workforce Management\"\n  description: \"Workforce management workflow combining timekeeping, scheduling, and accrual capabilities for hourly and salaried employees.\"\n  tags:\n    - UKG\n    - Workforce Management\n    - Timekeeping\n    - Scheduling\n    - Accruals\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n  personas:\n    - Workforce Manager\n    - Payroll Administrator\n    - Scheduler\n    - Employee\n\nimports:\n  - url: shared/pro-wfm.yaml\n    namespace: pro-wfm\n  - url: shared/pro-hcm.yaml\n    namespace: pro-hcm\n\ncapability:\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: workforce-management-api\n      resources:\n        - path: /v1/employees\n          name: employees\n          description: \"Employee records\"\n          operations:\n            - method: GET\n              name: list-employees\n              description: \"List WFM employees\"\n              call: \"pro-wfm.list-wfm-employees\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/employees/{employeeId}/timecards\n          name: timecards\n          description: \"Employee timecards\"\n          operations:\n            - method: GET\n              name: get-timecards\n              description: \"Get employee timecards\"\n              call: \"pro-wfm.get-employee-timecards\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/employees/{employeeId}/accruals\n          name: accruals\n          description: \"Employee accrual balances\"\n          operations:\n            - method: GET\n              name: get-accruals\n              description: \"Get employee accruals\"\n              call: \"pro-wfm.get-employee-accruals\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n    - type: mcp\n      port: 9080\n      namespace:\
  \ workforce-management-mcp\n      transport: http\n      tools:\n        - name: list-wfm-employees\n          description: \"List all WFM employee records\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"pro-wfm.list-wfm-employees\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-employee-timecards\n          description: \"Get timecard records for an employee within a date range\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"pro-wfm.get-employee-timecards\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-employee-punches\n          description: \"Get clock punch records for an employee\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"pro-wfm.get-employee-punches\"\n          outputParameters:\n            - type: object\n \
  \             mapping: \"$.\"\n        - name: create-punch\n          description: \"Submit a clock punch for an employee\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"pro-wfm.create-punch\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-employee-accruals\n          description: \"Get vacation, sick, and PTO accrual balances for an employee\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"pro-wfm.get-employee-accruals\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-schedules\n          description: \"List workforce schedules for a location and date range\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"pro-wfm.list-schedules\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n  \
  \      - name: get-employee-shifts\n          description: \"Get scheduled shifts for a specific employee\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"pro-wfm.get-employee-shifts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-hcm-employee\n          description: \"Get HCM employee record with full demographic and job data\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"pro-hcm.get-employee\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-pay-statements\n          description: \"Get employee pay statement history\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"pro-hcm.list-pay-statements\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ukg/refs/heads/main/capabilities/workforce-management.yaml
tags:
- UKG
- Workforce Management
- Timekeeping
- Scheduling
- Accruals
tools:
- description: List all WFM employee records
  hints:
    openWorld: true
    readOnly: true
  name: list-wfm-employees
- description: Get timecard records for an employee within a date range
  hints:
    openWorld: true
    readOnly: true
  name: get-employee-timecards
- description: Get clock punch records for an employee
  hints:
    openWorld: true
    readOnly: true
  name: get-employee-punches
- description: Submit a clock punch for an employee
  hints:
    openWorld: false
    readOnly: false
  name: create-punch
- description: Get vacation, sick, and PTO accrual balances for an employee
  hints:
    openWorld: true
    readOnly: true
  name: get-employee-accruals
- description: List workforce schedules for a location and date range
  hints:
    openWorld: true
    readOnly: true
  name: list-schedules
- description: Get scheduled shifts for a specific employee
  hints:
    openWorld: true
    readOnly: true
  name: get-employee-shifts
- description: Get HCM employee record with full demographic and job data
  hints:
    openWorld: true
    readOnly: true
  name: get-hcm-employee
- description: Get employee pay statement history
  hints:
    openWorld: true
    readOnly: true
  name: list-pay-statements
---
