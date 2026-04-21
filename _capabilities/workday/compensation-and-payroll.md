---
consumed_apis:
- workday-compensation
- workday-payroll
- workday-benefits
description: Unified compensation and payroll management combining Compensation, Payroll, and Benefits APIs for payroll administrators to manage pay plans, benefits enrollment, and payroll processing.
layout: capability
name: Workday Compensation and Payroll
operations:
- description: List compensation plans
  method: GET
  name: list-plans
  path: /v1/compensation-plans
- description: List pay groups
  method: GET
  name: list-pay-groups
  path: /v1/pay-groups
- description: List benefit plans
  method: GET
  name: list-benefit-plans
  path: /v1/benefit-plans
personas: []
provider_name: Workday
provider_slug: workday
search_terms:
- payroll get pay group
- benefits list elections
- list all pay groups
- list payroll inputs
- workday
- list benefit plans
- list benefit elections
- list plans
- get a pay group by id
- payroll list inputs
- benefits list dependents
- benefits list plans
- list pay groups
- benefits get eligible plans
- list all benefit plans
- list compensation grades
- list pay slips
- compensation plans
- get pay group details
- benefits
- hcm
- comp request change
- benefit plans
- request a one-time payment
- saas
- payroll
- comp list scorecards
- list compensation plans
- pay groups
- enterprise software
- financial management
- benefits change
- payroll get pay group details
- submit a compensation change request
- list compensation scorecards
- comp list plans
- payroll list pay groups
- list dependents
- payroll list pay slips
- submit a benefits change request
- comp list grades
- comp request one time payment
- get eligible benefit plans for a worker
- cloud computing
- compensation
slug: compensation-and-payroll
tags:
- Workday
- Compensation
- Payroll
- Benefits
tools:
- description: List compensation plans
  hints:
    readOnly: true
  name: comp-list-plans
- description: Submit a compensation change request
  hints:
    readOnly: false
  name: comp-request-change
- description: List compensation scorecards
  hints:
    readOnly: true
  name: comp-list-scorecards
- description: List compensation grades
  hints:
    readOnly: true
  name: comp-list-grades
- description: Request a one-time payment
  hints:
    readOnly: false
  name: comp-request-one-time-payment
- description: List all pay groups
  hints:
    readOnly: true
  name: payroll-list-pay-groups
- description: Get a pay group by ID
  hints:
    readOnly: true
  name: payroll-get-pay-group
- description: Get pay group details
  hints:
    readOnly: true
  name: payroll-get-pay-group-details
- description: List payroll inputs
  hints:
    readOnly: true
  name: payroll-list-inputs
- description: List pay slips
  hints:
    readOnly: true
  name: payroll-list-pay-slips
- description: List benefit elections
  hints:
    readOnly: true
  name: benefits-list-elections
- description: Get eligible benefit plans for a worker
  hints:
    readOnly: true
  name: benefits-get-eligible-plans
- description: List dependents
  hints:
    readOnly: true
  name: benefits-list-dependents
- description: Submit a benefits change request
  hints:
    readOnly: false
  name: benefits-change
- description: List all benefit plans
  hints:
    readOnly: true
  name: benefits-list-plans
---
