---
categories: []
consumed_apis: []
description: HR administration workflow combining employee records, benefits, payroll, and organizational management capabilities.
layout: capability
name: UKG HR Administration
operations:
- description: List all employees
  method: GET
  name: list-employees
  path: /v1/employees
- description: Get benefits elections for an employee
  method: GET
  name: get-benefits-elections
  path: /v1/employees/{employeeId}/benefits
- description: Get pay statement history
  method: GET
  name: list-pay-statements
  path: /v1/pay-statements
personas: []
provider_name: UKG
provider_slug: ukg
search_terms:
- list all work locations
- get benefits elections
- clock punches, timecards, and time approval workflows
- vacation, sick, and pto accrual policy management
- list employees
- list all departments in the organization
- hcm
- get employee pay statement history
- get employee
- get pay rates for an employee
- hr
- get pay statement history
- list pay statements
- manages benefits enrollment, plan administration, and compliance
- core hr functions including employee records, hiring, and organizational management
- pay processing, compensation management, and pay statement history
- ukg
- scheduling
- benefits
- payroll
- workforce schedules, shift management, and coverage planning
- list all employees
- hr administration
- employee records
- human capital management
- employee benefits elections
- get employee jobs
- manages employee schedules, timecards, and attendance
- employee records, benefits, payroll, and organizational management
- time and attendance
- list locations
- processes payroll, manages pay rates, and reviews pay statements
- creates and manages workforce schedules and shift assignments
- list all employee records with demographics and job data
- workforce management
- list departments
- get a specific employee record by id
- employees
- get benefits elections for an employee
- views own records, timecards, benefits, and pay statements
- employee pay statements
- benefits enrollment, elections, and plan administration
- timekeeping, scheduling, and accrual management for hourly and salaried employees
- get pay rates
- manages employee records, org structure, and hr transactions
- get job assignment information for an employee
slug: hr-administration
source_filename: hr-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"UKG HR Administration\"\n  description: \"HR administration workflow combining employee records, benefits, payroll, and organizational management capabilities.\"\n  tags:\n    - UKG\n    - HCM\n    - HR Administration\n    - Benefits\n    - Payroll\n    - Employees\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n  personas:\n    - HR Administrator\n    - Benefits Administrator\n    - Payroll Processor\n    - HR Business Partner\n\nimports:\n  - url: shared/pro-hcm.yaml\n    namespace: pro-hcm\n\ncapability:\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: hr-administration-api\n      resources:\n        - path: /v1/employees\n          name: employees\n          description: \"Employee records\"\n          operations:\n            - method: GET\n              name: list-employees\n              description: \"List all employees\"\n              call: \"pro-hcm.list-employees\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/employees/{employeeId}/benefits\n          name: benefits\n          description: \"Employee benefits elections\"\n          operations:\n            - method: GET\n              name: get-benefits-elections\n              description: \"Get benefits elections for an employee\"\n              call: \"pro-hcm.get-benefits-elections\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pay-statements\n          name: pay-statements\n          description: \"Employee pay statements\"\n          operations:\n            - method: GET\n              name: list-pay-statements\n              description: \"Get pay statement history\"\n              call: \"pro-hcm.list-pay-statements\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n    - type: mcp\n      port: 9081\n      namespace: hr-administration-mcp\n\
  \      transport: http\n      tools:\n        - name: list-employees\n          description: \"List all employee records with demographics and job data\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"pro-hcm.list-employees\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-employee\n          description: \"Get a specific employee record by ID\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"pro-hcm.get-employee\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-employee-jobs\n          description: \"Get job assignment information for an employee\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"pro-hcm.get-employee-jobs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-pay-rates\n\
  \          description: \"Get pay rates for an employee\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"pro-hcm.get-pay-rates\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-benefits-elections\n          description: \"Get benefits elections for an employee\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"pro-hcm.get-benefits-elections\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-departments\n          description: \"List all departments in the organization\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"pro-hcm.list-departments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-locations\n          description: \"List all work locations\"\n          hints:\n\
  \            readOnly: true\n            openWorld: true\n          call: \"pro-hcm.list-locations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-pay-statements\n          description: \"Get employee pay statement history\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"pro-hcm.list-pay-statements\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ukg/refs/heads/main/capabilities/hr-administration.yaml
tags:
- UKG
- HCM
- HR Administration
- Benefits
- Payroll
- Employees
tools:
- description: List all employee records with demographics and job data
  hints:
    openWorld: true
    readOnly: true
  name: list-employees
- description: Get a specific employee record by ID
  hints:
    openWorld: true
    readOnly: true
  name: get-employee
- description: Get job assignment information for an employee
  hints:
    openWorld: true
    readOnly: true
  name: get-employee-jobs
- description: Get pay rates for an employee
  hints:
    openWorld: true
    readOnly: true
  name: get-pay-rates
- description: Get benefits elections for an employee
  hints:
    openWorld: true
    readOnly: true
  name: get-benefits-elections
- description: List all departments in the organization
  hints:
    openWorld: true
    readOnly: true
  name: list-departments
- description: List all work locations
  hints:
    openWorld: true
    readOnly: true
  name: list-locations
- description: Get employee pay statement history
  hints:
    openWorld: true
    readOnly: true
  name: list-pay-statements
---
