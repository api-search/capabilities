---
categories: []
consumed_apis:
- workday-advanced-compensation
description: Unified capability for HR compensation teams managing Workday Advanced Compensation including compensation plans, merit increases, bonus plans, equity awards, budgets, review cycles, and individual employee compensation packages.
layout: capability
name: Workday Advanced Compensation Management
operations:
- description: List compensation plans
  method: GET
  name: list-compensation-plans
  path: /v1/compensation-plans
- description: Create a new compensation plan
  method: POST
  name: create-compensation-plan
  path: /v1/compensation-plans
- description: Get a compensation plan
  method: GET
  name: get-compensation-plan
  path: /v1/compensation-plans/{planId}
- description: List compensation grades
  method: GET
  name: list-compensation-grades
  path: /v1/compensation-grades
- description: List merit plans
  method: GET
  name: list-merit-plans
  path: /v1/merit-plans
- description: List bonus plans
  method: GET
  name: list-bonus-plans
  path: /v1/bonus-plans
- description: List stock plans
  method: GET
  name: list-stock-plans
  path: /v1/stock-plans
- description: List compensation budgets
  method: GET
  name: list-compensation-budgets
  path: /v1/compensation-budgets
- description: List compensation reviews
  method: GET
  name: list-compensation-reviews
  path: /v1/compensation-reviews
- description: Get employee compensation
  method: GET
  name: get-employee-compensation
  path: /v1/employees/{employeeId}/compensation
- description: Update employee compensation
  method: PUT
  name: update-employee-compensation
  path: /v1/employees/{employeeId}/compensation
personas: []
provider_name: Workday Advanced Compensation
provider_slug: workday-advanced-compensation
search_terms:
- workday
- merit plans
- update employee compensation
- list bonus plans
- stock plans
- get compensation grade
- enterprise
- compensation grades
- employee compensation
- hcm
- list compensation plans
- list workday merit increase plans and guidelines
- update an employee's compensation including merit increases or off-cycle adjustments
- hr
- list stock plans
- benefits
- single compensation plan
- list merit plans
- list compensation reviews
- create a new compensation plan
- list workday equity and stock compensation plans
- list workday compensation budgets and track allocations
- get a specific workday compensation grade with pay range details
- list workday compensation grades and their pay ranges
- advanced compensation
- get employee compensation
- create compensation plan
- list compensation budgets
- list workday compensation review cycles and their status
- bonus plans
- list compensation grades
- list workday compensation plans with optional filtering by type or status
- get a compensation plan
- get a specific workday compensation plan by id
- get compensation plan
- compensation reviews
- compensation plans
- create a new workday compensation plan
- get an employee's current compensation package including base pay, bonuses, and equity
- list workday bonus and incentive compensation plans
- compensation budgets
slug: compensation-management
source_filename: compensation-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Workday Advanced Compensation Management\"\n  description: \"Unified capability for HR compensation teams managing Workday Advanced Compensation including compensation plans, merit increases, bonus plans, equity awards, budgets, review cycles, and individual employee compensation packages.\"\n  tags:\n    - Advanced Compensation\n    - Benefits\n    - Enterprise\n    - HCM\n    - HR\n    - Workday\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WORKDAY_CLIENT_ID: WORKDAY_CLIENT_ID\n      WORKDAY_CLIENT_SECRET: WORKDAY_CLIENT_SECRET\n      WORKDAY_TENANT: WORKDAY_TENANT\n\ncapability:\n  consumes:\n    - import: workday-advanced-compensation\n      location: ./shared/advanced-compensation.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: workday-compensation-management-api\n      description: \"Unified REST API for Workday Advanced Compensation management\
  \ workflows.\"\n      resources:\n        - path: /v1/compensation-plans\n          name: compensation-plans\n          description: \"Compensation plans\"\n          operations:\n            - method: GET\n              name: list-compensation-plans\n              description: \"List compensation plans\"\n              call: \"workday-advanced-compensation.list-compensation-plans\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-compensation-plan\n              description: \"Create a new compensation plan\"\n              call: \"workday-advanced-compensation.create-compensation-plan\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/compensation-plans/{planId}\n          name: compensation-plan-by-id\n          description: \"Single compensation plan\"\n          operations:\n            - method: GET\n  \
  \            name: get-compensation-plan\n              description: \"Get a compensation plan\"\n              call: \"workday-advanced-compensation.get-compensation-plan\"\n              with:\n                planId: \"rest.planId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/compensation-grades\n          name: compensation-grades\n          description: \"Compensation grades\"\n          operations:\n            - method: GET\n              name: list-compensation-grades\n              description: \"List compensation grades\"\n              call: \"workday-advanced-compensation.list-compensation-grades\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/merit-plans\n          name: merit-plans\n          description: \"Merit plans\"\n          operations:\n            - method: GET\n              name: list-merit-plans\n             \
  \ description: \"List merit plans\"\n              call: \"workday-advanced-compensation.list-merit-plans\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/bonus-plans\n          name: bonus-plans\n          description: \"Bonus plans\"\n          operations:\n            - method: GET\n              name: list-bonus-plans\n              description: \"List bonus plans\"\n              call: \"workday-advanced-compensation.list-bonus-plans\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/stock-plans\n          name: stock-plans\n          description: \"Stock plans\"\n          operations:\n            - method: GET\n              name: list-stock-plans\n              description: \"List stock plans\"\n              call: \"workday-advanced-compensation.list-stock-plans\"\n              outputParameters:\n                - type: object\n   \
  \               mapping: \"$.\"\n        - path: /v1/compensation-budgets\n          name: compensation-budgets\n          description: \"Compensation budgets\"\n          operations:\n            - method: GET\n              name: list-compensation-budgets\n              description: \"List compensation budgets\"\n              call: \"workday-advanced-compensation.list-compensation-budgets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/compensation-reviews\n          name: compensation-reviews\n          description: \"Compensation reviews\"\n          operations:\n            - method: GET\n              name: list-compensation-reviews\n              description: \"List compensation reviews\"\n              call: \"workday-advanced-compensation.list-compensation-reviews\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/employees/{employeeId}/compensation\n\
  \          name: employee-compensation\n          description: \"Employee compensation\"\n          operations:\n            - method: GET\n              name: get-employee-compensation\n              description: \"Get employee compensation\"\n              call: \"workday-advanced-compensation.get-employee-compensation\"\n              with:\n                employeeId: \"rest.employeeId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-employee-compensation\n              description: \"Update employee compensation\"\n              call: \"workday-advanced-compensation.update-employee-compensation\"\n              with:\n                employeeId: \"rest.employeeId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: workday-compensation-management-mcp\n      transport: http\n\
  \      description: \"MCP server for AI-assisted Workday Advanced Compensation management, plan operations, and compensation analytics.\"\n      tools:\n        - name: list-compensation-plans\n          description: \"List Workday compensation plans with optional filtering by type or status\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"workday-advanced-compensation.list-compensation-plans\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-compensation-plan\n          description: \"Get a specific Workday compensation plan by ID\"\n          hints:\n            readOnly: true\n          call: \"workday-advanced-compensation.get-compensation-plan\"\n          with:\n            planId: \"tools.planId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-compensation-plan\n          description: \"Create a new Workday compensation\
  \ plan\"\n          hints:\n            readOnly: false\n          call: \"workday-advanced-compensation.create-compensation-plan\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-compensation-grades\n          description: \"List Workday compensation grades and their pay ranges\"\n          hints:\n            readOnly: true\n          call: \"workday-advanced-compensation.list-compensation-grades\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-compensation-grade\n          description: \"Get a specific Workday compensation grade with pay range details\"\n          hints:\n            readOnly: true\n          call: \"workday-advanced-compensation.get-compensation-grade\"\n          with:\n            gradeId: \"tools.gradeId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-merit-plans\n          description:\
  \ \"List Workday merit increase plans and guidelines\"\n          hints:\n            readOnly: true\n          call: \"workday-advanced-compensation.list-merit-plans\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-bonus-plans\n          description: \"List Workday bonus and incentive compensation plans\"\n          hints:\n            readOnly: true\n          call: \"workday-advanced-compensation.list-bonus-plans\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-stock-plans\n          description: \"List Workday equity and stock compensation plans\"\n          hints:\n            readOnly: true\n          call: \"workday-advanced-compensation.list-stock-plans\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-compensation-budgets\n          description: \"List Workday compensation budgets and track allocations\"\
  \n          hints:\n            readOnly: true\n          call: \"workday-advanced-compensation.list-compensation-budgets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-compensation-reviews\n          description: \"List Workday compensation review cycles and their status\"\n          hints:\n            readOnly: true\n          call: \"workday-advanced-compensation.list-compensation-reviews\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-employee-compensation\n          description: \"Get an employee's current compensation package including base pay, bonuses, and equity\"\n          hints:\n            readOnly: true\n          call: \"workday-advanced-compensation.get-employee-compensation\"\n          with:\n            employeeId: \"tools.employeeId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name:\
  \ update-employee-compensation\n          description: \"Update an employee's compensation including merit increases or off-cycle adjustments\"\n          hints:\n            readOnly: false\n          call: \"workday-advanced-compensation.update-employee-compensation\"\n          with:\n            employeeId: \"tools.employeeId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/workday-advanced-compensation/refs/heads/main/capabilities/compensation-management.yaml
tags:
- Advanced Compensation
- Benefits
- Enterprise
- HCM
- HR
- Workday
tools:
- description: List Workday compensation plans with optional filtering by type or status
  hints:
    openWorld: true
    readOnly: true
  name: list-compensation-plans
- description: Get a specific Workday compensation plan by ID
  hints:
    readOnly: true
  name: get-compensation-plan
- description: Create a new Workday compensation plan
  hints:
    readOnly: false
  name: create-compensation-plan
- description: List Workday compensation grades and their pay ranges
  hints:
    readOnly: true
  name: list-compensation-grades
- description: Get a specific Workday compensation grade with pay range details
  hints:
    readOnly: true
  name: get-compensation-grade
- description: List Workday merit increase plans and guidelines
  hints:
    readOnly: true
  name: list-merit-plans
- description: List Workday bonus and incentive compensation plans
  hints:
    readOnly: true
  name: list-bonus-plans
- description: List Workday equity and stock compensation plans
  hints:
    readOnly: true
  name: list-stock-plans
- description: List Workday compensation budgets and track allocations
  hints:
    readOnly: true
  name: list-compensation-budgets
- description: List Workday compensation review cycles and their status
  hints:
    readOnly: true
  name: list-compensation-reviews
- description: Get an employee's current compensation package including base pay, bonuses, and equity
  hints:
    readOnly: true
  name: get-employee-compensation
- description: Update an employee's compensation including merit increases or off-cycle adjustments
  hints:
    readOnly: false
  name: update-employee-compensation
---
