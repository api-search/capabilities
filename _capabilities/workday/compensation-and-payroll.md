---
categories:
- payroll-hr
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
- list benefit plans
- benefits get eligible plans
- list compensation grades
- list compensation scorecards
- request a one-time payment
- get pay group details
- cloud computing
- get eligible benefit plans for a worker
- compensation plans
- pay groups
- payroll get pay group details
- payroll list pay slips
- list benefit elections
- comp request change
- list all benefit plans
- payroll
- list compensation plans
- benefit plans
- comp list scorecards
- list dependents
- list pay groups
- hcm
- comp list plans
- workday
- benefits list elections
- list plans
- benefits
- get a pay group by id
- saas
- list all pay groups
- payroll get pay group
- benefits list dependents
- enterprise software
- compensation
- comp list grades
- list payroll inputs
- list pay slips
- benefits change
- submit a compensation change request
- comp request one time payment
- benefits list plans
- submit a benefits change request
- financial management
- payroll list pay groups
- payroll list inputs
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
