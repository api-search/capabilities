---
categories: []
consumed_apis: []
description: End-to-end employee lifecycle workflow combining HCM, recruiting, onboarding, benefits, time tracking, compensation, and offboarding capabilities in Workday.
layout: capability
name: Workday Hire-to-Retire Workflow
operations:
- description: ''
  method: GET
  name: list-workers
  path: /v1/workers
- description: ''
  method: GET
  name: list-job-requisitions
  path: /v1/job-requisitions
personas: []
provider_name: Workday Integration
provider_slug: workday-integration
search_terms:
- list available employee benefit plans
- list candidates
- workday
- list organizational units
- hcm
- list recruiting candidates
- integration
- finance
- get details for a specific worker
- payroll
- list open job requisitions
- recruiting
- list benefit enrollments
- list organizations
- enterprise
- list all workday workers
- benefits
- list workers
- erp
- list compensation plans
- hire-to-retire
- get worker
- list job requisitions
- list benefit plans
- list employee benefit enrollments
slug: hire-to-retire
source_filename: hire-to-retire.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Workday Hire-to-Retire Workflow\"\n  description: \"End-to-end employee lifecycle workflow combining HCM, recruiting, onboarding, benefits, time tracking, compensation, and offboarding capabilities in Workday.\"\n  tags:\n    - Workday\n    - Integration\n    - HCM\n    - Recruiting\n    - Benefits\n    - Hire-to-Retire\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WORKDAY_INTEGRATION_ACCESS_TOKEN: WORKDAY_INTEGRATION_ACCESS_TOKEN\n      WORKDAY_TENANT: WORKDAY_TENANT\n\ncapability:\n  consumes:\n    - type: http\n      namespace: hcm\n      baseUri: https://wd2-impl-services1.workday.com/ccx/service/{tenant}\n      description: \"Workday HCM API\"\n      authentication:\n        type: bearer\n        token: \"{{WORKDAY_INTEGRATION_ACCESS_TOKEN}}\"\n      resources:\n        - name: workers\n          path: /workers\n          operations:\n            - name: list-workers\n\
  \              method: GET\n              description: \"List workers\"\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n            - name: get-worker\n              method: GET\n              description: \"Get worker details\"\n              inputParameters:\n                - name: workerId\n                  in: path\n                  type: string\n                  required: true\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n        - name: organizations\n          path: /organizations\n          operations:\n            - name: list-organizations\n              method: GET\n              description: \"List organizations\"\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                \
  \  type: object\n                  value: \"$.\"\n    - type: http\n      namespace: recruiting\n      baseUri: https://wd2-impl-services1.workday.com/ccx/service/{tenant}\n      description: \"Workday Recruiting API\"\n      authentication:\n        type: bearer\n        token: \"{{WORKDAY_INTEGRATION_ACCESS_TOKEN}}\"\n      resources:\n        - name: job-requisitions\n          path: /jobRequisitions\n          operations:\n            - name: list-job-requisitions\n              method: GET\n              description: \"List job requisitions\"\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n        - name: candidates\n          path: /candidates\n          operations:\n            - name: list-candidates\n              method: GET\n              description: \"List candidates\"\n              outputRawFormat: json\n              outputParameters:\n               \
  \ - name: result\n                  type: object\n                  value: \"$.\"\n    - type: http\n      namespace: benefits\n      baseUri: https://wd2-impl-services1.workday.com/ccx/service/{tenant}\n      description: \"Workday Benefits API\"\n      authentication:\n        type: bearer\n        token: \"{{WORKDAY_INTEGRATION_ACCESS_TOKEN}}\"\n      resources:\n        - name: benefit-plans\n          path: /benefitPlans\n          operations:\n            - name: list-benefit-plans\n              method: GET\n              description: \"List benefit plans\"\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n        - name: benefit-enrollments\n          path: /benefitEnrollments\n          operations:\n            - name: list-benefit-enrollments\n              method: GET\n              description: \"List benefit enrollments\"\n              outputRawFormat: json\n\
  \              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n    - type: http\n      namespace: compensation\n      baseUri: https://wd2-impl-services1.workday.com/ccx/service/{tenant}\n      description: \"Workday Compensation API\"\n      authentication:\n        type: bearer\n        token: \"{{WORKDAY_INTEGRATION_ACCESS_TOKEN}}\"\n      resources:\n        - name: compensation-plans\n          path: /compensationPlans\n          operations:\n            - name: list-compensation-plans\n              method: GET\n              description: \"List compensation plans\"\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: hire-to-retire-rest-api\n      resources:\n        - path: /v1/workers\n          name: workers\n          operations:\n\
  \            - method: GET\n              name: list-workers\n              call: \"hcm.list-workers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/job-requisitions\n          name: job-requisitions\n          operations:\n            - method: GET\n              name: list-job-requisitions\n              call: \"recruiting.list-job-requisitions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: hire-to-retire-mcp\n      transport: http\n      tools:\n        - name: list-workers\n          description: \"List all Workday workers\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hcm.list-workers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-worker\n          description: \"Get details for a specific\
  \ worker\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"hcm.get-worker\"\n          with:\n            workerId: \"tools.workerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-organizations\n          description: \"List organizational units\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hcm.list-organizations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-job-requisitions\n          description: \"List open job requisitions\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"recruiting.list-job-requisitions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-candidates\n          description: \"List recruiting candidates\"\n          hints:\n            readOnly:\
  \ true\n            openWorld: true\n          call: \"recruiting.list-candidates\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-benefit-plans\n          description: \"List available employee benefit plans\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"benefits.list-benefit-plans\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-benefit-enrollments\n          description: \"List employee benefit enrollments\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"benefits.list-benefit-enrollments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-compensation-plans\n          description: \"List compensation plans\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"compensation.list-compensation-plans\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/workday-integration/refs/heads/main/capabilities/hire-to-retire.yaml
tags:
- Workday
- Integration
- HCM
- Recruiting
- Benefits
- Hire-to-Retire
tools:
- description: List all Workday workers
  hints:
    openWorld: true
    readOnly: true
  name: list-workers
- description: Get details for a specific worker
  hints:
    openWorld: false
    readOnly: true
  name: get-worker
- description: List organizational units
  hints:
    openWorld: true
    readOnly: true
  name: list-organizations
- description: List open job requisitions
  hints:
    openWorld: true
    readOnly: true
  name: list-job-requisitions
- description: List recruiting candidates
  hints:
    openWorld: true
    readOnly: true
  name: list-candidates
- description: List available employee benefit plans
  hints:
    openWorld: true
    readOnly: true
  name: list-benefit-plans
- description: List employee benefit enrollments
  hints:
    openWorld: true
    readOnly: true
  name: list-benefit-enrollments
- description: List compensation plans
  hints:
    openWorld: true
    readOnly: true
  name: list-compensation-plans
---
