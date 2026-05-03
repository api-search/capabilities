---
categories: []
consumed_apis:
- stackone
description: Unified workflow capability for HR and people operations using StackOne's unified APIs. Combines HRIS (employee data, time-off, employments) and ATS (candidates, jobs, applications) into a single people operations interface. Designed for HR teams, people analytics, and AI agents managing workforce data across multiple HR and recruitment platforms.
layout: capability
name: StackOne People Operations
operations:
- description: List all employees
  method: GET
  name: list-employees
  path: /v1/employees
- description: Create a new employee
  method: POST
  name: create-employee
  path: /v1/employees
- description: Get employee by ID
  method: GET
  name: get-employee
  path: /v1/employees/{id}
- description: Update employee details
  method: PATCH
  name: update-employee
  path: /v1/employees/{id}
- description: List time off requests
  method: GET
  name: list-time-off
  path: /v1/time-off
- description: Submit a time off request
  method: POST
  name: create-time-off
  path: /v1/time-off
- description: List candidates from ATS
  method: GET
  name: list-candidates
  path: /v1/candidates
- description: Get candidate details
  method: GET
  name: get-candidate
  path: /v1/candidates/{id}
- description: List open jobs
  method: GET
  name: list-jobs
  path: /v1/jobs
- description: List job applications
  method: GET
  name: list-applications
  path: /v1/applications
personas: []
provider_name: StackOne
provider_slug: stackone
search_terms:
- hris
- single candidate
- get detailed information for a specific employee
- list open jobs
- list applications
- recruitment candidates
- update employee
- list all employees from a connected hris system (bamboohr, workday, etc.)
- integrations
- update employee details
- get employee by id
- list all employees
- unified api
- list candidates
- create time off
- submit a time off request
- list jobs
- get candidate details
- list time off requests from the connected hris system
- single employee
- list time off requests
- recruitment
- time off requests
- list employees
- job applications
- human resources
- update employee information in the connected hris system
- employee management across hris systems
- get employee
- get candidate
- list recruitment candidates from the connected ats system
- ipaas
- list job applications across the connected ats system
- list candidates from ats
- get full profile for a recruitment candidate
- list open job positions from the connected ats system
- list time off
- create employee
- list job applications
- submit a time off request for an employee
- people operations
- open job positions
- create a new employee
- create a new employee record in the connected hris system
slug: people-operations
source_filename: people-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"StackOne People Operations\"\n  description: >-\n    Unified workflow capability for HR and people operations using StackOne's\n    unified APIs. Combines HRIS (employee data, time-off, employments) and\n    ATS (candidates, jobs, applications) into a single people operations\n    interface. Designed for HR teams, people analytics, and AI agents managing\n    workforce data across multiple HR and recruitment platforms.\n  tags:\n    - Human Resources\n    - HRIS\n    - Recruitment\n    - Unified API\n    - People Operations\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      STACKONE_API_KEY: STACKONE_API_KEY\n\ncapability:\n  consumes:\n    - import: stackone\n      location: ./shared/stackone-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: stackone-people-api\n      description: \"Unified REST API for people operations across HRIS and ATS platforms.\"\
  \n      resources:\n        - path: /v1/employees\n          name: employees\n          description: \"Employee management across HRIS systems\"\n          operations:\n            - method: GET\n              name: list-employees\n              description: \"List all employees\"\n              call: \"stackone.list-employees\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-employee\n              description: \"Create a new employee\"\n              call: \"stackone.create-employee\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/employees/{id}\n          name: employee\n          description: \"Single employee\"\n          operations:\n            - method: GET\n              name: get-employee\n              description: \"Get employee by ID\"\n              call: \"stackone.get-employee\"\n        \
  \      with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-employee\n              description: \"Update employee details\"\n              call: \"stackone.update-employee\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/time-off\n          name: time-off\n          description: \"Time off requests\"\n          operations:\n            - method: GET\n              name: list-time-off\n              description: \"List time off requests\"\n              call: \"stackone.list-time-off\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-time-off\n              description: \"Submit a time off request\"\n           \
  \   call: \"stackone.create-time-off\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/candidates\n          name: candidates\n          description: \"Recruitment candidates\"\n          operations:\n            - method: GET\n              name: list-candidates\n              description: \"List candidates from ATS\"\n              call: \"stackone.list-candidates\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/candidates/{id}\n          name: candidate\n          description: \"Single candidate\"\n          operations:\n            - method: GET\n              name: get-candidate\n              description: \"Get candidate details\"\n              call: \"stackone.get-candidate\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n\
  \        - path: /v1/jobs\n          name: jobs\n          description: \"Open job positions\"\n          operations:\n            - method: GET\n              name: list-jobs\n              description: \"List open jobs\"\n              call: \"stackone.list-jobs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/applications\n          name: applications\n          description: \"Job applications\"\n          operations:\n            - method: GET\n              name: list-applications\n              description: \"List job applications\"\n              call: \"stackone.list-applications\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: stackone-people-mcp\n      transport: http\n      description: \"MCP server for AI-assisted people operations across HRIS and ATS systems.\"\n      tools:\n        - name:\
  \ list-employees\n          description: \"List all employees from a connected HRIS system (BambooHR, Workday, etc.)\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"stackone.list-employees\"\n          with:\n            x-account-id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-employee\n          description: \"Get detailed information for a specific employee\"\n          hints:\n            readOnly: true\n          call: \"stackone.get-employee\"\n          with:\n            id: \"tools.employee_id\"\n            x-account-id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-employee\n          description: \"Create a new employee record in the connected HRIS system\"\n          hints:\n            readOnly: false\n          call: \"stackone.create-employee\"\n  \
  \        with:\n            x-account-id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-employee\n          description: \"Update employee information in the connected HRIS system\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"stackone.update-employee\"\n          with:\n            id: \"tools.employee_id\"\n            x-account-id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-time-off\n          description: \"List time off requests from the connected HRIS system\"\n          hints:\n            readOnly: true\n          call: \"stackone.list-time-off\"\n          with:\n            x-account-id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-time-off\n          description:\
  \ \"Submit a time off request for an employee\"\n          hints:\n            readOnly: false\n          call: \"stackone.create-time-off\"\n          with:\n            x-account-id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-candidates\n          description: \"List recruitment candidates from the connected ATS system\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"stackone.list-candidates\"\n          with:\n            x-account-id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-candidate\n          description: \"Get full profile for a recruitment candidate\"\n          hints:\n            readOnly: true\n          call: \"stackone.get-candidate\"\n          with:\n            id: \"tools.candidate_id\"\n            x-account-id: \"tools.account_id\"\n        \
  \  outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-jobs\n          description: \"List open job positions from the connected ATS system\"\n          hints:\n            readOnly: true\n          call: \"stackone.list-jobs\"\n          with:\n            x-account-id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-applications\n          description: \"List job applications across the connected ATS system\"\n          hints:\n            readOnly: true\n          call: \"stackone.list-applications\"\n          with:\n            x-account-id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/stackone/refs/heads/main/capabilities/people-operations.yaml
tags:
- Human Resources
- HRIS
- Recruitment
- Unified API
- People Operations
tools:
- description: List all employees from a connected HRIS system (BambooHR, Workday, etc.)
  hints:
    openWorld: true
    readOnly: true
  name: list-employees
- description: Get detailed information for a specific employee
  hints:
    readOnly: true
  name: get-employee
- description: Create a new employee record in the connected HRIS system
  hints:
    readOnly: false
  name: create-employee
- description: Update employee information in the connected HRIS system
  hints:
    idempotent: true
    readOnly: false
  name: update-employee
- description: List time off requests from the connected HRIS system
  hints:
    readOnly: true
  name: list-time-off
- description: Submit a time off request for an employee
  hints:
    readOnly: false
  name: create-time-off
- description: List recruitment candidates from the connected ATS system
  hints:
    openWorld: true
    readOnly: true
  name: list-candidates
- description: Get full profile for a recruitment candidate
  hints:
    readOnly: true
  name: get-candidate
- description: List open job positions from the connected ATS system
  hints:
    readOnly: true
  name: list-jobs
- description: List job applications across the connected ATS system
  hints:
    readOnly: true
  name: list-applications
---
