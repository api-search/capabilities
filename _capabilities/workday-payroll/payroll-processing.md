---
categories: []
consumed_apis: []
description: Unified capability for end-to-end payroll processing workflows combining the Workday Payroll, Payroll Input, Payroll Results, and Tax APIs. Supports HR administrators and payroll specialists running payroll cycles, managing worker pay data, submitting adjustments, and reviewing payroll results and compliance data.
layout: capability
name: Workday Payroll Processing
operations:
- description: List all payroll runs with optional filters
  method: GET
  name: list-pay-runs
  path: /v1/pay-runs
- description: Initiate a new payroll run
  method: POST
  name: create-pay-run
  path: /v1/pay-runs
- description: Get pay run details
  method: GET
  name: get-pay-run
  path: /v1/pay-runs/{payRunId}
- description: Update a pay run
  method: PATCH
  name: update-pay-run
  path: /v1/pay-runs/{payRunId}
- description: Trigger payroll calculations for a pay run
  method: POST
  name: calculate-pay-run
  path: /v1/pay-runs/{payRunId}/calculate
- description: Mark a pay run as completed
  method: POST
  name: complete-pay-run
  path: /v1/pay-runs/{payRunId}/complete
- description: Get aggregated results for a completed pay run
  method: GET
  name: get-pay-run-results
  path: /v1/pay-runs/{payRunId}/results
- description: List individual worker results for a pay run
  method: GET
  name: list-pay-run-worker-results
  path: /v1/pay-runs/{payRunId}/worker-results
- description: Get detailed result for a worker in a pay run
  method: GET
  name: get-pay-run-worker-result
  path: /v1/pay-runs/{payRunId}/worker-results/{workerId}
- description: List payments for a completed pay run
  method: GET
  name: list-pay-run-payments
  path: /v1/pay-runs/{payRunId}/payments
- description: List tax calculation results for a pay run
  method: GET
  name: list-pay-run-tax-results
  path: /v1/pay-runs/{payRunId}/tax-results
- description: List all pay groups
  method: GET
  name: list-pay-groups
  path: /v1/pay-groups
- description: Get a specific pay group
  method: GET
  name: get-pay-group
  path: /v1/pay-groups/{payGroupId}
- description: List workers in a pay group
  method: GET
  name: list-pay-group-workers
  path: /v1/pay-groups/{payGroupId}/workers
- description: Get a specific payment transaction
  method: GET
  name: get-payment
  path: /v1/payments/{paymentId}
- description: Get payroll details for a worker
  method: GET
  name: get-worker-payroll-details
  path: /v1/workers/{workerId}/payroll-details
- description: List payslips for a worker
  method: GET
  name: list-worker-payslips
  path: /v1/workers/{workerId}/payslips
- description: Get a specific payslip
  method: GET
  name: get-worker-payslip
  path: /v1/workers/{workerId}/payslips/{payslipId}
- description: List payment elections for a worker
  method: GET
  name: list-worker-payment-elections
  path: /v1/workers/{workerId}/payment-elections
- description: List earnings for a worker
  method: GET
  name: list-worker-earnings
  path: /v1/workers/{workerId}/earnings
- description: List deductions for a worker
  method: GET
  name: list-worker-deductions
  path: /v1/workers/{workerId}/deductions
- description: List tax withholdings for a worker
  method: GET
  name: list-worker-tax-withholdings
  path: /v1/workers/{workerId}/tax-withholdings
- description: Get a specific tax withholding
  method: GET
  name: get-worker-tax-withholding
  path: /v1/workers/{workerId}/tax-withholdings/{withholdingId}
- description: Update a tax withholding
  method: PATCH
  name: update-worker-tax-withholding
  path: /v1/workers/{workerId}/tax-withholdings/{withholdingId}
- description: List tax elections for a worker
  method: GET
  name: list-worker-tax-elections
  path: /v1/workers/{workerId}/tax-elections
- description: Submit a new W-4 or state tax election
  method: POST
  name: create-worker-tax-election
  path: /v1/workers/{workerId}/tax-elections
- description: Get a specific tax election
  method: GET
  name: get-worker-tax-election
  path: /v1/workers/{workerId}/tax-elections/{electionId}
- description: Get year-to-date tax summary
  method: GET
  name: get-worker-tax-summary
  path: /v1/workers/{workerId}/tax-summary
- description: List time off inputs for a worker
  method: GET
  name: list-worker-time-off-inputs
  path: /v1/workers/{workerId}/time-off-inputs
- description: Submit a time off input
  method: POST
  name: create-worker-time-off-input
  path: /v1/workers/{workerId}/time-off-inputs
- description: List one-time payment requests
  method: GET
  name: list-one-time-payments
  path: /v1/one-time-payments
- description: Submit a one-time payment
  method: POST
  name: create-one-time-payment
  path: /v1/one-time-payments
- description: Get a specific one-time payment
  method: GET
  name: get-one-time-payment
  path: /v1/one-time-payments/{paymentId}
- description: Update a pending one-time payment
  method: PATCH
  name: update-one-time-payment
  path: /v1/one-time-payments/{paymentId}
- description: Delete a pending one-time payment
  method: DELETE
  name: delete-one-time-payment
  path: /v1/one-time-payments/{paymentId}
- description: List payroll adjustments
  method: GET
  name: list-payroll-adjustments
  path: /v1/adjustments
- description: Submit a payroll adjustment
  method: POST
  name: create-payroll-adjustment
  path: /v1/adjustments
- description: Get a specific payroll adjustment
  method: GET
  name: get-payroll-adjustment
  path: /v1/adjustments/{adjustmentId}
- description: List supplemental earnings
  method: GET
  name: list-supplemental-earnings
  path: /v1/supplemental-earnings
- description: Submit a supplemental earning
  method: POST
  name: create-supplemental-earning
  path: /v1/supplemental-earnings
- description: Get a specific supplemental earning
  method: GET
  name: get-supplemental-earning
  path: /v1/supplemental-earnings/{earningId}
- description: Delete a pending supplemental earning
  method: DELETE
  name: delete-supplemental-earning
  path: /v1/supplemental-earnings/{earningId}
- description: List input batches
  method: GET
  name: list-input-batches
  path: /v1/input-batches
- description: Submit a batch of payroll inputs
  method: POST
  name: create-input-batch
  path: /v1/input-batches
- description: Get a specific input batch
  method: GET
  name: get-input-batch
  path: /v1/input-batches/{batchId}
- description: List configured earning codes
  method: GET
  name: list-earning-codes
  path: /v1/earning-codes
- description: List configured deduction codes
  method: GET
  name: list-deduction-codes
  path: /v1/deduction-codes
- description: List supported tax jurisdictions
  method: GET
  name: list-tax-jurisdictions
  path: /v1/tax-jurisdictions
- description: Get a specific tax jurisdiction
  method: GET
  name: get-tax-jurisdiction
  path: /v1/tax-jurisdictions/{jurisdictionId}
- description: List tax filings
  method: GET
  name: list-tax-filings
  path: /v1/tax-filings
- description: Get a specific tax filing
  method: GET
  name: get-tax-filing
  path: /v1/tax-filings/{filingId}
personas: []
provider_name: Workday Payroll
provider_slug: workday-payroll
search_terms:
- get aggregated totals for a completed pay run
- list pay statements for a worker
- list tax withholdings for a worker
- get a specific tax withholding for a worker
- payroll adjustments and corrections
- list payroll adjustments
- worker time off inputs
- get a specific tax withholding
- submit a new w-4 or state tax election
- get worker tax election
- submit a batch of payroll inputs
- get a specific input batch
- get details of a specific payment transaction
- get worker payroll details
- individual tax filing
- submit a supplemental earning (bonus, commission, stipend)
- trigger payroll calculation
- create supplemental earning
- create worker tax election
- update one time payment
- get pay run worker result
- get details of a specific pay group
- update a pay run
- list earnings records for a worker
- delete a pending one-time payment
- tax
- list pay run payments
- workers in a pay group
- get details of a specific payroll run
- get payroll configuration details for a worker
- list tax calculation results for a pay run
- list earning codes
- list payment transactions generated by a pay run
- list one time payments
- list workers in a pay group
- worker deduction records
- list input batches
- pay group management
- list supplemental earnings
- list payroll runs with optional filters by status, pay group, or date
- get a specific tax election for a worker
- list tax filings
- get detailed payslip with earnings, deductions, and taxes
- get worker tax withholding
- get a specific tax filing
- list payments for a completed pay run
- update a tax withholding
- list worker earnings
- get worker tax summary
- get year-to-date tax summary
- workday
- get details of a specific one-time payment
- list payment elections for a worker
- list worker tax withholdings
- initiate a new payroll run
- list worker deductions
- manage a specific pay run
- update pay run
- get detailed result for a worker in a pay run
- list pay runs
- complete a pay run
- get tax jurisdiction
- list all supported tax jurisdictions
- earning code reference data
- payroll
- pay run result summaries
- list pay group workers
- worker tax summary
- worker tax withholdings
- deduction code reference data
- list configured deduction code types
- get details of a specific input batch
- individual supplemental earning
- list configured deduction codes
- enterprise
- get a specific payment transaction
- list pending and processed one-time payments
- delete one time payment
- list tax filing records for compliance reporting
- get pay group
- update a pending one-time payment
- supplemental earnings (bonuses, commissions)
- submit a time off input for payroll processing
- submit a batch of payroll inputs for bulk processing
- get a specific pay group
- create payroll adjustment
- submit a payroll correction or retroactive adjustment
- trigger payroll calculations for a pay run
- list direct deposit and payment preferences for a worker
- get a specific supplemental earning
- list tax withholding configurations for a worker
- worker payment elections
- saas
- list tax calculation results for a completed pay run
- list configured earning codes
- submit a new w-4 or state tax election for a worker
- submit a one-time payment (bonus, relocation, retroactive pay)
- complete pay run
- get a specific payslip
- tax results for a pay run
- calculate pay run
- worker payroll details
- list worker payslips
- get details of a specific supplemental earning
- individual tax jurisdiction
- payments generated by a pay run
- get a specific payroll adjustment
- initiate a new payroll run for a pay group
- worker tax elections
- compensation
- get aggregated results for a completed pay run
- get payroll adjustment
- list time off inputs for a worker
- create input batch
- worker-level results for a pay run
- worker earnings records
- list all configured pay groups
- list worker payment elections
- list tax elections for a worker
- update a tax withholding (filing status, allowances, exemptions)
- get supplemental earning
- list deductions for a worker
- get year-to-date tax summary for a worker
- tax jurisdiction reference data
- submit a payroll adjustment
- list tax jurisdictions
- individual payment
- create pay run
- one-time payment requests
- create worker time off input
- mark a pay run as completed
- delete a pending supplemental earning
- submit a time off input
- list worker tax elections
- list payslips for a worker
- list configured earning code types
- list worker time off inputs
- list earnings for a worker
- get pay run
- get one time payment
- list supported tax jurisdictions
- individual pay group
- list all pay groups
- individual payroll adjustment
- list pay run worker results
- get payroll details for a worker
- list payroll input batch submissions
- get details of a specific tax filing
- list all payroll runs with optional filters
- get a specific tax election
- individual tax election
- individual payslip
- individual one-time payment
- delete supplemental earning
- get tax filing
- list pay groups
- compliance
- list individual worker results for a pay run
- worker pay statements
- get a specific one-time payment
- list one-time payment requests
- get payment
- payroll run lifecycle management
- list supplemental earning submissions
- submit a supplemental earning
- individual tax withholding
- list w-4 and state tax election forms for a worker
- detailed worker result
- list payroll adjustment records
- list pay run tax results
- individual input batch
- tax filings
- human resources
- get worker payslip
- get details of a specific payroll adjustment
- get pay run details
- list deduction codes
- update the status or properties of a pay run
- batch payroll input submissions
- get a specific tax jurisdiction
- get pay run results
- create one time payment
- get detailed result for a specific worker in a pay run
- get details of a specific tax jurisdiction
- mark a pay run as completed and finalize payments
- update worker tax withholding
- submit a one-time payment
- get input batch
slug: payroll-processing
source_filename: payroll-processing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Workday Payroll Processing\n  description: Unified capability for end-to-end payroll processing workflows combining the Workday Payroll, Payroll Input,\n    Payroll Results, and Tax APIs. Supports HR administrators and payroll specialists running payroll cycles, managing worker\n    pay data, submitting adjustments, and reviewing payroll results and compliance data.\n  tags:\n  - Workday\n  - Payroll\n  - Compensation\n  - Human Resources\n  - Tax\n  - Compliance\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WORKDAY_PAYROLL_TOKEN: WORKDAY_PAYROLL_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: payroll\n    baseUri: https://api.workday.com/payroll/v1\n    description: Core API for managing payroll runs, pay groups, workers, earnings, and deductions.\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_PAYROLL_TOKEN}}'\n    resources:\n    - name: pay-runs\n      path:\
  \ /payRuns\n      description: Manage payroll processing runs\n      operations:\n      - name: list-pay-runs\n        method: GET\n        description: Retrieve a collection of payroll runs\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: payGroupId\n          in: query\n          type: string\n          required: false\n          description: Filter by pay group identifier\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by pay run status\n        - name: fromDate\n          in: query\n          type: string\n          required: false\n          description: Filter from date\n        - name: toDate\n          in: query\n          type:\
  \ string\n          required: false\n          description: Filter to date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-pay-run\n        method: POST\n        description: Initiate a new payroll run\n        body:\n          type: json\n          data:\n            payGroupId: '{{tools.payGroupId}}'\n            payPeriod: '{{tools.payPeriod}}'\n            runCategory: '{{tools.runCategory}}'\n            paymentDate: '{{tools.paymentDate}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pay-run-by-id\n      path: /payRuns/{payRunId}\n      description: Manage a specific pay run\n      operations:\n      - name: get-pay-run\n        method: GET\n        description: Retrieve details of a specific payroll run\n        inputParameters:\n        - name: payRunId\n          in: path\n          type:\
  \ string\n          required: true\n          description: Unique identifier for the pay run\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-pay-run\n        method: PATCH\n        description: Update the status or properties of a pay run\n        inputParameters:\n        - name: payRunId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for the pay run\n        body:\n          type: json\n          data:\n            status: '{{tools.status}}'\n            paymentDate: '{{tools.paymentDate}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pay-run-calculate\n      path: /payRuns/{payRunId}/calculate\n      description: Trigger payroll calculations\n      operations:\n      - name: calculate-pay-run\n        method: POST\n        description:\
  \ Trigger payroll calculations for a specific pay run\n        inputParameters:\n        - name: payRunId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for the pay run\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pay-run-complete\n      path: /payRuns/{payRunId}/complete\n      description: Complete a pay run\n      operations:\n      - name: complete-pay-run\n        method: POST\n        description: Mark a pay run as completed\n        inputParameters:\n        - name: payRunId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for the pay run\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pay-groups\n      path: /payGroups\n      description: Manage pay groups\n      operations:\n\
  \      - name: list-pay-groups\n        method: GET\n        description: Retrieve all configured pay groups\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pay-group-by-id\n      path: /payGroups/{payGroupId}\n      description: Access a specific pay group\n      operations:\n      - name: get-pay-group\n        method: GET\n        description: Retrieve details of a specific pay group\n        inputParameters:\n        - name: payGroupId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for the pay group\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pay-group-workers\n      path: /payGroups/{payGroupId}/workers\n      description: Workers in a pay group\n      operations:\n      - name: list-pay-group-workers\n        method: GET\n        description: Retrieve all workers assigned to a specific pay group\n        inputParameters:\n        - name: payGroupId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for the pay group\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: worker-payroll-details\n\
  \      path: /workers/{workerId}/payrollDetails\n      description: Worker payroll details\n      operations:\n      - name: get-worker-payroll-details\n        method: GET\n        description: Retrieve payroll-specific details for a worker\n        inputParameters:\n        - name: workerId\n          in: path\n          type: string\n          required: true\n          description: Unique worker identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: worker-earnings\n      path: /workers/{workerId}/earnings\n      description: Worker earnings\n      operations:\n      - name: list-worker-earnings\n        method: GET\n        description: Retrieve all earnings records for a specific worker\n        inputParameters:\n        - name: workerId\n          in: path\n          type: string\n          required: true\n          description: Unique worker identifier\n        - name: limit\n       \
  \   in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: worker-deductions\n      path: /workers/{workerId}/deductions\n      description: Worker deductions\n      operations:\n      - name: list-worker-deductions\n        method: GET\n        description: Retrieve all deductions for a specific worker\n        inputParameters:\n        - name: workerId\n          in: path\n          type: string\n          required: true\n          description: Unique worker identifier\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n\
  \          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: earning-codes\n      path: /earningCodes\n      description: Earning code configuration\n      operations:\n      - name: list-earning-codes\n        method: GET\n        description: Retrieve all configured earning codes\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deduction-codes\n      path: /deductionCodes\n      description: Deduction code configuration\n\
  \      operations:\n      - name: list-deduction-codes\n        method: GET\n        description: Retrieve all configured deduction codes\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: payroll-results\n    baseUri: https://api.workday.com/payroll-results/v1\n    description: API for payslips, payments, payment elections, and payroll summaries.\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_PAYROLL_TOKEN}}'\n    resources:\n    - name: worker-payslips\n      path: /workers/{workerId}/payslips\n      description: Worker payslip data\n      operations:\n\
  \      - name: list-worker-payslips\n        method: GET\n        description: Retrieve all payslips for a specific worker\n        inputParameters:\n        - name: workerId\n          in: path\n          type: string\n          required: true\n          description: Unique worker identifier\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: fromDate\n          in: query\n          type: string\n          required: false\n          description: Filter from date\n        - name: toDate\n          in: query\n          type: string\n          required: false\n          description: Filter to date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: worker-payslip-by-id\n\
  \      path: /workers/{workerId}/payslips/{payslipId}\n      description: Individual payslip\n      operations:\n      - name: get-worker-payslip\n        method: GET\n        description: Retrieve detailed payslip for a specific pay period\n        inputParameters:\n        - name: workerId\n          in: path\n          type: string\n          required: true\n          description: Unique worker identifier\n        - name: payslipId\n          in: path\n          type: string\n          required: true\n          description: Unique payslip identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pay-run-results\n      path: /payRuns/{payRunId}/results\n      description: Aggregated pay run results\n      operations:\n      - name: get-pay-run-results\n        method: GET\n        description: Retrieve aggregated results for a completed pay run\n        inputParameters:\n        - name: payRunId\n\
  \          in: path\n          type: string\n          required: true\n          description: Unique pay run identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pay-run-worker-results\n      path: /payRuns/{payRunId}/results/workers\n      description: Worker-level pay run results\n      operations:\n      - name: list-pay-run-worker-results\n        method: GET\n        description: Retrieve individual worker results for a completed pay run\n        inputParameters:\n        - name: payRunId\n          in: path\n          type: string\n          required: true\n          description: Unique pay run identifier\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pay-run-worker-result-by-id\n      path: /payRuns/{payRunId}/results/workers/{workerId}\n      description: Individual worker result for a pay run\n      operations:\n      - name: get-pay-run-worker-result\n        method: GET\n        description: Retrieve detailed worker results within a completed pay run\n        inputParameters:\n        - name: payRunId\n          in: path\n          type: string\n          required: true\n          description: Unique pay run identifier\n        - name: workerId\n          in: path\n          type: string\n          required: true\n          description: Unique worker identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pay-run-payments\n      path: /payRuns/{payRunId}/payments\n      description: Payments generated\
  \ by a pay run\n      operations:\n      - name: list-pay-run-payments\n        method: GET\n        description: Retrieve all payment transactions generated by a pay run\n        inputParameters:\n        - name: payRunId\n          in: path\n          type: string\n          required: true\n          description: Unique pay run identifier\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payment-by-id\n      path: /payments/{paymentId}\n      description: Individual payment transaction\n      operations:\n      - name: get-payment\n        method: GET\n        description: Retrieve details of a specific payment transaction\n\
  \        inputParameters:\n        - name: paymentId\n          in: path\n          type: string\n          required: true\n          description: Unique payment identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: worker-payment-elections\n      path: /workers/{workerId}/paymentElections\n      description: Worker payment election details\n      operations:\n      - name: list-worker-payment-elections\n        method: GET\n        description: Retrieve payment election details for a worker\n        inputParameters:\n        - name: workerId\n          in: path\n          type: string\n          required: true\n          description: Unique worker identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: payroll-input\n    baseUri: https://api.workday.com/payroll-input/v1\n    description:\
  \ API for submitting one-time payments, adjustments, supplemental earnings, and batch payroll inputs.\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_PAYROLL_TOKEN}}'\n    resources:\n    - name: one-time-payments\n      path: /oneTimePayments\n      description: One-time payment requests\n      operations:\n      - name: list-one-time-payments\n        method: GET\n        description: Retrieve all one-time payment requests\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: workerId\n          in: query\n          type: string\n          required: false\n          description: Filter by worker\n        - name: status\n          in: query\n          type: string\n          required: false\n     \
  \     description: Filter by status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-one-time-payment\n        method: POST\n        description: Submit a new one-time payment request\n        body:\n          type: json\n          data:\n            workerId: '{{tools.workerId}}'\n            earningCode: '{{tools.earningCode}}'\n            amount: '{{tools.amount}}'\n            currency: '{{tools.currency}}'\n            reason: '{{tools.reason}}'\n            effectiveDate: '{{tools.effectiveDate}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: one-time-payment-by-id\n      path: /oneTimePayments/{paymentId}\n      description: Individual one-time payment\n      operations:\n      - name: get-one-time-payment\n        method: GET\n        description: Retrieve details of a specific one-time\
  \ payment\n        inputParameters:\n        - name: paymentId\n          in: path\n          type: string\n          required: true\n          description: One-time payment identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-one-time-payment\n        method: PATCH\n        description: Update a pending one-time payment request\n        inputParameters:\n        - name: paymentId\n          in: path\n          type: string\n          required: true\n          description: One-time payment identifier\n        body:\n          type: json\n          data:\n            amount: '{{tools.amount}}'\n            reason: '{{tools.reason}}'\n            effectiveDate: '{{tools.effectiveDate}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-one-time-payment\n        method: DELETE\n       \
  \ description: Delete a pending one-time payment\n        inputParameters:\n        - name: paymentId\n          in: path\n          type: string\n          required: true\n          description: One-time payment identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: adjustments\n      path: /adjustments\n      description: Payroll adjustments\n      operations:\n      - name: list-payroll-adjustments\n        method: GET\n        description: Retrieve all payroll adjustment records\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: workerId\n          in: query\n          type: string\n          required: false\n     \
  \     description: Filter by worker\n        - name: adjustmentType\n          in: query\n          type: string\n          required: false\n          description: Filter by adjustment type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-payroll-adjustment\n        method: POST\n        description: Submit a payroll adjustment\n        body:\n          type: json\n          data:\n            workerId: '{{tools.workerId}}'\n            adjustmentType: '{{tools.adjustmentType}}'\n            originalPayRunId: '{{tools.originalPayRunId}}'\n            earningCode: '{{tools.earningCode}}'\n            deductionCode: '{{tools.deductionCode}}'\n            amount: '{{tools.amount}}'\n            currency: '{{tools.currency}}'\n            reason: '{{tools.reason}}'\n            effectiveDate: '{{tools.effectiveDate}}'\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: adjustment-by-id\n      path: /adjustments/{adjustmentId}\n      description: Individual payroll adjustment\n      operations:\n      - name: get-payroll-adjustment\n        method: GET\n        description: Retrieve details of a specific payroll adjustment\n        inputParameters:\n        - name: adjustmentId\n          in: path\n          type: string\n          required: true\n          description: Payroll adjustment identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: supplemental-earnings\n      path: /supplementalEarnings\n      description: Supplemental earnings submissions\n      operations:\n      - name: list-supplemental-earnings\n        method: GET\n        description: Retrieve all supplemental earning submissions\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n\
  \          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: workerId\n          in: query\n          type: string\n          required: false\n          description: Filter by worker\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-supplemental-earning\n        method: POST\n        description: Submit a supplemental earning for a worker\n        body:\n          type: json\n          data:\n            workerId: '{{tools.workerId}}'\n            earningCode: '{{tools.earningCode}}'\n            type: '{{tools.type}}'\n            amount: '{{tools.amount}}'\n            currency: '{{tools.currency}}'\n            effectiveDate: '{{tools.effectiveDate}}'\n            reason: '{{tools.reason}}'\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: supplemental-earning-by-id\n      path: /supplementalEarnings/{earningId}\n      description: Individual supplemental earning\n      operations:\n      - name: get-supplemental-earning\n        method: GET\n        description: Retrieve details of a specific supplemental earning\n        inputParameters:\n        - name: earningId\n          in: path\n          type: string\n          required: true\n          description: Supplemental earning identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-supplemental-earning\n        method: DELETE\n        description: Delete a pending supplemental earning\n        inputParameters:\n        - name: earningId\n          in: path\n          type: string\n          required: true\n          description: Supplemental earning identifier\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: input-batches\n      path: /inputBatches\n      description: Batch payroll input submissions\n      operations:\n      - name: list-input-batches\n        method: GET\n        description: Retrieve all payroll input batch submissions\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by batch status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-input-batch\n        method:\
  \ POST\n        description: Submit a batch of payroll input records\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            records: '{{tools.records}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: input-batch-by-id\n      path: /inputBatches/{batchId}\n      description: Individual input batch\n      operations:\n      - name: get-input-batch\n        method: GET\n        description: Retrieve details of a specific input batch\n        inputParameters:\n        - name: batchId\n          in: path\n          type: string\n          required: true\n          description: Input batch identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: worker-time-off-inputs\n      path: /workers/{workerId}/timeOffInputs\n      description: Worker time off inputs\n  \
  \    operations:\n      - name: list-worker-time-off-inputs\n        method: GET\n        description: Retrieve time off input records for a worker\n        inputParameters:\n        - name: workerId\n          in: path\n          type: string\n          required: true\n          description: Unique worker identifier\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-worker-time-off-input\n        method: POST\n        description: Submit a time off input for a worker\n        inputParameters:\n        - name: workerId\n          in: path\n          type: string\n          required: true\n          description:\
  \ Unique worker identifier\n        body:\n          type: json\n          data:\n            timeOffType: '{{tools.timeOffType}}'\n            startDate: '{{tools.startDate}}'\n            endDate: '{{tools.endDate}}'\n            hours: '{{tools.hours}}'\n            paid: '{{tools.paid}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: payroll-tax\n    baseUri: https://api.workday.com/tax/v1\n    description: API for tax withholdings, elections, calculations, jurisdictions, and filing.\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_PAYROLL_TOKEN}}'\n    resources:\n    - name: worker-tax-withholdings\n      path: /workers/{workerId}/taxWithholdings\n      description: Worker tax withholding configurations\n      operations:\n      - name: list-worker-tax-withholdings\n        method: GET\n        description: Retrieve all tax withholding configurations for\
  \ a worker\n        inputParameters:\n        - name: workerId\n          in: path\n          type: string\n          required: true\n          description: Unique worker identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: worker-tax-withholding-by-id\n      path: /workers/{workerId}/taxWithholdings/{withholdingId}\n      description: Individual tax withholding\n      operations:\n      - name: get-worker-tax-withholding\n        method: GET\n        description: Retrieve a specific tax withholding configuration\n        inputParameters:\n        - name: workerId\n          in: path\n          type: string\n          required: true\n          description: Unique worker identifier\n        - name: withholdingId\n          in: path\n          type: string\n          required: true\n          description: Tax withholding identifier\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: update-worker-tax-withholding\n        method: PATCH\n        description: Update a tax withholding configuration\n        inputParameters:\n        - name: workerId\n          in: path\n          type: string\n          required: true\n          description: Unique worker identifier\n        - name: withholdingId\n          in: path\n          type: string\n          required: true\n          description: Tax withholding identifier\n        body:\n          type: json\n          data:\n            filingStatus: '{{tools.filingStatus}}'\n            allowances: '{{tools.allowances}}'\n            additionalWithholding: '{{tools.additionalWithholding}}'\n            exempt: '{{tools.exempt}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: worker-tax-elections\n      path: /workers/{workerId}/taxElections\n      description:\
  \ Worker tax elections (W-4, state forms)\n      operations:\n      - name: list-worker-tax-elections\n        method: GET\n        description: Retrieve W-4 and state tax election forms for a worker\n        inputParameters:\n        - name: workerId\n          in: path\n          type: string\n          required: true\n          description: Unique worker identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-worker-tax-election\n        method: POST\n        description: Submit a new tax election for a worker\n        inputParameters:\n        - name: workerId\n          in: path\n          type: string\n          required: true\n          description: Unique worker identifier\n        body:\n          type: json\n          data:\n            formType: '{{tools.formType}}'\n            jurisdictionId: '{{tools.jurisdictionId}}'\n            filingStatus: '{{tools.filingStatus}}'\n\
  \            multipleJobs: '{{tools.multipleJobs}}'\n            dependentsAmount: '{{tools.dependentsAmount}}'\n            otherIncome: '{{tools.otherIncome}}'\n            deductions: '{{tools.deductions}}'\n            additionalWithholding: '{{tools.additionalWithholding}}'\n            effectiveDate: '{{tools.effectiveDate}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: worker-tax-election-by-id\n      path: /workers/{workerId}/taxElections/{electionId}\n      description: Individual tax election\n      operations:\n      - name: get-worker-tax-election\n        method: GET\n        description: Retrieve a specific tax election\n        inputParameters:\n        - name: workerId\n          in: path\n          type: string\n          required: true\n          description: Unique worker identifier\n        - name: electionId\n          in: path\n          type: string\n          required:\
  \ true\n          description: Tax election identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tax-jurisdictions\n      path: /taxJurisdictions\n      description: Tax jurisdiction information\n      operations:\n      - name: list-tax-jurisdictions\n        method: GET\n        description: Retrieve all configured tax jurisdictions\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: level\n          i\n\n# --- truncated at 32 KB (70 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/workday-payroll/refs/heads/main/capabilities/payroll-processing.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/workday-payroll/refs/heads/main/capabilities/payroll-processing.yaml
tags:
- Workday
- Payroll
- Compensation
- Human Resources
- Tax
- Compliance
tools:
- description: List payroll runs with optional filters by status, pay group, or date
  hints:
    idempotent: true
    readOnly: true
  name: list-pay-runs
- description: Get details of a specific payroll run
  hints:
    idempotent: true
    readOnly: true
  name: get-pay-run
- description: Initiate a new payroll run for a pay group
  hints:
    idempotent: false
    readOnly: false
  name: create-pay-run
- description: Update the status or properties of a pay run
  hints:
    idempotent: true
    readOnly: false
  name: update-pay-run
- description: Trigger payroll calculations for a pay run
  hints:
    destructive: true
    idempotent: false
    readOnly: false
  name: calculate-pay-run
- description: Mark a pay run as completed and finalize payments
  hints:
    destructive: true
    idempotent: false
    readOnly: false
  name: complete-pay-run
- description: Get aggregated totals for a completed pay run
  hints:
    idempotent: true
    readOnly: true
  name: get-pay-run-results
- description: List individual worker results for a pay run
  hints:
    idempotent: true
    readOnly: true
  name: list-pay-run-worker-results
- description: Get detailed result for a specific worker in a pay run
  hints:
    idempotent: true
    readOnly: true
  name: get-pay-run-worker-result
- description: List payment transactions generated by a pay run
  hints:
    idempotent: true
    readOnly: true
  name: list-pay-run-payments
- description: Get details of a specific payment transaction
  hints:
    idempotent: true
    readOnly: true
  name: get-payment
- description: List tax calculation results for a completed pay run
  hints:
    idempotent: true
    readOnly: true
  name: list-pay-run-tax-results
- description: List all configured pay groups
  hints:
    idempotent: true
    readOnly: true
  name: list-pay-groups
- description: Get details of a specific pay group
  hints:
    idempotent: true
    readOnly: true
  name: get-pay-group
- description: List workers in a pay group
  hints:
    idempotent: true
    readOnly: true
  name: list-pay-group-workers
- description: Get payroll configuration details for a worker
  hints:
    idempotent: true
    readOnly: true
  name: get-worker-payroll-details
- description: List pay statements for a worker
  hints:
    idempotent: true
    readOnly: true
  name: list-worker-payslips
- description: Get detailed payslip with earnings, deductions, and taxes
  hints:
    idempotent: true
    readOnly: true
  name: get-worker-payslip
- description: List direct deposit and payment preferences for a worker
  hints:
    idempotent: true
    readOnly: true
  name: list-worker-payment-elections
- description: List earnings records for a worker
  hints:
    idempotent: true
    readOnly: true
  name: list-worker-earnings
- description: List deductions for a worker
  hints:
    idempotent: true
    readOnly: true
  name: list-worker-deductions
- description: List tax withholding configurations for a worker
  hints:
    idempotent: true
    readOnly: true
  name: list-worker-tax-withholdings
- description: Get a specific tax withholding for a worker
  hints:
    idempotent: true
    readOnly: true
  name: get-worker-tax-withholding
- description: Update a tax withholding (filing status, allowances, exemptions)
  hints:
    idempotent: true
    readOnly: false
  name: update-worker-tax-withholding
- description: List W-4 and state tax election forms for a worker
  hints:
    idempotent: true
    readOnly: true
  name: list-worker-tax-elections
- description: Get a specific tax election for a worker
  hints:
    idempotent: true
    readOnly: true
  name: get-worker-tax-election
- description: Submit a new W-4 or state tax election for a worker
  hints:
    idempotent: false
    readOnly: false
  name: create-worker-tax-election
- description: Get year-to-date tax summary for a worker
  hints:
    idempotent: true
    readOnly: true
  name: get-worker-tax-summary
- description: List time off inputs for a worker
  hints:
    idempotent: true
    readOnly: true
  name: list-worker-time-off-inputs
- description: Submit a time off input for payroll processing
  hints:
    idempotent: false
    readOnly: false
  name: create-worker-time-off-input
- description: List pending and processed one-time payments
  hints:
    idempotent: true
    readOnly: true
  name: list-one-time-payments
- description: Get details of a specific one-time payment
  hints:
    idempotent: true
    readOnly: true
  name: get-one-time-payment
- description: Submit a one-time payment (bonus, relocation, retroactive pay)
  hints:
    idempotent: false
    readOnly: false
  name: create-one-time-payment
- description: Update a pending one-time payment
  hints:
    idempotent: true
    readOnly: false
  name: update-one-time-payment
- description: Delete a pending one-time payment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-one-time-payment
- description: List payroll adjustment records
  hints:
    idempotent: true
    readOnly: true
  name: list-payroll-adjustments
- description: Get details of a specific payroll adjustment
  hints:
    idempotent: true
    readOnly: true
  name: get-payroll-adjustment
- description: Submit a payroll correction or retroactive adjustment
  hints:
    idempotent: false
    readOnly: false
  name: create-payroll-adjustment
- description: List supplemental earning submissions
  hints:
    idempotent: true
    readOnly: true
  name: list-supplemental-earnings
- description: Get details of a specific supplemental earning
  hints:
    idempotent: true
    readOnly: true
  name: get-supplemental-earning
- description: Submit a supplemental earning (bonus, commission, stipend)
  hints:
    idempotent: false
    readOnly: false
  name: create-supplemental-earning
- description: Delete a pending supplemental earning
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-supplemental-earning
- description: List payroll input batch submissions
  hints:
    idempotent: true
    readOnly: true
  name: list-input-batches
- description: Get details of a specific input batch
  hints:
    idempotent: true
    readOnly: true
  name: get-input-batch
- description: Submit a batch of payroll inputs for bulk processing
  hints:
    idempotent: false
    readOnly: false
  name: create-input-batch
- description: List configured earning code types
  hints:
    idempotent: true
    readOnly: true
  name: list-earning-codes
- description: List configured deduction code types
  hints:
    idempotent: true
    readOnly: true
  name: list-deduction-codes
- description: List all supported tax jurisdictions
  hints:
    idempotent: true
    readOnly: true
  name: list-tax-jurisdictions
- description: Get details of a specific tax jurisdiction
  hints:
    idempotent: true
    readOnly: true
  name: get-tax-jurisdiction
- description: List tax filing records for compliance reporting
  hints:
    idempotent: true
    readOnly: true
  name: list-tax-filings
- description: Get details of a specific tax filing
  hints:
    idempotent: true
    readOnly: true
  name: get-tax-filing
---
