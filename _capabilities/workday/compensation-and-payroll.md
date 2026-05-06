---
categories:
- payroll-hr
consumed_apis: []
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
- benefit plans
- list pay groups
- submit a compensation change request
- benefits list plans
- list benefit elections
- get pay group details
- compensation
- comp request change
- list benefit plans
- benefits list dependents
- list dependents
- payroll list pay groups
- list payroll inputs
- comp request one time payment
- submit a benefits change request
- payroll list pay slips
- list plans
- list all pay groups
- payroll get pay group details
- benefits
- get eligible benefit plans for a worker
- comp list scorecards
- cloud computing
- payroll
- benefits change
- workday
- list compensation plans
- financial management
- request a one-time payment
- saas
- benefits get eligible plans
- payroll list inputs
- hcm
- comp list plans
- payroll get pay group
- compensation plans
- list compensation grades
- enterprise software
- list pay slips
- list all benefit plans
- benefits list elections
- pay groups
- get a pay group by id
- comp list grades
- list compensation scorecards
slug: compensation-and-payroll
source_filename: compensation-and-payroll.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Workday Compensation and Payroll\n  description: Unified compensation and payroll management combining Compensation, Payroll, and Benefits APIs for payroll\n    administrators to manage pay plans, benefits enrollment, and payroll processing.\n  tags:\n  - Workday\n  - Compensation\n  - Payroll\n  - Benefits\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WORKDAY_OAUTH_TOKEN: WORKDAY_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: workday-compensation\n    baseUri: https://wd2-impl-services1.workday.com/ccx/api/v1/{tenant}/compensation\n    description: Workday Compensation REST API.\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_OAUTH_TOKEN}}'\n    resources:\n    - name: compensation\n      path: /\n      description: Compensation operations\n      operations:\n      - name: get-compensation-plans\n        method: GET\n        description: Returns compensation\
  \ plans.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: request-compensation-change\n        method: POST\n        description: Submits a compensation change request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            worker: '{{tools.worker}}'\n            proposedCompensation: '{{tools.proposedCompensation}}'\n      - name: get-compensation-scorecards\n        method: GET\n        description: Returns compensation scorecards.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-compensation-scorecard-by-id\n        method: GET\n        description: Returns a compensation scorecard by ID.\n        inputParameters:\n        - name: ID\n          in: path\n    \
  \      type: string\n          required: true\n          description: Scorecard ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-compensation-scorecard-results\n        method: GET\n        description: Returns scorecard results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: request-one-time-payment\n        method: POST\n        description: Requests a one-time payment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            worker: '{{tools.worker}}'\n            amount: '{{tools.amount}}'\n      - name: get-compensation-grades\n        method: GET\n        description: Returns compensation grades.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: workday-payroll\n    baseUri: https://wd2-impl-services1.workday.com/ccx/api/v1/{tenant}/payroll\n    description: Workday Payroll REST API.\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_OAUTH_TOKEN}}'\n    resources:\n    - name: payroll\n      path: /\n      description: Payroll operations\n      operations:\n      - name: get-pay-groups\n        method: GET\n        description: Returns pay groups.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-pay-group-by-id\n        method: GET\n        description: Returns a pay group by ID.\n        inputParameters:\n        - name: ID\n          in: path\n          type: string\n          required: true\n          description: Pay group ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n    \
  \      type: object\n          value: $.\n      - name: get-pay-group-details\n        method: GET\n        description: Returns pay group details.\n        inputParameters:\n        - name: ID\n          in: path\n          type: string\n          required: true\n          description: Pay group ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-payroll-inputs\n        method: GET\n        description: Returns payroll inputs.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-pay-slips\n        method: GET\n        description: Returns pay slips.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: workday-benefits\n    baseUri: https://wd2-impl-services1.workday.com/ccx/api/v1/{tenant}/benefits\n\
  \    description: Workday Benefits REST API.\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_OAUTH_TOKEN}}'\n    resources:\n    - name: benefits\n      path: /\n      description: Benefits operations\n      operations:\n      - name: get-benefit-elections\n        method: GET\n        description: Returns benefit elections for workers.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-eligible-benefit-plans\n        method: GET\n        description: Returns eligible benefit plans for a worker.\n        inputParameters:\n        - name: worker\n          in: query\n          type: string\n          required: true\n          description: Worker ID.\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n      - name: get-dependents\n        method: GET\n        description: Returns dependents for a worker.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: change-benefits\n        method: POST\n        description: Submits a benefits change request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            worker: '{{tools.worker}}'\n            benefitPlan: '{{tools.benefitPlan}}'\n      - name: get-benefit-plans\n        method: GET\n        description: Returns available benefit plans.\n        inputParameters:\n        - name: limit\n \
  \         in: query\n          type: integer\n          required: false\n          description: Maximum results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: compensation-payroll-api\n    description: Unified REST API for compensation, payroll, and benefits.\n    resources:\n    - path: /v1/compensation-plans\n      name: compensation-plans\n      description: Compensation plans\n      operations:\n      - method: GET\n        name: list-plans\n        description: List compensation plans\n        call: workday-compensation.get-compensation-plans\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pay-groups\n      name: pay-groups\n      description: Pay groups\n      operations:\n      - method: GET\n        name: list-pay-groups\n        description: List pay groups\n        call: workday-payroll.get-pay-groups\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/benefit-plans\n      name: benefit-plans\n      description: Benefit plans\n      operations:\n      - method: GET\n        name: list-benefit-plans\n        description: List benefit plans\n        call: workday-benefits.get-benefit-plans\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9082\n    namespace: compensation-payroll-mcp\n    transport: http\n    description: MCP server for AI-assisted compensation and payroll management.\n    tools:\n    - name: comp-list-plans\n      description: List compensation plans\n      hints:\n        readOnly: true\n      call: workday-compensation.get-compensation-plans\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: comp-request-change\n      description: Submit a compensation change request\n      hints:\n        readOnly: false\n      call: workday-compensation.request-compensation-change\n\
  \      with:\n        worker: tools.worker\n        proposedCompensation: tools.proposedCompensation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: comp-list-scorecards\n      description: List compensation scorecards\n      hints:\n        readOnly: true\n      call: workday-compensation.get-compensation-scorecards\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: comp-list-grades\n      description: List compensation grades\n      hints:\n        readOnly: true\n      call: workday-compensation.get-compensation-grades\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: comp-request-one-time-payment\n      description: Request a one-time payment\n      hints:\n        readOnly: false\n      call: workday-compensation.request-one-time-payment\n      with:\n        worker: tools.worker\n        amount: tools.amount\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ payroll-list-pay-groups\n      description: List all pay groups\n      hints:\n        readOnly: true\n      call: workday-payroll.get-pay-groups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: payroll-get-pay-group\n      description: Get a pay group by ID\n      hints:\n        readOnly: true\n      call: workday-payroll.get-pay-group-by-id\n      with:\n        ID: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: payroll-get-pay-group-details\n      description: Get pay group details\n      hints:\n        readOnly: true\n      call: workday-payroll.get-pay-group-details\n      with:\n        ID: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: payroll-list-inputs\n      description: List payroll inputs\n      hints:\n        readOnly: true\n      call: workday-payroll.get-payroll-inputs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ payroll-list-pay-slips\n      description: List pay slips\n      hints:\n        readOnly: true\n      call: workday-payroll.get-pay-slips\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: benefits-list-elections\n      description: List benefit elections\n      hints:\n        readOnly: true\n      call: workday-benefits.get-benefit-elections\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: benefits-get-eligible-plans\n      description: Get eligible benefit plans for a worker\n      hints:\n        readOnly: true\n      call: workday-benefits.get-eligible-benefit-plans\n      with:\n        worker: tools.worker\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: benefits-list-dependents\n      description: List dependents\n      hints:\n        readOnly: true\n      call: workday-benefits.get-dependents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: benefits-change\n\
  \      description: Submit a benefits change request\n      hints:\n        readOnly: false\n      call: workday-benefits.change-benefits\n      with:\n        worker: tools.worker\n        benefitPlan: tools.benefitPlan\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: benefits-list-plans\n      description: List all benefit plans\n      hints:\n        readOnly: true\n      call: workday-benefits.get-benefit-plans\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
