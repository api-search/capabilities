---
categories: []
consumed_apis:
- payroll
- payroll-results
- payroll-input
- payroll-tax
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
- tax filings
- payroll run lifecycle management
- deduction code reference data
- one-time payment requests
- update a pending one-time payment
- earning code reference data
- get detailed payslip with earnings, deductions, and taxes
- individual tax withholding
- list pending and processed one-time payments
- list configured earning code types
- calculate pay run
- worker-level results for a pay run
- submit a one-time payment
- delete supplemental earning
- submit a supplemental earning
- list pay run payments
- list supplemental earning submissions
- list earnings records for a worker
- update a pay run
- get details of a specific tax filing
- worker tax summary
- get worker payslip
- list pay runs
- list tax elections for a worker
- list all supported tax jurisdictions
- get input batch
- get a specific tax election for a worker
- human resources
- delete a pending supplemental earning
- list payroll adjustment records
- create pay run
- get a specific tax withholding
- get pay run worker result
- submit a time off input
- get a specific tax jurisdiction
- list tax jurisdictions
- submit a payroll correction or retroactive adjustment
- get a specific supplemental earning
- create worker tax election
- get details of a specific payroll run
- get worker tax election
- individual payslip
- payroll adjustments and corrections
- list supplemental earnings
- get a specific payroll adjustment
- individual input batch
- get payroll adjustment
- submit a batch of payroll inputs
- delete one time payment
- update one time payment
- update the status or properties of a pay run
- list worker earnings
- list all configured pay groups
- saas
- list tax filings
- submit a supplemental earning (bonus, commission, stipend)
- individual tax filing
- list pay statements for a worker
- submit a batch of payroll inputs for bulk processing
- list workers in a pay group
- individual supplemental earning
- get payroll details for a worker
- get a specific tax withholding for a worker
- list worker tax withholdings
- initiate a new payroll run
- get worker payroll details
- individual payroll adjustment
- complete pay run
- list worker tax elections
- update pay run
- pay group management
- list worker time off inputs
- create input batch
- list supported tax jurisdictions
- get aggregated totals for a completed pay run
- list payslips for a worker
- list pay run tax results
- get details of a specific payment transaction
- worker earnings records
- batch payroll input submissions
- list all payroll runs with optional filters
- mark a pay run as completed and finalize payments
- list payroll adjustments
- create payroll adjustment
- individual pay group
- initiate a new payroll run for a pay group
- get payment
- trigger payroll calculation
- detailed worker result
- submit a new w-4 or state tax election
- list deduction codes
- list tax withholding configurations for a worker
- list configured deduction code types
- list pay group workers
- submit a one-time payment (bonus, relocation, retroactive pay)
- get details of a specific input batch
- create supplemental earning
- get pay run
- get pay group
- list pay groups
- workday
- get worker tax withholding
- get details of a specific pay group
- list one-time payment requests
- submit a time off input for payroll processing
- list payment transactions generated by a pay run
- list worker deductions
- workers in a pay group
- delete a pending one-time payment
- payments generated by a pay run
- get details of a specific payroll adjustment
- worker deduction records
- worker payment elections
- get a specific one-time payment
- get a specific payslip
- list one time payments
- list time off inputs for a worker
- update a tax withholding (filing status, allowances, exemptions)
- get details of a specific supplemental earning
- worker tax elections
- get worker tax summary
- mark a pay run as completed
- compliance
- get pay run details
- list tax filing records for compliance reporting
- get supplemental earning
- payroll
- list earnings for a worker
- update a tax withholding
- list earning codes
- get pay run results
- get details of a specific one-time payment
- worker time off inputs
- list worker payment elections
- tax jurisdiction reference data
- individual payment
- worker payroll details
- get details of a specific tax jurisdiction
- get tax jurisdiction
- get tax filing
- submit a new w-4 or state tax election for a worker
- list payment elections for a worker
- get year-to-date tax summary for a worker
- list tax withholdings for a worker
- get year-to-date tax summary
- get detailed result for a worker in a pay run
- compensation
- complete a pay run
- submit a payroll adjustment
- supplemental earnings (bonuses, commissions)
- tax results for a pay run
- individual tax jurisdiction
- individual tax election
- list tax calculation results for a pay run
- create worker time off input
- list configured deduction codes
- get payroll configuration details for a worker
- get a specific input batch
- get a specific tax filing
- list payroll input batch submissions
- get a specific pay group
- list payroll runs with optional filters by status, pay group, or date
- get a specific payment transaction
- list direct deposit and payment preferences for a worker
- enterprise
- trigger payroll calculations for a pay run
- list all pay groups
- manage a specific pay run
- list pay run worker results
- list input batches
- list configured earning codes
- list tax calculation results for a completed pay run
- list payments for a completed pay run
- worker tax withholdings
- update worker tax withholding
- list deductions for a worker
- get detailed result for a specific worker in a pay run
- get aggregated results for a completed pay run
- list w-4 and state tax election forms for a worker
- list worker payslips
- pay run result summaries
- worker pay statements
- get a specific tax election
- tax
- individual one-time payment
- get one time payment
- create one time payment
- list individual worker results for a pay run
slug: payroll-processing
source_filename: payroll-processing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Workday Payroll Processing\"\n  description: >-\n    Unified capability for end-to-end payroll processing workflows combining\n    the Workday Payroll, Payroll Input, Payroll Results, and Tax APIs. Supports\n    HR administrators and payroll specialists running payroll cycles, managing\n    worker pay data, submitting adjustments, and reviewing payroll results and\n    compliance data.\n  tags:\n    - Workday\n    - Payroll\n    - Compensation\n    - Human Resources\n    - Tax\n    - Compliance\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WORKDAY_PAYROLL_TOKEN: WORKDAY_PAYROLL_TOKEN\n\ncapability:\n  consumes:\n    - import: payroll\n      location: ./shared/payroll.yaml\n    - import: payroll-results\n      location: ./shared/payroll-results.yaml\n    - import: payroll-input\n      location: ./shared/payroll-input.yaml\n    - import: payroll-tax\n      location: ./shared/payroll-tax.yaml\n\
  \n  exposes:\n    - type: rest\n      port: 8080\n      namespace: payroll-processing-api\n      description: \"Unified REST API for Workday payroll processing workflows.\"\n      resources:\n        - path: /v1/pay-runs\n          name: pay-runs\n          description: \"Payroll run lifecycle management\"\n          operations:\n            - method: GET\n              name: list-pay-runs\n              description: \"List all payroll runs with optional filters\"\n              call: \"payroll.list-pay-runs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-pay-run\n              description: \"Initiate a new payroll run\"\n              call: \"payroll.create-pay-run\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pay-runs/{payRunId}\n          name: pay-run-by-id\n          description: \"Manage a specific\
  \ pay run\"\n          operations:\n            - method: GET\n              name: get-pay-run\n              description: \"Get pay run details\"\n              call: \"payroll.get-pay-run\"\n              with:\n                payRunId: \"rest.payRunId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-pay-run\n              description: \"Update a pay run\"\n              call: \"payroll.update-pay-run\"\n              with:\n                payRunId: \"rest.payRunId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pay-runs/{payRunId}/calculate\n          name: pay-run-calculate\n          description: \"Trigger payroll calculation\"\n          operations:\n            - method: POST\n              name: calculate-pay-run\n              description: \"Trigger payroll calculations for a pay run\"\n     \
  \         call: \"payroll.calculate-pay-run\"\n              with:\n                payRunId: \"rest.payRunId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pay-runs/{payRunId}/complete\n          name: pay-run-complete\n          description: \"Complete a pay run\"\n          operations:\n            - method: POST\n              name: complete-pay-run\n              description: \"Mark a pay run as completed\"\n              call: \"payroll.complete-pay-run\"\n              with:\n                payRunId: \"rest.payRunId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pay-runs/{payRunId}/results\n          name: pay-run-results\n          description: \"Pay run result summaries\"\n          operations:\n            - method: GET\n              name: get-pay-run-results\n              description: \"Get aggregated results for a completed\
  \ pay run\"\n              call: \"payroll-results.get-pay-run-results\"\n              with:\n                payRunId: \"rest.payRunId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pay-runs/{payRunId}/worker-results\n          name: pay-run-worker-results\n          description: \"Worker-level results for a pay run\"\n          operations:\n            - method: GET\n              name: list-pay-run-worker-results\n              description: \"List individual worker results for a pay run\"\n              call: \"payroll-results.list-pay-run-worker-results\"\n              with:\n                payRunId: \"rest.payRunId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pay-runs/{payRunId}/worker-results/{workerId}\n          name: pay-run-worker-result-by-id\n          description: \"Detailed worker result\"\n          operations:\n   \
  \         - method: GET\n              name: get-pay-run-worker-result\n              description: \"Get detailed result for a worker in a pay run\"\n              call: \"payroll-results.get-pay-run-worker-result\"\n              with:\n                payRunId: \"rest.payRunId\"\n                workerId: \"rest.workerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pay-runs/{payRunId}/payments\n          name: pay-run-payments\n          description: \"Payments generated by a pay run\"\n          operations:\n            - method: GET\n              name: list-pay-run-payments\n              description: \"List payments for a completed pay run\"\n              call: \"payroll-results.list-pay-run-payments\"\n              with:\n                payRunId: \"rest.payRunId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pay-runs/{payRunId}/tax-results\n\
  \          name: pay-run-tax-results\n          description: \"Tax results for a pay run\"\n          operations:\n            - method: GET\n              name: list-pay-run-tax-results\n              description: \"List tax calculation results for a pay run\"\n              call: \"payroll-tax.list-pay-run-tax-results\"\n              with:\n                payRunId: \"rest.payRunId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pay-groups\n          name: pay-groups\n          description: \"Pay group management\"\n          operations:\n            - method: GET\n              name: list-pay-groups\n              description: \"List all pay groups\"\n              call: \"payroll.list-pay-groups\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pay-groups/{payGroupId}\n          name: pay-group-by-id\n          description: \"Individual\
  \ pay group\"\n          operations:\n            - method: GET\n              name: get-pay-group\n              description: \"Get a specific pay group\"\n              call: \"payroll.get-pay-group\"\n              with:\n                payGroupId: \"rest.payGroupId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pay-groups/{payGroupId}/workers\n          name: pay-group-workers\n          description: \"Workers in a pay group\"\n          operations:\n            - method: GET\n              name: list-pay-group-workers\n              description: \"List workers in a pay group\"\n              call: \"payroll.list-pay-group-workers\"\n              with:\n                payGroupId: \"rest.payGroupId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/payments/{paymentId}\n          name: payment-by-id\n          description: \"Individual\
  \ payment\"\n          operations:\n            - method: GET\n              name: get-payment\n              description: \"Get a specific payment transaction\"\n              call: \"payroll-results.get-payment\"\n              with:\n                paymentId: \"rest.paymentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workers/{workerId}/payroll-details\n          name: worker-payroll-details\n          description: \"Worker payroll details\"\n          operations:\n            - method: GET\n              name: get-worker-payroll-details\n              description: \"Get payroll details for a worker\"\n              call: \"payroll.get-worker-payroll-details\"\n              with:\n                workerId: \"rest.workerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workers/{workerId}/payslips\n          name: worker-payslips\n\
  \          description: \"Worker pay statements\"\n          operations:\n            - method: GET\n              name: list-worker-payslips\n              description: \"List payslips for a worker\"\n              call: \"payroll-results.list-worker-payslips\"\n              with:\n                workerId: \"rest.workerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workers/{workerId}/payslips/{payslipId}\n          name: worker-payslip-by-id\n          description: \"Individual payslip\"\n          operations:\n            - method: GET\n              name: get-worker-payslip\n              description: \"Get a specific payslip\"\n              call: \"payroll-results.get-worker-payslip\"\n              with:\n                workerId: \"rest.workerId\"\n                payslipId: \"rest.payslipId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n     \
  \   - path: /v1/workers/{workerId}/payment-elections\n          name: worker-payment-elections\n          description: \"Worker payment elections\"\n          operations:\n            - method: GET\n              name: list-worker-payment-elections\n              description: \"List payment elections for a worker\"\n              call: \"payroll-results.list-worker-payment-elections\"\n              with:\n                workerId: \"rest.workerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workers/{workerId}/earnings\n          name: worker-earnings\n          description: \"Worker earnings records\"\n          operations:\n            - method: GET\n              name: list-worker-earnings\n              description: \"List earnings for a worker\"\n              call: \"payroll.list-worker-earnings\"\n              with:\n                workerId: \"rest.workerId\"\n              outputParameters:\n      \
  \          - type: object\n                  mapping: \"$.\"\n        - path: /v1/workers/{workerId}/deductions\n          name: worker-deductions\n          description: \"Worker deduction records\"\n          operations:\n            - method: GET\n              name: list-worker-deductions\n              description: \"List deductions for a worker\"\n              call: \"payroll.list-worker-deductions\"\n              with:\n                workerId: \"rest.workerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workers/{workerId}/tax-withholdings\n          name: worker-tax-withholdings\n          description: \"Worker tax withholdings\"\n          operations:\n            - method: GET\n              name: list-worker-tax-withholdings\n              description: \"List tax withholdings for a worker\"\n              call: \"payroll-tax.list-worker-tax-withholdings\"\n              with:\n                workerId:\
  \ \"rest.workerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workers/{workerId}/tax-withholdings/{withholdingId}\n          name: worker-tax-withholding-by-id\n          description: \"Individual tax withholding\"\n          operations:\n            - method: GET\n              name: get-worker-tax-withholding\n              description: \"Get a specific tax withholding\"\n              call: \"payroll-tax.get-worker-tax-withholding\"\n              with:\n                workerId: \"rest.workerId\"\n                withholdingId: \"rest.withholdingId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-worker-tax-withholding\n              description: \"Update a tax withholding\"\n              call: \"payroll-tax.update-worker-tax-withholding\"\n              with:\n                workerId: \"rest.workerId\"\
  \n                withholdingId: \"rest.withholdingId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workers/{workerId}/tax-elections\n          name: worker-tax-elections\n          description: \"Worker tax elections\"\n          operations:\n            - method: GET\n              name: list-worker-tax-elections\n              description: \"List tax elections for a worker\"\n              call: \"payroll-tax.list-worker-tax-elections\"\n              with:\n                workerId: \"rest.workerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-worker-tax-election\n              description: \"Submit a new W-4 or state tax election\"\n              call: \"payroll-tax.create-worker-tax-election\"\n              with:\n                workerId: \"rest.workerId\"\n              outputParameters:\n \
  \               - type: object\n                  mapping: \"$.\"\n        - path: /v1/workers/{workerId}/tax-elections/{electionId}\n          name: worker-tax-election-by-id\n          description: \"Individual tax election\"\n          operations:\n            - method: GET\n              name: get-worker-tax-election\n              description: \"Get a specific tax election\"\n              call: \"payroll-tax.get-worker-tax-election\"\n              with:\n                workerId: \"rest.workerId\"\n                electionId: \"rest.electionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workers/{workerId}/tax-summary\n          name: worker-tax-summary\n          description: \"Worker tax summary\"\n          operations:\n            - method: GET\n              name: get-worker-tax-summary\n              description: \"Get year-to-date tax summary\"\n              call: \"payroll-tax.get-worker-tax-summary\"\
  \n              with:\n                workerId: \"rest.workerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workers/{workerId}/time-off-inputs\n          name: worker-time-off-inputs\n          description: \"Worker time off inputs\"\n          operations:\n            - method: GET\n              name: list-worker-time-off-inputs\n              description: \"List time off inputs for a worker\"\n              call: \"payroll-input.list-worker-time-off-inputs\"\n              with:\n                workerId: \"rest.workerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-worker-time-off-input\n              description: \"Submit a time off input\"\n              call: \"payroll-input.create-worker-time-off-input\"\n              with:\n                workerId: \"rest.workerId\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/one-time-payments\n          name: one-time-payments\n          description: \"One-time payment requests\"\n          operations:\n            - method: GET\n              name: list-one-time-payments\n              description: \"List one-time payment requests\"\n              call: \"payroll-input.list-one-time-payments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-one-time-payment\n              description: \"Submit a one-time payment\"\n              call: \"payroll-input.create-one-time-payment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/one-time-payments/{paymentId}\n          name: one-time-payment-by-id\n          description: \"Individual one-time payment\"\n          operations:\n            - method:\
  \ GET\n              name: get-one-time-payment\n              description: \"Get a specific one-time payment\"\n              call: \"payroll-input.get-one-time-payment\"\n              with:\n                paymentId: \"rest.paymentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-one-time-payment\n              description: \"Update a pending one-time payment\"\n              call: \"payroll-input.update-one-time-payment\"\n              with:\n                paymentId: \"rest.paymentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-one-time-payment\n              description: \"Delete a pending one-time payment\"\n              call: \"payroll-input.delete-one-time-payment\"\n              with:\n                paymentId: \"rest.paymentId\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/adjustments\n          name: adjustments\n          description: \"Payroll adjustments and corrections\"\n          operations:\n            - method: GET\n              name: list-payroll-adjustments\n              description: \"List payroll adjustments\"\n              call: \"payroll-input.list-payroll-adjustments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-payroll-adjustment\n              description: \"Submit a payroll adjustment\"\n              call: \"payroll-input.create-payroll-adjustment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/adjustments/{adjustmentId}\n          name: adjustment-by-id\n          description: \"Individual payroll adjustment\"\n          operations:\n            - method: GET\n\
  \              name: get-payroll-adjustment\n              description: \"Get a specific payroll adjustment\"\n              call: \"payroll-input.get-payroll-adjustment\"\n              with:\n                adjustmentId: \"rest.adjustmentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/supplemental-earnings\n          name: supplemental-earnings\n          description: \"Supplemental earnings (bonuses, commissions)\"\n          operations:\n            - method: GET\n              name: list-supplemental-earnings\n              description: \"List supplemental earnings\"\n              call: \"payroll-input.list-supplemental-earnings\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-supplemental-earning\n              description: \"Submit a supplemental earning\"\n              call: \"payroll-input.create-supplemental-earning\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/supplemental-earnings/{earningId}\n          name: supplemental-earning-by-id\n          description: \"Individual supplemental earning\"\n          operations:\n            - method: GET\n              name: get-supplemental-earning\n              description: \"Get a specific supplemental earning\"\n              call: \"payroll-input.get-supplemental-earning\"\n              with:\n                earningId: \"rest.earningId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-supplemental-earning\n              description: \"Delete a pending supplemental earning\"\n              call: \"payroll-input.delete-supplemental-earning\"\n              with:\n                earningId: \"rest.earningId\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n        - path: /v1/input-batches\n          name: input-batches\n          description: \"Batch payroll input submissions\"\n          operations:\n            - method: GET\n              name: list-input-batches\n              description: \"List input batches\"\n              call: \"payroll-input.list-input-batches\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-input-batch\n              description: \"Submit a batch of payroll inputs\"\n              call: \"payroll-input.create-input-batch\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/input-batches/{batchId}\n          name: input-batch-by-id\n          description: \"Individual input batch\"\n          operations:\n            - method: GET\n              name: get-input-batch\n              description: \"\
  Get a specific input batch\"\n              call: \"payroll-input.get-input-batch\"\n              with:\n                batchId: \"rest.batchId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/earning-codes\n          name: earning-codes\n          description: \"Earning code reference data\"\n          operations:\n            - method: GET\n              name: list-earning-codes\n              description: \"List configured earning codes\"\n              call: \"payroll.list-earning-codes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/deduction-codes\n          name: deduction-codes\n          description: \"Deduction code reference data\"\n          operations:\n            - method: GET\n              name: list-deduction-codes\n              description: \"List configured deduction codes\"\n              call: \"payroll.list-deduction-codes\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tax-jurisdictions\n          name: tax-jurisdictions\n          description: \"Tax jurisdiction reference data\"\n          operations:\n            - method: GET\n              name: list-tax-jurisdictions\n              description: \"List supported tax jurisdictions\"\n              call: \"payroll-tax.list-tax-jurisdictions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tax-jurisdictions/{jurisdictionId}\n          name: tax-jurisdiction-by-id\n          description: \"Individual tax jurisdiction\"\n          operations:\n            - method: GET\n              name: get-tax-jurisdiction\n              description: \"Get a specific tax jurisdiction\"\n              call: \"payroll-tax.get-tax-jurisdiction\"\n              with:\n                jurisdictionId: \"rest.jurisdictionId\"\n\
  \              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tax-filings\n          name: tax-filings\n          description: \"Tax filings\"\n          operations:\n            - method: GET\n              name: list-tax-filings\n              description: \"List tax filings\"\n              call: \"payroll-tax.list-tax-filings\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tax-filings/{filingId}\n          name: tax-filing-by-id\n          description: \"Individual tax filing\"\n          operations:\n            - method: GET\n              name: get-tax-filing\n              description: \"Get a specific tax filing\"\n              call: \"payroll-tax.get-tax-filing\"\n              with:\n                filingId: \"rest.filingId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n\
  \      port: 9090\n      namespace: payroll-processing-mcp\n      transport: http\n      description: \"MCP server for AI-assisted payroll processing and compensation management.\"\n      tools:\n        - name: list-pay-runs\n          description: \"List payroll runs with optional filters by status, pay group, or date\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"payroll.list-pay-runs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-pay-run\n          description: \"Get details of a specific payroll run\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"payroll.get-pay-run\"\n          with:\n            payRunId: \"tools.payRunId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-pay-run\n          description: \"Initiate a new payroll run for a pay group\"\n     \
  \     hints:\n            readOnly: false\n            idempotent: false\n          call: \"payroll.create-pay-run\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-pay-run\n          description: \"Update the status or properties of a pay run\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"payroll.update-pay-run\"\n          with:\n            payRunId: \"tools.payRunId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: calculate-pay-run\n          description: \"Trigger payroll calculations for a pay run\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: false\n          call: \"payroll.calculate-pay-run\"\n          with:\n            payRunId: \"tools.payRunId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name:\
  \ complete-pay-run\n          description: \"Mark a pay run as completed and finalize payments\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: false\n          call: \"payroll.complete-pay-run\"\n          with:\n            payRunId: \"tools.payRunId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-pay-run-results\n          description: \"Get aggregated totals for a completed pay run\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"payroll-results.get-pay-run-results\"\n          with:\n            payRunId: \"tools.payRunId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-pay-run-worker-results\n          description: \"List individual worker results for a pay run\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call:\
  \ \"payroll-results.list-pay-run-worker-results\"\n          with:\n            payRunId: \"tools.payRunId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-pay-run-worker-result\n          description: \"Get detailed result for a specific worker in a pay run\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"payroll-results.get-pay-run-worker-result\"\n          with:\n            payRunId: \"tools.payRunId\"\n            workerId: \"tools.workerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-pay-run-payments\n          description: \"List payment transactions generated by a pay run\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"payroll-results.list-pay-run-payments\"\n          with:\n            payRunId: \"tools.payRunId\"\n          outputParameters:\n        \
  \    - type: object\n              mapping: \"$.\"\n        - name: get-payment\n          description: \"Get details of a specific payment transaction\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"payroll-results.get-payment\"\n          with:\n            paymentId: \"tools.paymentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-pay-run-tax-results\n          description: \"List tax calculation results for a completed pay run\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"payroll-tax.list-pay-run-tax-results\"\n          with:\n            payRunId: \"tools.payRunId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-pay-groups\n          description: \"List all configured pay groups\"\n          hints:\n            readOnly: true\n            idempotent: true\n\
  \          call: \"payroll.list-pay-groups\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-pay-group\n          description: \"Get details of a specific pay group\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"payroll.get-pay-group\"\n          with:\n            payGroupId: \"tools.payGroupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-pay-group-workers\n          description: \"List workers in a pay group\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"payroll.list-pay-group-workers\"\n          with:\n            payGroupId: \"tools.payGroupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-worker-payroll-details\n          description: \"Get payroll configuration details for a worker\"\n      \
  \    hints:\n            readOnly: true\n            idempotent: true\n          call: \"payroll.get-worker-payroll-details\"\n          with:\n            workerId: \"tools.workerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-worker-payslips\n          description: \"List pay statements for a worker\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"payroll-results.list-worker-payslips\"\n          with:\n            workerId: \"tools.workerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-worker-payslip\n          description: \"Get detailed payslip with earnings, deductions, and taxes\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"payroll-results.get-worker-payslip\"\n          with:\n            workerId: \"tools.workerId\"\n            payslipId: \"tools.payslipId\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-worker-payment-elections\n          description: \"List direct deposit and payment preferences for a worker\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"payroll-results.list-worker-payment-elections\"\n          with:\n            workerId: \"tools.workerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-worker-earnings\n          description: \"List earnings records for a worker\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"payroll.list-worker-earnings\"\n          with:\n            workerId: \"tools.workerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-worker-deductions\n          description: \"List deductions for a worker\"\n          hints:\n\
  \            readOnly: true\n            idempotent: true\n          call: \"payroll.list-worker-deductions\"\n          with:\n            workerId: \"tools.workerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-worker-tax-withholdings\n          description: \"List tax withholding configurations for a worker\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"payroll-tax.list-worker-tax-withholdings\"\n          with:\n            workerId: \"tools.workerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-worker-tax-withholding\n          description: \"Get a specific tax withholding for a worker\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"payroll-tax.get-worker-tax-withholding\"\n          with:\n            workerId: \"tools.workerId\"\n            withholdingId:\
  \ \"tools.withholdingId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-worker-tax-withholding\n          description: \"Update a tax withh\n\n# --- truncated at 32 KB (41 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/workday-payroll/refs/heads/main/capabilities/payroll-processing.yaml\n"
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
