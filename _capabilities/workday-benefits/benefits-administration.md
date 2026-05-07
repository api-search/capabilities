---
categories: []
consumed_apis: []
description: Unified capability for HR and benefits teams managing Workday employee benefits including health insurance enrollments, retirement plans, dependent management, qualifying life events, and time off administration.
layout: capability
name: Workday Benefits Administration
operations:
- description: List benefit plans
  method: GET
  name: list-benefit-plans
  path: /v1/benefit-plans
- description: Get a benefit plan
  method: GET
  name: get-benefit-plan
  path: /v1/benefit-plans/{planId}
- description: List benefit enrollments
  method: GET
  name: list-benefit-enrollments
  path: /v1/benefit-enrollments
- description: Create enrollment
  method: POST
  name: create-benefit-enrollment
  path: /v1/benefit-enrollments
- description: List dependents
  method: GET
  name: list-dependents
  path: /v1/dependents
- description: Add a dependent
  method: POST
  name: create-dependent
  path: /v1/dependents
- description: Get employee benefits
  method: GET
  name: get-employee-benefits
  path: /v1/employees/{employeeId}/benefits
personas: []
provider_name: Workday Benefits
provider_slug: workday-benefits
search_terms:
- list workday benefit plans including health, dental, vision, life, and retirement options
- get a benefit plan
- benefit enrollments
- get benefit enrollment
- add a new dependent or beneficiary for an employee
- list benefit events
- list benefit plans
- workday
- list workday employee dependents and beneficiaries
- hcm
- add a dependent
- list time off plans
- list workday benefit qualifying life events and open enrollment windows
- hr
- list workday time off and leave plans with accrual information
- create benefit enrollment
- list workday benefit enrollments with optional filtering by employee or plan
- benefit plans
- employee benefits
- get a specific workday benefit plan with coverage options and costs
- list benefit enrollments
- enterprise
- get a specific workday benefit enrollment by id
- create enrollment
- create a new workday benefit enrollment for an employee
- benefits
- create dependent
- get a complete summary of all active benefit enrollments for an employee
- list dependents
- dependents
- get employee benefits
- get benefit plan
slug: benefits-administration
source_filename: benefits-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Workday Benefits Administration\n  description: Unified capability for HR and benefits teams managing Workday employee benefits including health insurance\n    enrollments, retirement plans, dependent management, qualifying life events, and time off administration.\n  tags:\n  - Benefits\n  - Employee Benefits\n  - Enterprise\n  - HCM\n  - HR\n  - Workday\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WORKDAY_CLIENT_ID: WORKDAY_CLIENT_ID\n    WORKDAY_CLIENT_SECRET: WORKDAY_CLIENT_SECRET\n    WORKDAY_TENANT: WORKDAY_TENANT\ncapability:\n  consumes:\n  - openapi: workday-benefits\n    location: ../../openapi/workday-benefits-openapi.yml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: workday-benefits-administration-api\n    description: Unified REST API for Workday Benefits Administration workflows.\n    resources:\n    - path: /v1/benefit-plans\n      name: benefit-plans\n      description:\
  \ Benefit plans\n      operations:\n      - method: GET\n        name: list-benefit-plans\n        description: List benefit plans\n        call: workday-benefits.list-benefit-plans\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/benefit-plans/{planId}\n      name: benefit-plan-by-id\n      operations:\n      - method: GET\n        name: get-benefit-plan\n        description: Get a benefit plan\n        call: workday-benefits.get-benefit-plan\n        with:\n          planId: rest.planId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/benefit-enrollments\n      name: benefit-enrollments\n      description: Benefit enrollments\n      operations:\n      - method: GET\n        name: list-benefit-enrollments\n        description: List benefit enrollments\n        call: workday-benefits.list-benefit-enrollments\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n\
  \        name: create-benefit-enrollment\n        description: Create enrollment\n        call: workday-benefits.create-benefit-enrollment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/dependents\n      name: dependents\n      description: Dependents\n      operations:\n      - method: GET\n        name: list-dependents\n        description: List dependents\n        call: workday-benefits.list-dependents\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-dependent\n        description: Add a dependent\n        call: workday-benefits.create-dependent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/employees/{employeeId}/benefits\n      name: employee-benefits\n      description: Employee benefits\n      operations:\n      - method: GET\n        name: get-employee-benefits\n        description: Get employee benefits\n        call: workday-benefits.get-employee-benefits\n\
  \        with:\n          employeeId: rest.employeeId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: workday-benefits-administration-mcp\n    transport: http\n    description: MCP server for AI-assisted Workday Benefits Administration, enrollment operations, and benefits analytics.\n    tools:\n    - name: list-benefit-plans\n      description: List Workday benefit plans including health, dental, vision, life, and retirement options\n      hints:\n        readOnly: true\n        openWorld: true\n      call: workday-benefits.list-benefit-plans\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-benefit-plan\n      description: Get a specific Workday benefit plan with coverage options and costs\n      hints:\n        readOnly: true\n      call: workday-benefits.get-benefit-plan\n      with:\n        planId: tools.planId\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: list-benefit-enrollments\n      description: List Workday benefit enrollments with optional filtering by employee or plan\n      hints:\n        readOnly: true\n      call: workday-benefits.list-benefit-enrollments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-benefit-enrollment\n      description: Get a specific Workday benefit enrollment by ID\n      hints:\n        readOnly: true\n      call: workday-benefits.get-benefit-enrollment\n      with:\n        enrollmentId: tools.enrollmentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-benefit-enrollment\n      description: Create a new Workday benefit enrollment for an employee\n      hints:\n        readOnly: false\n      call: workday-benefits.create-benefit-enrollment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-dependents\n      description: List Workday employee dependents and beneficiaries\n \
  \     hints:\n        readOnly: true\n      call: workday-benefits.list-dependents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-dependent\n      description: Add a new dependent or beneficiary for an employee\n      hints:\n        readOnly: false\n      call: workday-benefits.create-dependent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-benefit-events\n      description: List Workday benefit qualifying life events and open enrollment windows\n      hints:\n        readOnly: true\n      call: workday-benefits.list-benefit-events\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-time-off-plans\n      description: List Workday time off and leave plans with accrual information\n      hints:\n        readOnly: true\n      call: workday-benefits.list-time-off-plans\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-employee-benefits\n    \
  \  description: Get a complete summary of all active benefit enrollments for an employee\n      hints:\n        readOnly: true\n      call: workday-benefits.get-employee-benefits\n      with:\n        employeeId: tools.employeeId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/workday-benefits/refs/heads/main/capabilities/benefits-administration.yaml
tags:
- Benefits
- Employee Benefits
- Enterprise
- HCM
- HR
- Workday
tools:
- description: List Workday benefit plans including health, dental, vision, life, and retirement options
  hints:
    openWorld: true
    readOnly: true
  name: list-benefit-plans
- description: Get a specific Workday benefit plan with coverage options and costs
  hints:
    readOnly: true
  name: get-benefit-plan
- description: List Workday benefit enrollments with optional filtering by employee or plan
  hints:
    readOnly: true
  name: list-benefit-enrollments
- description: Get a specific Workday benefit enrollment by ID
  hints:
    readOnly: true
  name: get-benefit-enrollment
- description: Create a new Workday benefit enrollment for an employee
  hints:
    readOnly: false
  name: create-benefit-enrollment
- description: List Workday employee dependents and beneficiaries
  hints:
    readOnly: true
  name: list-dependents
- description: Add a new dependent or beneficiary for an employee
  hints:
    readOnly: false
  name: create-dependent
- description: List Workday benefit qualifying life events and open enrollment windows
  hints:
    readOnly: true
  name: list-benefit-events
- description: List Workday time off and leave plans with accrual information
  hints:
    readOnly: true
  name: list-time-off-plans
- description: Get a complete summary of all active benefit enrollments for an employee
  hints:
    readOnly: true
  name: get-employee-benefits
---
