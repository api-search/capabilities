---
categories:
- recruiting-ats
consumed_apis: []
description: Unified workflow combining HRIS and ATS APIs for end-to-end talent management, from candidate sourcing through onboarding and employee lifecycle. Used by HR teams, recruiters, and people operations.
layout: capability
name: Merge Talent Management
operations:
- description: List all candidates.
  method: GET
  name: list-candidates
  path: /v1/candidates
- description: Create a new candidate.
  method: POST
  name: create-candidate
  path: /v1/candidates
- description: List all applications.
  method: GET
  name: list-applications
  path: /v1/applications
- description: List all job postings.
  method: GET
  name: list-jobs
  path: /v1/jobs
- description: List all employees.
  method: GET
  name: list-employees
  path: /v1/employees
- description: Create a new employee.
  method: POST
  name: create-employee
  path: /v1/employees
- description: List time off requests.
  method: GET
  name: list-time-off
  path: /v1/time-off
personas: []
provider_name: Merge
provider_slug: merge
search_terms:
- employee management, benefits, time off, and payroll.
- create a new candidate in the ats.
- hris list companies
- application tracking.
- create a new employee.
- list jobs
- ats create candidate
- recruiting
- hris list time off
- list time off
- manages employee records, time off, and hr processes.
- manages tickets and customer support issues.
- ats
- ticket management and customer communication.
- ats list interviews
- hris create employee
- unified api
- manages leads, opportunities, and crm activities.
- talent management
- manages candidate pipeline and hiring workflow.
- list candidates from the connected ats.
- ats list jobs
- end-to-end talent management combining hris and ats.
- time off management.
- hris list employees
- create candidate
- create a time off request.
- crm, leads, opportunities, and engagements.
- invoicing, payments, expenses, and financial reporting.
- list candidates
- list all applications.
- list employees from the connected hris.
- file storage, sharing, and permissions.
- candidate pipeline management.
- integrations
- list all employees.
- create employee
- list all offers.
- ats list candidates
- employee records.
- list scheduled interviews.
- create an employee in the hris.
- hris
- list all open job postings.
- list employees
- list time off requests.
- ats list applications
- hris create time off
- list companies from the hris.
- manages invoices, payments, and financial reporting.
- merge
- Recruiter
- job postings.
- HR Manager
- platform
- create a new candidate.
- list all candidates.
- list applications
- ats list offers
- list all job postings.
- list all applications from the ats.
- candidate sourcing, applications, interviews, and offers.
slug: talent-management
source_filename: talent-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Merge Talent Management\n  description: Unified workflow combining HRIS and ATS APIs for end-to-end talent management, from candidate sourcing through\n    onboarding and employee lifecycle. Used by HR teams, recruiters, and people operations.\n  tags:\n  - Merge\n  - Talent Management\n  - HRIS\n  - ATS\n  - Recruiting\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    MERGE_API_KEY: MERGE_API_KEY\n    MERGE_ACCOUNT_TOKEN: MERGE_ACCOUNT_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: merge-hris\n    baseUri: https://api.merge.dev/api/hris/v1\n    description: Merge Unified HRIS API.\n    authentication:\n      type: bearer\n      token: '{{MERGE_API_KEY}}'\n    resources:\n    - name: employees\n      path: /employees\n      description: Employee operations.\n      operations:\n      - name: list-employees\n        method: GET\n        description: List all employees.\n        inputParameters:\n\
  \        - name: cursor\n          in: query\n          type: string\n          required: false\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-employee\n        method: POST\n        description: Create an employee.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: companies\n      path: /companies\n      description: Company operations.\n      operations:\n      - name: list-companies\n        method: GET\n        description: List all companies.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: time-off\n      path: /time-off\n\
  \      description: Time off operations.\n      operations:\n      - name: list-time-off\n        method: GET\n        description: List time off requests.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-time-off\n        method: POST\n        description: Create a time off request.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: merge-ats\n    baseUri: https://api.merge.dev/api/ats/v1\n    description: Merge Unified ATS API.\n    authentication:\n      type: bearer\n      token: '{{MERGE_API_KEY}}'\n    resources:\n    - name: candidates\n      path: /candidates\n      description: Candidate operations.\n      operations:\n      - name: list-candidates\n        method: GET\n        description:\
  \ List all candidates.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-candidate\n        method: POST\n        description: Create a candidate.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications\n      path: /applications\n      description: Application operations.\n      operations:\n      - name: list-applications\n        method: GET\n        description: List all applications.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-application\n        method: POST\n        description: Create an application.\n        body:\n          type: json\n          data:\n            model: '{{tools.model}}'\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs\n      path: /jobs\n      description: Job posting operations.\n      operations:\n      - name: list-jobs\n        method: GET\n        description: List all job postings.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: interviews\n      path: /interviews\n      description: Interview operations.\n      operations:\n      - name: list-interviews\n        method: GET\n        description: List all scheduled interviews.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: offers\n      path: /offers\n      description: Offer operations.\n      operations:\n      - name: list-offers\n        method: GET\n        description: List all offers.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: merge-talent-api\n    description: Unified REST API for talent management across HRIS and ATS.\n    resources:\n    - path: /v1/candidates\n      name: candidates\n      description: Candidate pipeline management.\n      operations:\n      - method: GET\n        name: list-candidates\n        description: List all candidates.\n        call: merge-ats.list-candidates\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-candidate\n        description: Create a new candidate.\n        call: merge-ats.create-candidate\n        with:\n          model: rest.model\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications\n      name: applications\n      description: Application tracking.\n      operations:\n      - method: GET\n \
  \       name: list-applications\n        description: List all applications.\n        call: merge-ats.list-applications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobs\n      name: jobs\n      description: Job postings.\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List all job postings.\n        call: merge-ats.list-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/employees\n      name: employees\n      description: Employee records.\n      operations:\n      - method: GET\n        name: list-employees\n        description: List all employees.\n        call: merge-hris.list-employees\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-employee\n        description: Create a new employee.\n        call: merge-hris.create-employee\n        with:\n          model: rest.model\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/time-off\n      name: time-off\n      description: Time off management.\n      operations:\n      - method: GET\n        name: list-time-off\n        description: List time off requests.\n        call: merge-hris.list-time-off\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: merge-talent-mcp\n    transport: http\n    description: MCP server for AI-assisted talent management.\n    tools:\n    - name: ats-list-candidates\n      description: List candidates from the connected ATS.\n      hints:\n        readOnly: true\n      call: merge-ats.list-candidates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ats-create-candidate\n      description: Create a new candidate in the ATS.\n      hints:\n        readOnly: false\n      call: merge-ats.create-candidate\n      with:\n        model: tools.model\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: ats-list-applications\n      description: List all applications from the ATS.\n      hints:\n        readOnly: true\n      call: merge-ats.list-applications\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ats-list-jobs\n      description: List all open job postings.\n      hints:\n        readOnly: true\n      call: merge-ats.list-jobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ats-list-interviews\n      description: List scheduled interviews.\n      hints:\n        readOnly: true\n      call: merge-ats.list-interviews\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ats-list-offers\n      description: List all offers.\n      hints:\n        readOnly: true\n      call: merge-ats.list-offers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: hris-list-employees\n      description: List employees from\
  \ the connected HRIS.\n      hints:\n        readOnly: true\n      call: merge-hris.list-employees\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: hris-create-employee\n      description: Create an employee in the HRIS.\n      hints:\n        readOnly: false\n      call: merge-hris.create-employee\n      with:\n        model: tools.model\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: hris-list-companies\n      description: List companies from the HRIS.\n      hints:\n        readOnly: true\n      call: merge-hris.list-companies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: hris-list-time-off\n      description: List time off requests.\n      hints:\n        readOnly: true\n      call: merge-hris.list-time-off\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: hris-create-time-off\n      description: Create a time off request.\n      hints:\n        readOnly:\
  \ false\n      call: merge-hris.create-time-off\n      with:\n        model: tools.model\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/merge/refs/heads/main/capabilities/talent-management.yaml
tags:
- Merge
- Talent Management
- HRIS
- ATS
- Recruiting
tools:
- description: List candidates from the connected ATS.
  hints:
    readOnly: true
  name: ats-list-candidates
- description: Create a new candidate in the ATS.
  hints:
    readOnly: false
  name: ats-create-candidate
- description: List all applications from the ATS.
  hints:
    readOnly: true
  name: ats-list-applications
- description: List all open job postings.
  hints:
    readOnly: true
  name: ats-list-jobs
- description: List scheduled interviews.
  hints:
    readOnly: true
  name: ats-list-interviews
- description: List all offers.
  hints:
    readOnly: true
  name: ats-list-offers
- description: List employees from the connected HRIS.
  hints:
    readOnly: true
  name: hris-list-employees
- description: Create an employee in the HRIS.
  hints:
    readOnly: false
  name: hris-create-employee
- description: List companies from the HRIS.
  hints:
    readOnly: true
  name: hris-list-companies
- description: List time off requests.
  hints:
    readOnly: true
  name: hris-list-time-off
- description: Create a time off request.
  hints:
    readOnly: false
  name: hris-create-time-off
---
