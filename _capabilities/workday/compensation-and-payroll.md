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
- get a pay group by id
- list compensation plans
- payroll
- compensation
- request a one-time payment
- comp request one time payment
- pay groups
- payroll get pay group
- benefits get eligible plans
- payroll list pay slips
- list plans
- financial management
- saas
- list pay slips
- get eligible benefit plans for a worker
- list compensation scorecards
- payroll list inputs
- list benefit elections
- cloud computing
- list dependents
- list pay groups
- benefit plans
- benefits list dependents
- submit a compensation change request
- compensation plans
- payroll get pay group details
- hcm
- benefits list elections
- list benefit plans
- comp list scorecards
- get pay group details
- submit a benefits change request
- workday
- list all pay groups
- benefits list plans
- comp list grades
- benefits change
- list compensation grades
- list payroll inputs
- payroll list pay groups
- benefits
- comp list plans
- list all benefit plans
- comp request change
- enterprise software
slug: compensation-and-payroll
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Workday Compensation and Payroll\"\n  description: \"Unified compensation and payroll management combining Compensation, Payroll, and Benefits APIs for payroll administrators to manage pay plans, benefits enrollment, and payroll processing.\"\n  tags:\n    - Workday\n    - Compensation\n    - Payroll\n    - Benefits\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      WORKDAY_OAUTH_TOKEN: WORKDAY_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: workday-compensation\n      location: ./shared/compensation.yaml\n    - import: workday-payroll\n      location: ./shared/payroll.yaml\n    - import: workday-benefits\n      location: ./shared/benefits.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: compensation-payroll-api\n      description: \"Unified REST API for compensation, payroll, and benefits.\"\n      resources:\n        - path: /v1/compensation-plans\n\
  \          name: compensation-plans\n          description: \"Compensation plans\"\n          operations:\n            - method: GET\n              name: list-plans\n              description: \"List compensation plans\"\n              call: \"workday-compensation.get-compensation-plans\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pay-groups\n          name: pay-groups\n          description: \"Pay groups\"\n          operations:\n            - method: GET\n              name: list-pay-groups\n              description: \"List pay groups\"\n              call: \"workday-payroll.get-pay-groups\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/benefit-plans\n          name: benefit-plans\n          description: \"Benefit plans\"\n          operations:\n            - method: GET\n              name: list-benefit-plans\n              description:\
  \ \"List benefit plans\"\n              call: \"workday-benefits.get-benefit-plans\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9082\n      namespace: compensation-payroll-mcp\n      transport: http\n      description: \"MCP server for AI-assisted compensation and payroll management.\"\n      tools:\n        - name: comp-list-plans\n          description: \"List compensation plans\"\n          hints:\n            readOnly: true\n          call: \"workday-compensation.get-compensation-plans\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: comp-request-change\n          description: \"Submit a compensation change request\"\n          hints:\n            readOnly: false\n          call: \"workday-compensation.request-compensation-change\"\n          with:\n            worker: \"tools.worker\"\n            proposedCompensation: \"tools.proposedCompensation\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: comp-list-scorecards\n          description: \"List compensation scorecards\"\n          hints:\n            readOnly: true\n          call: \"workday-compensation.get-compensation-scorecards\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: comp-list-grades\n          description: \"List compensation grades\"\n          hints:\n            readOnly: true\n          call: \"workday-compensation.get-compensation-grades\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: comp-request-one-time-payment\n          description: \"Request a one-time payment\"\n          hints:\n            readOnly: false\n          call: \"workday-compensation.request-one-time-payment\"\n          with:\n            worker: \"tools.worker\"\n            amount: \"tools.amount\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: payroll-list-pay-groups\n          description: \"List all pay groups\"\n          hints:\n            readOnly: true\n          call: \"workday-payroll.get-pay-groups\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: payroll-get-pay-group\n          description: \"Get a pay group by ID\"\n          hints:\n            readOnly: true\n          call: \"workday-payroll.get-pay-group-by-id\"\n          with:\n            ID: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: payroll-get-pay-group-details\n          description: \"Get pay group details\"\n          hints:\n            readOnly: true\n          call: \"workday-payroll.get-pay-group-details\"\n          with:\n            ID: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\
  \        - name: payroll-list-inputs\n          description: \"List payroll inputs\"\n          hints:\n            readOnly: true\n          call: \"workday-payroll.get-payroll-inputs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: payroll-list-pay-slips\n          description: \"List pay slips\"\n          hints:\n            readOnly: true\n          call: \"workday-payroll.get-pay-slips\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: benefits-list-elections\n          description: \"List benefit elections\"\n          hints:\n            readOnly: true\n          call: \"workday-benefits.get-benefit-elections\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: benefits-get-eligible-plans\n          description: \"Get eligible benefit plans for a worker\"\n          hints:\n            readOnly: true\n          call:\
  \ \"workday-benefits.get-eligible-benefit-plans\"\n          with:\n            worker: \"tools.worker\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: benefits-list-dependents\n          description: \"List dependents\"\n          hints:\n            readOnly: true\n          call: \"workday-benefits.get-dependents\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: benefits-change\n          description: \"Submit a benefits change request\"\n          hints:\n            readOnly: false\n          call: \"workday-benefits.change-benefits\"\n          with:\n            worker: \"tools.worker\"\n            benefitPlan: \"tools.benefitPlan\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: benefits-list-plans\n          description: \"List all benefit plans\"\n          hints:\n            readOnly: true\n          call:\
  \ \"workday-benefits.get-benefit-plans\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/workday/refs/heads/main/capabilities/compensation-and-payroll.yaml
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
