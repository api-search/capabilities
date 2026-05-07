---
categories:
- payroll-hr
consumed_apis: []
description: Unified workforce development workflow using Acadia's Connected Worker Platform for managing employee training, skills matrices, work instructions, and quizzes. Used by HR managers, training coordinators, and operations managers to track and improve frontline worker capabilities.
layout: capability
name: Acadia Workforce Development
operations:
- description: List all digital work instructions
  method: GET
  name: list-work-instructions
  path: /v1/work-instructions
- description: List all employees with training completion data
  method: GET
  name: list-employees
  path: /v1/employees
- description: Get skills matrix for a specific employee
  method: GET
  name: get-employee-skills
  path: /v1/employees/{id}/skills
- description: List all job roles with training requirements
  method: GET
  name: list-roles
  path: /v1/roles
personas:
- description: HR professional managing employee training records, skills matrices, and role requirements
  id: hr-manager
  name: HR Manager
- description: Professional responsible for creating and assigning work instructions and quizzes
  id: training-coordinator
  name: Training Coordinator
- description: Manager monitoring team skill gaps, compliance, and training completion rates
  id: operations-manager
  name: Operations Manager
provider_name: Acadia
provider_slug: acadia
search_terms:
- tracking and managing employee skills, roles, and career development
- list all digital work instructions with status and category filtering
- list employees with training completion percentages, filtered by role or department
- get the complete skills matrix for an employee showing required and completed skills
- acadia
- list quizzes
- end-to-end employee training management from work instructions to skill validation
- manage digital work instructions
- get employee skills
- list all employees with training completion data
- list all active quizzes and assessments available in the platform
- knowledge management
- skills management
- manufacturing
- manager monitoring team skill gaps, compliance, and training completion rates
- operations manager
- list all job roles with training requirements
- hr manager
- get employee skills matrix
- list employees
- professional responsible for creating and assigning work instructions and quizzes
- training management
- digital work instructions, employee skills, quizzes, and role management
- training
- list job roles and training requirements
- list employees and their training status
- list all job roles with training requirements and completion rates
- training coordinator
- list work instructions
- create work instruction
- hr professional managing employee training records, skills matrices, and role requirements
- list roles
- workforce development
- list all digital work instructions
- create a new digital work instruction with title, category, and steps
- get skills matrix for a specific employee
- connected worker
slug: workforce-development
source_filename: workforce-development.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Acadia Workforce Development\n  description: Unified workforce development workflow using Acadia's Connected Worker Platform for managing employee training,\n    skills matrices, work instructions, and quizzes. Used by HR managers, training coordinators, and operations managers to\n    track and improve frontline worker capabilities.\n  tags:\n  - Acadia\n  - Workforce Development\n  - Connected Worker\n  - Training Management\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ACADIA_API_TOKEN: ACADIA_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: acadia\n    baseUri: https://api.acadia-software.com/v1\n    description: Acadia Platform REST API\n    authentication:\n      type: bearer\n      token: '{{env.ACADIA_API_TOKEN}}'\n    resources:\n    - name: work-instructions\n      path: /work-instructions\n      description: Digital work instruction management\n      operations:\n\
  \      - name: listWorkInstructions\n        method: GET\n        description: List all digital work instructions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createWorkInstruction\n        method: POST\n        description: Create a new work instruction\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            category: '{{tools.category}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: employees\n      path: /employees\n      description: Employee management\n      operations:\n      - name: listEmployees\n        method: GET\n        description: List all employees\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: employee-skills\n      path: /employees/{id}/skills\n\
  \      description: Employee skills matrix\n      operations:\n      - name: getEmployeeSkills\n        method: GET\n        description: Get skills matrix for an employee\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Employee identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: quizzes\n      path: /quizzes\n      description: Quiz and assessment management\n      operations:\n      - name: listQuizzes\n        method: GET\n        description: List all quizzes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: roles\n      path: /roles\n      description: Job role management\n      operations:\n      - name: listRoles\n        method: GET\n        description: List all job roles\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: workforce-development-api\n    description: Unified REST API for workforce development and training management.\n    resources:\n    - path: /v1/work-instructions\n      name: work-instructions\n      description: Manage digital work instructions\n      operations:\n      - method: GET\n        name: list-work-instructions\n        description: List all digital work instructions\n        call: acadia.listWorkInstructions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/employees\n      name: employees\n      description: List employees and their training status\n      operations:\n      - method: GET\n        name: list-employees\n        description: List all employees with training completion data\n        call: acadia.listEmployees\n        outputParameters:\n        - type: object\n    \
  \      mapping: $.\n    - path: /v1/employees/{id}/skills\n      name: employee-skills\n      description: Get employee skills matrix\n      operations:\n      - method: GET\n        name: get-employee-skills\n        description: Get skills matrix for a specific employee\n        call: acadia.getEmployeeSkills\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/roles\n      name: roles\n      description: List job roles and training requirements\n      operations:\n      - method: GET\n        name: list-roles\n        description: List all job roles with training requirements\n        call: acadia.listRoles\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: workforce-development-mcp\n    transport: http\n    description: MCP server for AI-assisted workforce development and training management.\n    tools:\n    - name: list-work-instructions\n\
  \      description: List all digital work instructions with status and category filtering\n      hints:\n        readOnly: true\n        openWorld: false\n      call: acadia.listWorkInstructions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-work-instruction\n      description: Create a new digital work instruction with title, category, and steps\n      hints:\n        readOnly: false\n        openWorld: false\n      call: acadia.createWorkInstruction\n      with:\n        title: tools.title\n        category: tools.category\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-employees\n      description: List employees with training completion percentages, filtered by role or department\n      hints:\n        readOnly: true\n        openWorld: false\n      call: acadia.listEmployees\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-employee-skills\n      description: Get the complete\
  \ skills matrix for an employee showing required and completed skills\n      hints:\n        readOnly: true\n        openWorld: false\n      call: acadia.getEmployeeSkills\n      with:\n        id: tools.employee_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-quizzes\n      description: List all active quizzes and assessments available in the platform\n      hints:\n        readOnly: true\n        openWorld: false\n      call: acadia.listQuizzes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-roles\n      description: List all job roles with training requirements and completion rates\n      hints:\n        readOnly: true\n        openWorld: false\n      call: acadia.listRoles\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/acadia/refs/heads/main/capabilities/workforce-development.yaml
tags:
- Acadia
- Workforce Development
- Connected Worker
- Training Management
tools:
- description: List all digital work instructions with status and category filtering
  hints:
    openWorld: false
    readOnly: true
  name: list-work-instructions
- description: Create a new digital work instruction with title, category, and steps
  hints:
    openWorld: false
    readOnly: false
  name: create-work-instruction
- description: List employees with training completion percentages, filtered by role or department
  hints:
    openWorld: false
    readOnly: true
  name: list-employees
- description: Get the complete skills matrix for an employee showing required and completed skills
  hints:
    openWorld: false
    readOnly: true
  name: get-employee-skills
- description: List all active quizzes and assessments available in the platform
  hints:
    openWorld: false
    readOnly: true
  name: list-quizzes
- description: List all job roles with training requirements and completion rates
  hints:
    openWorld: false
    readOnly: true
  name: list-roles
---
