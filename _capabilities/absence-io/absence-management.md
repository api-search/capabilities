---
api_specs:
- filename: absence-io-openapi.yml
  format: yaml
  label: absence-io
  slug: absence-io
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/absence-io/refs/heads/main/openapi/absence-io-openapi.yml
categories:
- payroll-hr
consumed_apis:
- absence-io
description: Unified workflow for managing employee absences, tracking leave balances, and administering organizational structure in Absence.io. Designed for HR managers, payroll teams, and integration developers building absence management workflows.
layout: capability
name: Absence.io Absence Management
operations:
- description: List all employee absences.
  method: GET
  name: list-absences
  path: /v1/absences
- description: Create a new absence record.
  method: POST
  name: create-absence
  path: /v1/absences
- description: Get an absence by ID.
  method: GET
  name: get-absence
  path: /v1/absences/{id}
- description: Update an absence.
  method: PUT
  name: update-absence
  path: /v1/absences/{id}
- description: Delete an absence.
  method: DELETE
  name: delete-absence
  path: /v1/absences/{id}
- description: List all employees.
  method: GET
  name: list-users
  path: /v1/employees
- description: Get an employee by ID.
  method: GET
  name: get-user
  path: /v1/employees/{id}
- description: List employee leave allowances.
  method: GET
  name: list-allowances
  path: /v1/allowances
- description: List departments.
  method: GET
  name: list-departments
  path: /v1/departments
- description: List locations.
  method: GET
  name: list-locations
  path: /v1/locations
- description: List absence reason types.
  method: GET
  name: list-reason-types
  path: /v1/absence-types
personas: []
provider_name: Absence.io
provider_slug: absence-io
search_terms:
- delete absence
- list absence types
- absence management
- employee absence records.
- list leave allowances
- list employee absences. supports date range filtering and pagination.
- list locations.
- absence reason types.
- update absence
- list employee leave allowances.
- list all office locations.
- get an absence by id.
- a specific employee record.
- delete an absence record permanently.
- list departments
- list employee leave allowances and remaining balances for the year.
- HR Manager
- list all employees.
- list allowances
- Payroll Processor
- organizational departments.
- create a new absence record.
- unified workflow for managing employee absences, leave balances, and org structure
- list absence reason types.
- get details of a specific absence record by its id.
- list all employee absences.
- update an absence.
- developers building integrations between absence.io and erp/hris systems
- create absence
- a specific absence record.
- get absence
- office locations.
- list all absence reason types (vacation, sick leave, parental leave, etc.).
- list users
- payroll
- list reason types
- list all employees in the organization with their department and location assignments.
- list departments.
- employees
- employee leave allowances.
- employee records.
- employee absence tracking, approval workflows, and leave balance management
- organizational structure including departments, locations, and employees
- get an employee by id.
- get employee
- list all organizational departments.
- absences
- get user
- update an existing absence record (change dates, reason, etc.).
- Integration Developer
- payroll teams using absence data to calculate leave deductions and entitlements
- hr professionals managing employee leave requests and approvals
- create a new absence record for an employee.
- delete an absence.
- list employees
- get detailed information about a specific employee.
- leave management
- list locations
- list absences
- hr
slug: absence-management
source_filename: absence-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Absence.io Absence Management\"\n  description: \"Unified workflow for managing employee absences, tracking leave balances, and administering organizational structure in Absence.io. Designed for HR managers, payroll teams, and integration developers building absence management workflows.\"\n  tags:\n    - Absence Management\n    - HR\n    - Leave Management\n    - Payroll\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ABSENCE_IO_API_KEY_ID: ABSENCE_IO_API_KEY_ID\n      ABSENCE_IO_API_KEY: ABSENCE_IO_API_KEY\n\ncapability:\n  consumes:\n    - import: absence-io\n      location: ./shared/absence-io.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: absence-management-api\n      description: \"Unified REST API for comprehensive absence and leave management.\"\n      resources:\n        - path: /v1/absences\n          name: absences\n          description:\
  \ \"Employee absence records.\"\n          operations:\n            - method: GET\n              name: list-absences\n              description: \"List all employee absences.\"\n              call: \"absence-io.list-absences\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-absence\n              description: \"Create a new absence record.\"\n              call: \"absence-io.create-absence\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/absences/{id}\n          name: absence-by-id\n          description: \"A specific absence record.\"\n          operations:\n            - method: GET\n              name: get-absence\n              description: \"Get an absence by ID.\"\n              call: \"absence-io.get-absence\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n  \
  \              - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-absence\n              description: \"Update an absence.\"\n              call: \"absence-io.update-absence\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-absence\n              description: \"Delete an absence.\"\n              call: \"absence-io.delete-absence\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/employees\n          name: employees\n          description: \"Employee records.\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List all employees.\"\n              call: \"absence-io.list-users\"\n       \
  \       outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/employees/{id}\n          name: employee-by-id\n          description: \"A specific employee record.\"\n          operations:\n            - method: GET\n              name: get-user\n              description: \"Get an employee by ID.\"\n              call: \"absence-io.get-user\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/allowances\n          name: allowances\n          description: \"Employee leave allowances.\"\n          operations:\n            - method: GET\n              name: list-allowances\n              description: \"List employee leave allowances.\"\n              call: \"absence-io.list-allowances\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/departments\n\
  \          name: departments\n          description: \"Organizational departments.\"\n          operations:\n            - method: GET\n              name: list-departments\n              description: \"List departments.\"\n              call: \"absence-io.list-departments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/locations\n          name: locations\n          description: \"Office locations.\"\n          operations:\n            - method: GET\n              name: list-locations\n              description: \"List locations.\"\n              call: \"absence-io.list-locations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/absence-types\n          name: absence-types\n          description: \"Absence reason types.\"\n          operations:\n            - method: GET\n              name: list-reason-types\n              description: \"\
  List absence reason types.\"\n              call: \"absence-io.list-reason-types\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: absence-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted absence and leave management workflows.\"\n      tools:\n        - name: list-absences\n          description: \"List employee absences. Supports date range filtering and pagination.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"absence-io.list-absences\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-absence\n          description: \"Get details of a specific absence record by its ID.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"absence-io.get-absence\"\n          with:\n            id: \"tools.id\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-absence\n          description: \"Create a new absence record for an employee.\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"absence-io.create-absence\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-absence\n          description: \"Update an existing absence record (change dates, reason, etc.).\"\n          hints:\n            readOnly: false\n            openWorld: false\n            idempotent: true\n          call: \"absence-io.update-absence\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-absence\n          description: \"Delete an absence record permanently.\"\n          hints:\n            readOnly: false\n            destructive: true\n   \
  \         idempotent: true\n          call: \"absence-io.delete-absence\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-employees\n          description: \"List all employees in the organization with their department and location assignments.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"absence-io.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-employee\n          description: \"Get detailed information about a specific employee.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"absence-io.get-user\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-leave-allowances\n          description: \"List employee\
  \ leave allowances and remaining balances for the year.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"absence-io.list-allowances\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-departments\n          description: \"List all organizational departments.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"absence-io.list-departments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-locations\n          description: \"List all office locations.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"absence-io.list-locations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-absence-types\n          description: \"List all absence reason types (vacation, sick leave, parental\
  \ leave, etc.).\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"absence-io.list-reason-types\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/absence-io/refs/heads/main/capabilities/absence-management.yaml
tags:
- Absence Management
- HR
- Leave Management
- Payroll
tools:
- description: List employee absences. Supports date range filtering and pagination.
  hints:
    openWorld: false
    readOnly: true
  name: list-absences
- description: Get details of a specific absence record by its ID.
  hints:
    openWorld: false
    readOnly: true
  name: get-absence
- description: Create a new absence record for an employee.
  hints:
    openWorld: false
    readOnly: false
  name: create-absence
- description: Update an existing absence record (change dates, reason, etc.).
  hints:
    idempotent: true
    openWorld: false
    readOnly: false
  name: update-absence
- description: Delete an absence record permanently.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-absence
- description: List all employees in the organization with their department and location assignments.
  hints:
    openWorld: false
    readOnly: true
  name: list-employees
- description: Get detailed information about a specific employee.
  hints:
    openWorld: false
    readOnly: true
  name: get-employee
- description: List employee leave allowances and remaining balances for the year.
  hints:
    openWorld: false
    readOnly: true
  name: list-leave-allowances
- description: List all organizational departments.
  hints:
    openWorld: false
    readOnly: true
  name: list-departments
- description: List all office locations.
  hints:
    openWorld: false
    readOnly: true
  name: list-locations
- description: List all absence reason types (vacation, sick leave, parental leave, etc.).
  hints:
    openWorld: false
    readOnly: true
  name: list-absence-types
---
