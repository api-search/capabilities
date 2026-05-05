---
categories: []
consumed_apis:
- wtw-hr-portal
description: Workflow capability for HR teams and employees using the WTW HR Portal. Combines employee profile management, total rewards communication, benefits enrollment tracking, HR content delivery, and case management to create a unified digital HR experience.
layout: capability
name: WTW Employee Experience
operations:
- description: List all employees
  method: GET
  name: list-employees
  path: /v1/employees
- description: Get employee profile
  method: GET
  name: get-employee
  path: /v1/employees/{employeeId}
- description: Get total rewards statement
  method: GET
  name: get-employee-total-rewards
  path: /v1/employees/{employeeId}/total-rewards
- description: Get benefits summary
  method: GET
  name: get-employee-benefits
  path: /v1/employees/{employeeId}/benefits
- description: List HR content
  method: GET
  name: list-content
  path: /v1/content
- description: Create HR content
  method: POST
  name: create-content
  path: /v1/content
- description: List HR cases
  method: GET
  name: list-cases
  path: /v1/cases
- description: Create a new case
  method: POST
  name: create-case
  path: /v1/cases
personas: []
provider_name: Towers Watson
provider_slug: towers-watson
search_terms:
- submit hr case
- consulting
- total compensation and rewards
- list all employees in the hr portal with optional department and status filters
- list employees
- hr service cases
- create a new case
- get employee
- human resources
- employee benefits enrollment
- actuarial
- risk management
- publish hr content
- human capital
- benefits
- list hr content
- list all employees
- list cases
- get benefits summary
- individual employee
- submit a new hr service case or employee inquiry
- get hr portal profile for a specific employee
- employee management
- list content
- create hr content
- get total rewards statement
- list hr content articles, announcements, and policies
- create content
- get employee total rewards
- get hr case
- create case
- hr content and communications
- get total compensation and rewards statement for an employee
- get details and status for a specific hr service case
- get total rewards
- hr technology
- list hr cases
- list hr service cases with optional status and category filters
- get employee benefits
- get benefits enrollment
- insurance brokerage
- get current benefits enrollment summary for an employee
- total rewards
- employee experience
- create and publish a new hr content item or announcement
- get employee profile
slug: employee-experience
source_filename: employee-experience.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"WTW Employee Experience\"\n  description: \"Workflow capability for HR teams and employees using the WTW HR Portal. Combines employee profile management, total rewards communication, benefits enrollment tracking, HR content delivery, and case management to create a unified digital HR experience.\"\n  tags:\n    - Human Resources\n    - Employee Experience\n    - Benefits\n    - Total Rewards\n    - HR Technology\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WTW_HR_PORTAL_TOKEN: WTW_HR_PORTAL_TOKEN\n\ncapability:\n  consumes:\n    - import: wtw-hr-portal\n      location: ./shared/hr-portal.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: wtw-employee-api\n      description: \"Unified REST API for WTW employee digital experience management.\"\n      resources:\n        - path: /v1/employees\n          name: employees\n          description: \"Employee\
  \ management\"\n          operations:\n            - method: GET\n              name: list-employees\n              description: \"List all employees\"\n              call: \"wtw-hr-portal.list-employees\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/employees/{employeeId}\n          name: employee\n          description: \"Individual employee\"\n          operations:\n            - method: GET\n              name: get-employee\n              description: \"Get employee profile\"\n              call: \"wtw-hr-portal.get-employee\"\n              with:\n                employeeId: \"rest.employeeId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/employees/{employeeId}/total-rewards\n          name: total-rewards\n          description: \"Total compensation and rewards\"\n          operations:\n            - method: GET\n              name:\
  \ get-employee-total-rewards\n              description: \"Get total rewards statement\"\n              call: \"wtw-hr-portal.get-employee-total-rewards\"\n              with:\n                employeeId: \"rest.employeeId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/employees/{employeeId}/benefits\n          name: employee-benefits\n          description: \"Employee benefits enrollment\"\n          operations:\n            - method: GET\n              name: get-employee-benefits\n              description: \"Get benefits summary\"\n              call: \"wtw-hr-portal.get-employee-benefits\"\n              with:\n                employeeId: \"rest.employeeId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/content\n          name: content\n          description: \"HR content and communications\"\n          operations:\n            - method:\
  \ GET\n              name: list-content\n              description: \"List HR content\"\n              call: \"wtw-hr-portal.list-content\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-content\n              description: \"Create HR content\"\n              call: \"wtw-hr-portal.create-content\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cases\n          name: cases\n          description: \"HR service cases\"\n          operations:\n            - method: GET\n              name: list-cases\n              description: \"List HR cases\"\n              call: \"wtw-hr-portal.list-cases\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-case\n              description: \"Create a new case\"\n      \
  \        call: \"wtw-hr-portal.create-case\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: wtw-employee-mcp\n      transport: http\n      description: \"MCP server for AI-assisted WTW HR employee experience workflows.\"\n      tools:\n        - name: list-employees\n          description: \"List all employees in the HR portal with optional department and status filters\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wtw-hr-portal.list-employees\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-employee\n          description: \"Get HR portal profile for a specific employee\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"wtw-hr-portal.get-employee\"\n          with:\n            employeeId: \"tools.employeeId\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: get-total-rewards\n          description: \"Get total compensation and rewards statement for an employee\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"wtw-hr-portal.get-employee-total-rewards\"\n          with:\n            employeeId: \"tools.employeeId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-benefits-enrollment\n          description: \"Get current benefits enrollment summary for an employee\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"wtw-hr-portal.get-employee-benefits\"\n          with:\n            employeeId: \"tools.employeeId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-hr-content\n          description: \"List HR content articles, announcements, and policies\"\n  \
  \        hints:\n            readOnly: true\n            openWorld: true\n          call: \"wtw-hr-portal.list-content\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: publish-hr-content\n          description: \"Create and publish a new HR content item or announcement\"\n          hints:\n            readOnly: false\n          call: \"wtw-hr-portal.create-content\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-hr-cases\n          description: \"List HR service cases with optional status and category filters\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wtw-hr-portal.list-cases\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: submit-hr-case\n          description: \"Submit a new HR service case or employee inquiry\"\n          hints:\n            readOnly: false\n\
  \          call: \"wtw-hr-portal.create-case\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-hr-case\n          description: \"Get details and status for a specific HR service case\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"wtw-hr-portal.get-case\"\n          with:\n            caseId: \"tools.caseId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/towers-watson/refs/heads/main/capabilities/employee-experience.yaml
tags:
- Human Resources
- Employee Experience
- Benefits
- Total Rewards
- HR Technology
tools:
- description: List all employees in the HR portal with optional department and status filters
  hints:
    openWorld: true
    readOnly: true
  name: list-employees
- description: Get HR portal profile for a specific employee
  hints:
    idempotent: true
    readOnly: true
  name: get-employee
- description: Get total compensation and rewards statement for an employee
  hints:
    idempotent: true
    readOnly: true
  name: get-total-rewards
- description: Get current benefits enrollment summary for an employee
  hints:
    idempotent: true
    readOnly: true
  name: get-benefits-enrollment
- description: List HR content articles, announcements, and policies
  hints:
    openWorld: true
    readOnly: true
  name: list-hr-content
- description: Create and publish a new HR content item or announcement
  hints:
    readOnly: false
  name: publish-hr-content
- description: List HR service cases with optional status and category filters
  hints:
    openWorld: true
    readOnly: true
  name: list-hr-cases
- description: Submit a new HR service case or employee inquiry
  hints:
    readOnly: false
  name: submit-hr-case
- description: Get details and status for a specific HR service case
  hints:
    idempotent: true
    readOnly: true
  name: get-hr-case
---
