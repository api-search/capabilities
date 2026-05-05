---
categories:
- payroll-hr
consumed_apis:
- oracle-human-resources
description: Human capital management combining HR, payroll, benefits, and organizational management. Used by HR administrators and payroll managers for employee lifecycle operations.
layout: capability
name: Oracle EBS Workforce Management
operations:
- description: List employees.
  method: GET
  name: get-employees
  path: /v1/employees
- description: List organizations.
  method: GET
  name: get-organizations
  path: /v1/organizations
- description: List payrolls.
  method: GET
  name: get-payrolls
  path: /v1/payrolls
personas: []
provider_name: Oracle E-Business Suite
provider_slug: oracle-e-business-suite
search_terms:
- get employee by id.
- get positions
- get benefit enrollments
- get employee by id
- employee management.
- retrieve assignments.
- update employee
- list employees.
- enterprise
- create employee
- organization management.
- human resources
- retrieve positions.
- get employees
- e-business suite
- oracle
- get assignments
- payroll
- create an employee record.
- get organizations
- get payrolls
- retrieve organizations.
- erp
- get payroll runs
- retrieve benefit enrollments.
- retrieve payroll runs.
- business applications
- update employee record.
- workforce management
- list organizations.
- list payrolls.
- retrieve payroll definitions.
- retrieve employees.
- payroll management.
slug: workforce-management
source_filename: workforce-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Oracle EBS Workforce Management\"\n  description: \"Human capital management combining HR, payroll, benefits, and organizational management. Used by HR administrators and payroll managers for employee lifecycle operations.\"\n  tags:\n    - Oracle\n    - Human Resources\n    - Workforce Management\n    - Payroll\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      ORACLE_EBS_TOKEN: ORACLE_EBS_TOKEN\n\ncapability:\n  consumes:\n    - import: oracle-human-resources\n      location: ./shared/human-resources.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: workforce-management-api\n      description: \"Unified REST API for Oracle EBS workforce management.\"\n      resources:\n        - path: /v1/employees\n          name: employees\n          description: \"Employee management.\"\n          operations:\n            - method: GET\n              name: get-employees\n\
  \              description: \"List employees.\"\n              call: \"oracle-human-resources.get-employees\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/organizations\n          name: organizations\n          description: \"Organization management.\"\n          operations:\n            - method: GET\n              name: get-organizations\n              description: \"List organizations.\"\n              call: \"oracle-human-resources.get-organizations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/payrolls\n          name: payrolls\n          description: \"Payroll management.\"\n          operations:\n            - method: GET\n              name: get-payrolls\n              description: \"List payrolls.\"\n              call: \"oracle-human-resources.get-payrolls\"\n              outputParameters:\n                - type: object\n \
  \                 mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: workforce-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Oracle EBS workforce management.\"\n      tools:\n        - name: get-employees\n          description: \"Retrieve employees.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"oracle-human-resources.get-employees\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-employee\n          description: \"Create an employee record.\"\n          hints:\n            readOnly: false\n          call: \"oracle-human-resources.create-employee\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-employee-by-id\n          description: \"Get employee by ID.\"\n          hints:\n            readOnly: true\n          call: \"oracle-human-resources.get-employee-by-id\"\
  \n          with:\n            personId: \"tools.person_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-employee\n          description: \"Update employee record.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"oracle-human-resources.update-employee\"\n          with:\n            personId: \"tools.person_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-assignments\n          description: \"Retrieve assignments.\"\n          hints:\n            readOnly: true\n          call: \"oracle-human-resources.get-assignments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-organizations\n          description: \"Retrieve organizations.\"\n          hints:\n            readOnly: true\n          call: \"oracle-human-resources.get-organizations\"\n       \
  \   outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-positions\n          description: \"Retrieve positions.\"\n          hints:\n            readOnly: true\n          call: \"oracle-human-resources.get-positions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-payrolls\n          description: \"Retrieve payroll definitions.\"\n          hints:\n            readOnly: true\n          call: \"oracle-human-resources.get-payrolls\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-payroll-runs\n          description: \"Retrieve payroll runs.\"\n          hints:\n            readOnly: true\n          call: \"oracle-human-resources.get-payroll-runs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-benefit-enrollments\n          description: \"Retrieve benefit enrollments.\"\
  \n          hints:\n            readOnly: true\n          call: \"oracle-human-resources.get-benefit-enrollments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/oracle-e-business-suite/refs/heads/main/capabilities/workforce-management.yaml
tags:
- Oracle
- Human Resources
- Workforce Management
- Payroll
tools:
- description: Retrieve employees.
  hints:
    openWorld: true
    readOnly: true
  name: get-employees
- description: Create an employee record.
  hints:
    readOnly: false
  name: create-employee
- description: Get employee by ID.
  hints:
    readOnly: true
  name: get-employee-by-id
- description: Update employee record.
  hints:
    idempotent: true
    readOnly: false
  name: update-employee
- description: Retrieve assignments.
  hints:
    readOnly: true
  name: get-assignments
- description: Retrieve organizations.
  hints:
    readOnly: true
  name: get-organizations
- description: Retrieve positions.
  hints:
    readOnly: true
  name: get-positions
- description: Retrieve payroll definitions.
  hints:
    readOnly: true
  name: get-payrolls
- description: Retrieve payroll runs.
  hints:
    readOnly: true
  name: get-payroll-runs
- description: Retrieve benefit enrollments.
  hints:
    readOnly: true
  name: get-benefit-enrollments
---
