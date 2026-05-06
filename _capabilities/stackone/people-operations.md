---
categories: []
consumed_apis: []
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
- update employee
- list job applications across the connected ats system
- update employee information in the connected hris system
- list candidates from ats
- list jobs
- recruitment candidates
- list job applications
- list time off
- submit a time off request
- time off requests
- employee management across hris systems
- get employee by id
- create a new employee
- unified api
- get candidate details
- people operations
- list open jobs
- list all employees
- get detailed information for a specific employee
- create time off
- list candidates
- list all employees from a connected hris system (bamboohr, workday, etc.)
- list recruitment candidates from the connected ats system
- integrations
- open job positions
- create employee
- update employee details
- get candidate
- ipaas
- list time off requests from the connected hris system
- hris
- get employee
- list employees
- human resources
- list open job positions from the connected ats system
- recruitment
- create a new employee record in the connected hris system
- single employee
- job applications
- list time off requests
- get full profile for a recruitment candidate
- list applications
- single candidate
- submit a time off request for an employee
slug: people-operations
source_filename: people-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: StackOne People Operations\n  description: Unified workflow capability for HR and people operations using StackOne's unified APIs. Combines HRIS (employee\n    data, time-off, employments) and ATS (candidates, jobs, applications) into a single people operations interface. Designed\n    for HR teams, people analytics, and AI agents managing workforce data across multiple HR and recruitment platforms.\n  tags:\n  - Human Resources\n  - HRIS\n  - Recruitment\n  - Unified API\n  - People Operations\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    STACKONE_API_KEY: STACKONE_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: stackone\n    baseUri: https://api.stackone.com\n    description: StackOne unified integration platform API\n    authentication:\n      type: basic\n      username: '{{STACKONE_API_KEY}}'\n      password: ''\n    resources:\n    - name: accounts\n      path: /accounts\n\
  \      description: Manage linked integration accounts\n      operations:\n      - name: list-accounts\n        method: GET\n        description: List all linked integration accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-account\n        method: GET\n        description: Get a specific linked account\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-account\n        method: DELETE\n        description: Remove a linked account\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  \
  \  - name: connect-sessions\n      path: /connect_sessions\n      description: Manage integration connect sessions\n      operations:\n      - name: create-connect-session\n        method: POST\n        description: Create a connect session for onboarding\n        body:\n          type: json\n          data:\n            provider: '{{tools.provider}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hris-employees\n      path: /unified/hris/employees\n      description: HRIS employee management\n      operations:\n      - name: list-employees\n        method: GET\n        description: List employees across HRIS systems\n        inputParameters:\n        - name: x-account-id\n          in: header\n          type: string\n          required: true\n          description: StackOne account ID for the HRIS integration\n        - name: page\n          in: query\n          type: integer\n          required:\
  \ false\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-employee\n        method: GET\n        description: Get a specific employee\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: x-account-id\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-employee\n        method: POST\n        description: Create a new employee\n        inputParameters:\n        - name: x-account-id\n          in: header\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            first_name: '{{tools.first_name}}'\n\
  \            last_name: '{{tools.last_name}}'\n            email: '{{tools.email}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-employee\n        method: PATCH\n        description: Update an employee\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: x-account-id\n          in: header\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            fields: '{{tools.fields}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hris-time-off\n      path: /unified/hris/time_off\n      description: HRIS time off request management\n      operations:\n      - name: list-time-off\n        method: GET\n        description: List time off requests\n        inputParameters:\n\
  \        - name: x-account-id\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-time-off\n        method: POST\n        description: Create a time off request\n        inputParameters:\n        - name: x-account-id\n          in: header\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            employee_id: '{{tools.employee_id}}'\n            type: '{{tools.type}}'\n            start_date: '{{tools.start_date}}'\n            end_date: '{{tools.end_date}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ats-candidates\n      path: /unified/ats/candidates\n      description: ATS candidate management\n      operations:\n      - name: list-candidates\n        method: GET\n\
  \        description: List candidates across ATS systems\n        inputParameters:\n        - name: x-account-id\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-candidate\n        method: GET\n        description: Get a specific candidate\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: x-account-id\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ats-jobs\n      path: /unified/ats/jobs\n      description: ATS job management\n      operations:\n      - name: list-jobs\n        method: GET\n        description: List jobs across ATS systems\n        inputParameters:\n        - name:\
  \ x-account-id\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-job\n        method: GET\n        description: Get a specific job\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: x-account-id\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ats-applications\n      path: /unified/ats/applications\n      description: ATS application tracking\n      operations:\n      - name: list-applications\n        method: GET\n        description: List job applications\n        inputParameters:\n        - name: x-account-id\n          in: header\n          type: string\n          required: true\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-application\n        method: GET\n        description: Get a specific application\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: x-account-id\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: crm-contacts\n      path: /unified/crm/contacts\n      description: CRM contact management\n      operations:\n      - name: list-contacts\n        method: GET\n        description: List contacts across CRM systems\n        inputParameters:\n        - name: x-account-id\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: create-contact\n        method: POST\n        description: Create a new CRM contact\n        inputParameters:\n        - name: x-account-id\n          in: header\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            first_name: '{{tools.first_name}}'\n            last_name: '{{tools.last_name}}'\n            email: '{{tools.email}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: marketing-campaigns\n      path: /unified/marketing/campaigns\n      description: Marketing campaign management\n      operations:\n      - name: list-campaigns\n        method: GET\n        description: List campaigns across marketing platforms\n        inputParameters:\n        - name: x-account-id\n          in: header\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: proxy\n      path: /unified/proxy\n      description: Proxy requests to provider APIs\n      operations:\n      - name: proxy-request\n        method: POST\n        description: Forward a request directly to a provider API\n        inputParameters:\n        - name: x-account-id\n          in: header\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            path: '{{tools.path}}'\n            method: '{{tools.method}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: stackone-people-api\n    description: Unified REST API for people operations across HRIS and ATS platforms.\n    resources:\n    - path: /v1/employees\n      name: employees\n      description: Employee management across\
  \ HRIS systems\n      operations:\n      - method: GET\n        name: list-employees\n        description: List all employees\n        call: stackone.list-employees\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-employee\n        description: Create a new employee\n        call: stackone.create-employee\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/employees/{id}\n      name: employee\n      description: Single employee\n      operations:\n      - method: GET\n        name: get-employee\n        description: Get employee by ID\n        call: stackone.get-employee\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-employee\n        description: Update employee details\n        call: stackone.update-employee\n        with:\n          id: rest.id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/time-off\n      name: time-off\n      description: Time off requests\n      operations:\n      - method: GET\n        name: list-time-off\n        description: List time off requests\n        call: stackone.list-time-off\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-time-off\n        description: Submit a time off request\n        call: stackone.create-time-off\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/candidates\n      name: candidates\n      description: Recruitment candidates\n      operations:\n      - method: GET\n        name: list-candidates\n        description: List candidates from ATS\n        call: stackone.list-candidates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/candidates/{id}\n      name: candidate\n      description: Single candidate\n    \
  \  operations:\n      - method: GET\n        name: get-candidate\n        description: Get candidate details\n        call: stackone.get-candidate\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobs\n      name: jobs\n      description: Open job positions\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List open jobs\n        call: stackone.list-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications\n      name: applications\n      description: Job applications\n      operations:\n      - method: GET\n        name: list-applications\n        description: List job applications\n        call: stackone.list-applications\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: stackone-people-mcp\n    transport: http\n    description: MCP server for AI-assisted\
  \ people operations across HRIS and ATS systems.\n    tools:\n    - name: list-employees\n      description: List all employees from a connected HRIS system (BambooHR, Workday, etc.)\n      hints:\n        readOnly: true\n        openWorld: true\n      call: stackone.list-employees\n      with:\n        x-account-id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-employee\n      description: Get detailed information for a specific employee\n      hints:\n        readOnly: true\n      call: stackone.get-employee\n      with:\n        id: tools.employee_id\n        x-account-id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-employee\n      description: Create a new employee record in the connected HRIS system\n      hints:\n        readOnly: false\n      call: stackone.create-employee\n      with:\n        x-account-id: tools.account_id\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: update-employee\n      description: Update employee information in the connected HRIS system\n      hints:\n        readOnly: false\n        idempotent: true\n      call: stackone.update-employee\n      with:\n        id: tools.employee_id\n        x-account-id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-time-off\n      description: List time off requests from the connected HRIS system\n      hints:\n        readOnly: true\n      call: stackone.list-time-off\n      with:\n        x-account-id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-time-off\n      description: Submit a time off request for an employee\n      hints:\n        readOnly: false\n      call: stackone.create-time-off\n      with:\n        x-account-id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-candidates\n\
  \      description: List recruitment candidates from the connected ATS system\n      hints:\n        readOnly: true\n        openWorld: true\n      call: stackone.list-candidates\n      with:\n        x-account-id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-candidate\n      description: Get full profile for a recruitment candidate\n      hints:\n        readOnly: true\n      call: stackone.get-candidate\n      with:\n        id: tools.candidate_id\n        x-account-id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-jobs\n      description: List open job positions from the connected ATS system\n      hints:\n        readOnly: true\n      call: stackone.list-jobs\n      with:\n        x-account-id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-applications\n      description: List job applications across the connected\
  \ ATS system\n      hints:\n        readOnly: true\n      call: stackone.list-applications\n      with:\n        x-account-id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
