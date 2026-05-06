---
categories: []
consumed_apis: []
description: Workforce analytics and reporting workflow combining Prism Analytics data loading, RaaS reporting, HCM data, and workforce planning for enterprise decision-making in Workday.
layout: capability
name: Workday Workforce Intelligence Workflow
operations:
- description: ''
  method: GET
  name: list-datasets
  path: /v1/datasets
personas: []
provider_name: Workday Integration
provider_slug: workday-integration
search_terms:
- integration
- list workforce planning scenarios
- list organizations
- reporting
- analytics
- list headcount planning scenarios
- list datasets
- list workforce data from hcm
- list headcount scenarios
- finance
- get a prism analytics dataset
- list workers
- list workforce plans
- enterprise
- list prism analytics datasets
- payroll
- erp
- workday
- workforce planning
- list organizational units
- hcm
- create a data upload bucket for prism analytics
- create bucket
- get dataset
- prism analytics
slug: workforce-intelligence
source_filename: workforce-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Workday Workforce Intelligence Workflow\"\n  description: \"Workforce analytics and reporting workflow combining Prism Analytics data loading, RaaS reporting, HCM data, and workforce planning for enterprise decision-making in Workday.\"\n  tags:\n    - Workday\n    - Integration\n    - Analytics\n    - Reporting\n    - Workforce Planning\n    - Prism Analytics\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WORKDAY_INTEGRATION_ACCESS_TOKEN: WORKDAY_INTEGRATION_ACCESS_TOKEN\n      WORKDAY_TENANT: WORKDAY_TENANT\n\ncapability:\n  consumes:\n    - type: http\n      namespace: prism\n      baseUri: https://wd2-impl-services1.workday.com/ccx/service/{tenant}\n      description: \"Workday Prism Analytics API\"\n      authentication:\n        type: bearer\n        token: \"{{WORKDAY_INTEGRATION_ACCESS_TOKEN}}\"\n      resources:\n        - name: datasets\n          path: /datasets\n\
  \          operations:\n            - name: list-datasets\n              method: GET\n              description: \"List datasets\"\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n            - name: get-dataset\n              method: GET\n              description: \"Get a dataset\"\n              inputParameters:\n                - name: datasetId\n                  in: path\n                  type: string\n                  required: true\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n        - name: buckets\n          path: /buckets\n          operations:\n            - name: create-bucket\n              method: POST\n              description: \"Create upload bucket\"\n              outputRawFormat: json\n              outputParameters:\n      \
  \          - name: result\n                  type: object\n                  value: \"$.\"\n    - type: http\n      namespace: hcm\n      baseUri: https://wd2-impl-services1.workday.com/ccx/service/{tenant}\n      description: \"Workday HCM API\"\n      authentication:\n        type: bearer\n        token: \"{{WORKDAY_INTEGRATION_ACCESS_TOKEN}}\"\n      resources:\n        - name: workers\n          path: /workers\n          operations:\n            - name: list-workers\n              method: GET\n              description: \"List workers\"\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n        - name: organizations\n          path: /organizations\n          operations:\n            - name: list-organizations\n              method: GET\n              description: \"List organizations\"\n              outputRawFormat: json\n              outputParameters:\n          \
  \      - name: result\n                  type: object\n                  value: \"$.\"\n    - type: http\n      namespace: workforce-planning\n      baseUri: https://wd2-impl-services1.workday.com/ccx/service/{tenant}\n      description: \"Workday Workforce Planning API\"\n      authentication:\n        type: bearer\n        token: \"{{WORKDAY_INTEGRATION_ACCESS_TOKEN}}\"\n      resources:\n        - name: workforce-plans\n          path: /workforcePlans\n          operations:\n            - name: list-workforce-plans\n              method: GET\n              description: \"List workforce plans\"\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n        - name: headcount-scenarios\n          path: /headcountScenarios\n          operations:\n            - name: list-headcount-scenarios\n              method: GET\n              description: \"List headcount scenarios\"\n\
  \              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n\n  exposes:\n    - type: rest\n      port: 8084\n      namespace: workforce-intelligence-rest-api\n      resources:\n        - path: /v1/datasets\n          name: datasets\n          operations:\n            - method: GET\n              name: list-datasets\n              call: \"prism.list-datasets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9094\n      namespace: workforce-intelligence-mcp\n      transport: http\n      tools:\n        - name: list-datasets\n          description: \"List Prism Analytics datasets\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"prism.list-datasets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name:\
  \ get-dataset\n          description: \"Get a Prism Analytics dataset\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"prism.get-dataset\"\n          with:\n            datasetId: \"tools.datasetId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-bucket\n          description: \"Create a data upload bucket for Prism Analytics\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"prism.create-bucket\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-workers\n          description: \"List workforce data from HCM\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hcm.list-workers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-organizations\n          description: \"\
  List organizational units\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hcm.list-organizations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-workforce-plans\n          description: \"List workforce planning scenarios\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"workforce-planning.list-workforce-plans\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-headcount-scenarios\n          description: \"List headcount planning scenarios\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"workforce-planning.list-headcount-scenarios\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/workday-integration/refs/heads/main/capabilities/workforce-intelligence.yaml
tags:
- Workday
- Integration
- Analytics
- Reporting
- Workforce Planning
- Prism Analytics
tools:
- description: List Prism Analytics datasets
  hints:
    openWorld: true
    readOnly: true
  name: list-datasets
- description: Get a Prism Analytics dataset
  hints:
    openWorld: false
    readOnly: true
  name: get-dataset
- description: Create a data upload bucket for Prism Analytics
  hints:
    openWorld: false
    readOnly: false
  name: create-bucket
- description: List workforce data from HCM
  hints:
    openWorld: true
    readOnly: true
  name: list-workers
- description: List organizational units
  hints:
    openWorld: true
    readOnly: true
  name: list-organizations
- description: List workforce planning scenarios
  hints:
    openWorld: true
    readOnly: true
  name: list-workforce-plans
- description: List headcount planning scenarios
  hints:
    openWorld: true
    readOnly: true
  name: list-headcount-scenarios
---
