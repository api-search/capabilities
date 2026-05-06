---
categories: []
consumed_apis: []
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
- list hr service cases with optional status and category filters
- get details and status for a specific hr service case
- total rewards
- hr service cases
- list all employees in the hr portal with optional department and status filters
- create and publish a new hr content item or announcement
- employee management
- get total rewards statement
- consulting
- create a new case
- list hr content
- list cases
- risk management
- employee benefits enrollment
- list hr content articles, announcements, and policies
- get employee total rewards
- list hr cases
- benefits
- list all employees
- individual employee
- hr content and communications
- get total rewards
- create hr content
- create case
- submit a new hr service case or employee inquiry
- get total compensation and rewards statement for an employee
- actuarial
- publish hr content
- human capital
- get benefits summary
- get hr case
- insurance brokerage
- get employee profile
- get employee
- list employees
- employee experience
- hr technology
- human resources
- list content
- submit hr case
- get employee benefits
- get hr portal profile for a specific employee
- get current benefits enrollment summary for an employee
- create content
- total compensation and rewards
- get benefits enrollment
slug: employee-experience
source_filename: employee-experience.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: WTW Employee Experience\n  description: Workflow capability for HR teams and employees using the WTW HR Portal. Combines employee profile management,\n    total rewards communication, benefits enrollment tracking, HR content delivery, and case management to create a unified\n    digital HR experience.\n  tags:\n  - Human Resources\n  - Employee Experience\n  - Benefits\n  - Total Rewards\n  - HR Technology\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WTW_HR_PORTAL_TOKEN: WTW_HR_PORTAL_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: wtw-hr-portal\n    baseUri: https://api.wtwco.com/hrportal/v1\n    description: WTW HR Portal API for employee experience management\n    authentication:\n      type: bearer\n      token: '{{WTW_HR_PORTAL_TOKEN}}'\n    resources:\n    - name: employees\n      path: /employees\n      description: Employee profile management\n      operations:\n   \
  \   - name: list-employees\n        method: GET\n        description: List all employees in the HR portal\n        inputParameters:\n        - name: department\n          in: query\n          type: string\n          required: false\n          description: Filter by department\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by employment status\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: employee\n      path: /employees/{employeeId}\n      description: Individual employee\n      operations:\n      - name: get-employee\n        method: GET\n        description: Get HR portal profile for an employee\n        inputParameters:\n        - name: employeeId\n          in: path\n          type:\
  \ string\n          required: true\n          description: Employee identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: total-rewards\n      path: /employees/{employeeId}/total-rewards\n      description: Employee total rewards statement\n      operations:\n      - name: get-employee-total-rewards\n        method: GET\n        description: Get total compensation and rewards statement\n        inputParameters:\n        - name: employeeId\n          in: path\n          type: string\n          required: true\n          description: Employee identifier\n        - name: year\n          in: query\n          type: integer\n          required: false\n          description: Plan year\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: employee-benefits\n      path: /employees/{employeeId}/benefits\n      description:\
  \ Employee benefits enrollment\n      operations:\n      - name: get-employee-benefits\n        method: GET\n        description: Get benefits enrollment summary for an employee\n        inputParameters:\n        - name: employeeId\n          in: path\n          type: string\n          required: true\n          description: Employee identifier\n        - name: planYear\n          in: query\n          type: integer\n          required: false\n          description: Benefits plan year\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: content\n      path: /content\n      description: HR content management\n      operations:\n      - name: list-content\n        method: GET\n        description: List HR content and communications\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Content type filter\n        -\
  \ name: audience\n          in: query\n          type: string\n          required: false\n          description: Target audience filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-content\n        method: POST\n        description: Create a new HR content item\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            type: '{{tools.type}}'\n            body: '{{tools.body}}'\n            audience: '{{tools.audience}}'\n    - name: cases\n      path: /cases\n      description: HR service case management\n      operations:\n      - name: list-cases\n        method: GET\n        description: List HR service cases\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n      \
  \    required: false\n          description: Filter by status\n        - name: category\n          in: query\n          type: string\n          required: false\n          description: Filter by category\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-case\n        method: POST\n        description: Submit a new HR service case\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            employeeId: '{{tools.employeeId}}'\n            category: '{{tools.category}}'\n            subject: '{{tools.subject}}'\n            description: '{{tools.description}}'\n    - name: case\n      path: /cases/{caseId}\n      description: Individual case\n      operations:\n      - name: get-case\n        method: GET\n        description: Get an HR service case\n        inputParameters:\n\
  \        - name: caseId\n          in: path\n          type: string\n          required: true\n          description: Case identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: wtw-employee-api\n    description: Unified REST API for WTW employee digital experience management.\n    resources:\n    - path: /v1/employees\n      name: employees\n      description: Employee management\n      operations:\n      - method: GET\n        name: list-employees\n        description: List all employees\n        call: wtw-hr-portal.list-employees\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/employees/{employeeId}\n      name: employee\n      description: Individual employee\n      operations:\n      - method: GET\n        name: get-employee\n        description: Get employee profile\n        call: wtw-hr-portal.get-employee\n\
  \        with:\n          employeeId: rest.employeeId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/employees/{employeeId}/total-rewards\n      name: total-rewards\n      description: Total compensation and rewards\n      operations:\n      - method: GET\n        name: get-employee-total-rewards\n        description: Get total rewards statement\n        call: wtw-hr-portal.get-employee-total-rewards\n        with:\n          employeeId: rest.employeeId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/employees/{employeeId}/benefits\n      name: employee-benefits\n      description: Employee benefits enrollment\n      operations:\n      - method: GET\n        name: get-employee-benefits\n        description: Get benefits summary\n        call: wtw-hr-portal.get-employee-benefits\n        with:\n          employeeId: rest.employeeId\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/content\n      name: content\n      description: HR content and communications\n      operations:\n      - method: GET\n        name: list-content\n        description: List HR content\n        call: wtw-hr-portal.list-content\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-content\n        description: Create HR content\n        call: wtw-hr-portal.create-content\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cases\n      name: cases\n      description: HR service cases\n      operations:\n      - method: GET\n        name: list-cases\n        description: List HR cases\n        call: wtw-hr-portal.list-cases\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-case\n        description: Create a new case\n        call: wtw-hr-portal.create-case\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: wtw-employee-mcp\n    transport: http\n    description: MCP server for AI-assisted WTW HR employee experience workflows.\n    tools:\n    - name: list-employees\n      description: List all employees in the HR portal with optional department and status filters\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wtw-hr-portal.list-employees\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-employee\n      description: Get HR portal profile for a specific employee\n      hints:\n        readOnly: true\n        idempotent: true\n      call: wtw-hr-portal.get-employee\n      with:\n        employeeId: tools.employeeId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-total-rewards\n      description: Get total compensation and rewards statement for an employee\n      hints:\n        readOnly: true\n        idempotent: true\n\
  \      call: wtw-hr-portal.get-employee-total-rewards\n      with:\n        employeeId: tools.employeeId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-benefits-enrollment\n      description: Get current benefits enrollment summary for an employee\n      hints:\n        readOnly: true\n        idempotent: true\n      call: wtw-hr-portal.get-employee-benefits\n      with:\n        employeeId: tools.employeeId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-hr-content\n      description: List HR content articles, announcements, and policies\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wtw-hr-portal.list-content\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publish-hr-content\n      description: Create and publish a new HR content item or announcement\n      hints:\n        readOnly: false\n      call: wtw-hr-portal.create-content\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-hr-cases\n      description: List HR service cases with optional status and category filters\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wtw-hr-portal.list-cases\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-hr-case\n      description: Submit a new HR service case or employee inquiry\n      hints:\n        readOnly: false\n      call: wtw-hr-portal.create-case\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-hr-case\n      description: Get details and status for a specific HR service case\n      hints:\n        readOnly: true\n        idempotent: true\n      call: wtw-hr-portal.get-case\n      with:\n        caseId: tools.caseId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
