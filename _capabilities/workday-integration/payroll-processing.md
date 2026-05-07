---
categories: []
consumed_apis: []
description: End-to-end payroll processing workflow combining payroll calculations, time tracking, absence management, compensation, and tax management across US, Australia, Canada, France, and UK payroll modules.
layout: capability
name: Workday Payroll Processing Workflow
operations:
- description: ''
  method: GET
  name: list-pay-groups
  path: /v1/pay-groups
- description: ''
  method: GET
  name: list-payroll-results
  path: /v1/payroll-results
personas: []
provider_name: Workday Integration
provider_slug: workday-integration
search_terms:
- time tracking
- workday
- list pay groups
- list worker time entries for payroll processing
- hcm
- integration
- list employee leave requests affecting payroll
- finance
- list leave requests
- payroll
- list pay components
- enterprise
- compensation
- tax
- list payroll calculation results
- list payroll results
- list time entries
- list payroll pay groups
- erp
slug: payroll-processing
source_filename: payroll-processing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Workday Payroll Processing Workflow\"\n  description: \"End-to-end payroll processing workflow combining payroll calculations, time tracking, absence management, compensation, and tax management across US, Australia, Canada, France, and UK payroll modules.\"\n  tags:\n    - Workday\n    - Integration\n    - Payroll\n    - Time Tracking\n    - Compensation\n    - Tax\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WORKDAY_INTEGRATION_ACCESS_TOKEN: WORKDAY_INTEGRATION_ACCESS_TOKEN\n      WORKDAY_TENANT: WORKDAY_TENANT\n\ncapability:\n  consumes:\n    - type: http\n      namespace: payroll\n      baseUri: https://wd2-impl-services1.workday.com/ccx/service/{tenant}\n      description: \"Workday Payroll API\"\n      authentication:\n        type: bearer\n        token: \"{{WORKDAY_INTEGRATION_ACCESS_TOKEN}}\"\n      resources:\n        - name: pay-groups\n          path: /payGroups\n\
  \          operations:\n            - name: list-pay-groups\n              method: GET\n              description: \"List pay groups\"\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n        - name: payroll-results\n          path: /payrollResults\n          operations:\n            - name: list-payroll-results\n              method: GET\n              description: \"List payroll results\"\n              inputParameters:\n                - name: period\n                  in: query\n                  type: string\n                  required: false\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n        - name: pay-components\n          path: /payComponents\n          operations:\n            - name: list-pay-components\n              method: GET\n   \
  \           description: \"List pay components\"\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n    - type: http\n      namespace: time-tracking\n      baseUri: https://wd2-impl-services1.workday.com/ccx/service/{tenant}\n      description: \"Workday Time Tracking API\"\n      authentication:\n        type: bearer\n        token: \"{{WORKDAY_INTEGRATION_ACCESS_TOKEN}}\"\n      resources:\n        - name: time-entries\n          path: /timeEntries\n          operations:\n            - name: list-time-entries\n              method: GET\n              description: \"List time entries\"\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n    - type: http\n      namespace: absence\n      baseUri: https://wd2-impl-services1.workday.com/ccx/service/{tenant}\n\
  \      description: \"Workday Absence Management API\"\n      authentication:\n        type: bearer\n        token: \"{{WORKDAY_INTEGRATION_ACCESS_TOKEN}}\"\n      resources:\n        - name: leave-requests\n          path: /leaveRequests\n          operations:\n            - name: list-leave-requests\n              method: GET\n              description: \"List leave requests\"\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: payroll-processing-rest-api\n      resources:\n        - path: /v1/pay-groups\n          name: pay-groups\n          operations:\n            - method: GET\n              name: list-pay-groups\n              call: \"payroll.list-pay-groups\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/payroll-results\n  \
  \        name: payroll-results\n          operations:\n            - method: GET\n              name: list-payroll-results\n              call: \"payroll.list-payroll-results\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9092\n      namespace: payroll-processing-mcp\n      transport: http\n      tools:\n        - name: list-pay-groups\n          description: \"List payroll pay groups\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"payroll.list-pay-groups\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-payroll-results\n          description: \"List payroll calculation results\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"payroll.list-payroll-results\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n \
  \       - name: list-pay-components\n          description: \"List pay components\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"payroll.list-pay-components\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-time-entries\n          description: \"List worker time entries for payroll processing\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"time-tracking.list-time-entries\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-leave-requests\n          description: \"List employee leave requests affecting payroll\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"absence.list-leave-requests\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/workday-integration/refs/heads/main/capabilities/payroll-processing.yaml
tags:
- Workday
- Integration
- Payroll
- Time Tracking
- Compensation
- Tax
tools:
- description: List payroll pay groups
  hints:
    openWorld: true
    readOnly: true
  name: list-pay-groups
- description: List payroll calculation results
  hints:
    openWorld: true
    readOnly: true
  name: list-payroll-results
- description: List pay components
  hints:
    openWorld: true
    readOnly: true
  name: list-pay-components
- description: List worker time entries for payroll processing
  hints:
    openWorld: true
    readOnly: true
  name: list-time-entries
- description: List employee leave requests affecting payroll
  hints:
    openWorld: true
    readOnly: true
  name: list-leave-requests
---
