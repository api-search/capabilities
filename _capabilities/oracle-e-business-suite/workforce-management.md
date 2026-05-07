---
categories:
- payroll-hr
consumed_apis: []
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
- list organizations.
- update employee
- retrieve employees.
- get employee by id.
- update employee record.
- e-business suite
- list employees.
- get employee by id
- retrieve benefit enrollments.
- get assignments
- business applications
- list payrolls.
- retrieve payroll runs.
- organization management.
- get payrolls
- payroll
- retrieve positions.
- retrieve organizations.
- create an employee record.
- enterprise
- human resources
- employee management.
- get positions
- get payroll runs
- get benefit enrollments
- retrieve assignments.
- get employees
- workforce management
- erp
- retrieve payroll definitions.
- create employee
- oracle
- payroll management.
- get organizations
slug: workforce-management
source_filename: workforce-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Oracle EBS Workforce Management\n  description: Human capital management combining HR, payroll, benefits, and organizational management. Used by HR administrators\n    and payroll managers for employee lifecycle operations.\n  tags:\n  - Oracle\n  - Human Resources\n  - Workforce Management\n  - Payroll\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ORACLE_EBS_TOKEN: ORACLE_EBS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: oracle-human-resources\n    baseUri: https://{instance}.oracle.com/webservices/rest\n    description: Oracle EBS Human Resources API for managing employees and payroll.\n    authentication:\n      type: bearer\n      token: '{{ORACLE_EBS_TOKEN}}'\n    resources:\n    - name: employees\n      path: /hr/employees\n      description: Employee management.\n      operations:\n      - name: get-employees\n        method: GET\n        description: Retrieve employees.\n\
  \        inputParameters:\n        - name: organizationId\n          in: query\n          type: integer\n          required: false\n          description: Organization identifier.\n        - name: employeeNumber\n          in: query\n          type: string\n          required: false\n          description: Employee number.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-employee\n        method: POST\n        description: Create a new employee record.\n        body:\n          type: json\n          data:\n            lastName: '{{tools.last_name}}'\n            firstName: '{{tools.first_name}}'\n            hireDate: '{{tools.hire_date}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: employee\n      path: /hr/employees/{personId}\n      description: Specific employee.\n      operations:\n     \
  \ - name: get-employee-by-id\n        method: GET\n        description: Get employee by ID.\n        inputParameters:\n        - name: personId\n          in: path\n          type: integer\n          required: true\n          description: Person identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-employee\n        method: PUT\n        description: Update employee record.\n        inputParameters:\n        - name: personId\n          in: path\n          type: integer\n          required: true\n          description: Person identifier.\n        body:\n          type: json\n          data:\n            lastName: '{{tools.last_name}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assignments\n      path: /hr/assignments\n      description: Employee assignments.\n      operations:\n      - name:\
  \ get-assignments\n        method: GET\n        description: Retrieve assignments.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations\n      path: /hr/organizations\n      description: Organizations.\n      operations:\n      - name: get-organizations\n        method: GET\n        description: Retrieve organizations.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: positions\n      path: /hr/positions\n      description: Positions.\n      operations:\n      - name: get-positions\n        method: GET\n        description: Retrieve positions.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payrolls\n      path: /pay/payrolls\n      description: Payroll definitions.\n      operations:\n      - name: get-payrolls\n\
  \        method: GET\n        description: Retrieve payrolls.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payroll-runs\n      path: /pay/payroll-runs\n      description: Payroll runs.\n      operations:\n      - name: get-payroll-runs\n        method: GET\n        description: Retrieve payroll runs.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: benefit-enrollments\n      path: /ben/enrollments\n      description: Benefit enrollments.\n      operations:\n      - name: get-benefit-enrollments\n        method: GET\n        description: Retrieve benefit enrollments.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: workforce-management-api\n    description: Unified REST\
  \ API for Oracle EBS workforce management.\n    resources:\n    - path: /v1/employees\n      name: employees\n      description: Employee management.\n      operations:\n      - method: GET\n        name: get-employees\n        description: List employees.\n        call: oracle-human-resources.get-employees\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations\n      name: organizations\n      description: Organization management.\n      operations:\n      - method: GET\n        name: get-organizations\n        description: List organizations.\n        call: oracle-human-resources.get-organizations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payrolls\n      name: payrolls\n      description: Payroll management.\n      operations:\n      - method: GET\n        name: get-payrolls\n        description: List payrolls.\n        call: oracle-human-resources.get-payrolls\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: workforce-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Oracle EBS workforce management.\n    tools:\n    - name: get-employees\n      description: Retrieve employees.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: oracle-human-resources.get-employees\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-employee\n      description: Create an employee record.\n      hints:\n        readOnly: false\n      call: oracle-human-resources.create-employee\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-employee-by-id\n      description: Get employee by ID.\n      hints:\n        readOnly: true\n      call: oracle-human-resources.get-employee-by-id\n      with:\n        personId: tools.person_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    -\
  \ name: update-employee\n      description: Update employee record.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: oracle-human-resources.update-employee\n      with:\n        personId: tools.person_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-assignments\n      description: Retrieve assignments.\n      hints:\n        readOnly: true\n      call: oracle-human-resources.get-assignments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-organizations\n      description: Retrieve organizations.\n      hints:\n        readOnly: true\n      call: oracle-human-resources.get-organizations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-positions\n      description: Retrieve positions.\n      hints:\n        readOnly: true\n      call: oracle-human-resources.get-positions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ get-payrolls\n      description: Retrieve payroll definitions.\n      hints:\n        readOnly: true\n      call: oracle-human-resources.get-payrolls\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-payroll-runs\n      description: Retrieve payroll runs.\n      hints:\n        readOnly: true\n      call: oracle-human-resources.get-payroll-runs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-benefit-enrollments\n      description: Retrieve benefit enrollments.\n      hints:\n        readOnly: true\n      call: oracle-human-resources.get-benefit-enrollments\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
