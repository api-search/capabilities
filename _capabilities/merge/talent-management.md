---
api_specs:
- filename: merge-hris-api-openapi.yaml
  format: yaml
  label: merge-hris
  slug: merge-hris
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/merge/refs/heads/main/openapi/merge-hris-api-openapi.yaml
- filename: merge-ats-api-openapi.yaml
  format: yaml
  label: merge-ats
  slug: merge-ats
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/merge/refs/heads/main/openapi/merge-ats-api-openapi.yaml
categories:
- recruiting-ats
consumed_apis:
- merge-hris
- merge-ats
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
- list time off
- ats create candidate
- ats
- list all open job postings.
- list candidates
- hris list employees
- manages employee records, time off, and hr processes.
- manages candidate pipeline and hiring workflow.
- invoicing, payments, expenses, and financial reporting.
- ats list offers
- hris list time off
- list scheduled interviews.
- ats list applications
- list employees from the connected hris.
- hris list companies
- hris create employee
- ats list jobs
- list all applications.
- employee management, benefits, time off, and payroll.
- ats list candidates
- ticket management and customer communication.
- hris
- employee records.
- ats list interviews
- list all applications from the ats.
- create a new employee.
- application tracking.
- HR Manager
- list all candidates.
- create a new candidate.
- list jobs
- list all job postings.
- recruiting
- create a time off request.
- time off management.
- end-to-end talent management combining hris and ats.
- crm, leads, opportunities, and engagements.
- list candidates from the connected ats.
- list employees
- list applications
- manages leads, opportunities, and crm activities.
- file storage, sharing, and permissions.
- unified api
- create employee
- list companies from the hris.
- create candidate
- manages tickets and customer support issues.
- integrations
- list all offers.
- list all employees.
- manages invoices, payments, and financial reporting.
- candidate pipeline management.
- create a new candidate in the ats.
- talent management
- hris create time off
- platform
- merge
- job postings.
- candidate sourcing, applications, interviews, and offers.
- create an employee in the hris.
- Recruiter
- list time off requests.
slug: talent-management
source_filename: talent-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Merge Talent Management\"\n  description: \"Unified workflow combining HRIS and ATS APIs for end-to-end talent management, from candidate sourcing through onboarding and employee lifecycle. Used by HR teams, recruiters, and people operations.\"\n  tags:\n    - Merge\n    - Talent Management\n    - HRIS\n    - ATS\n    - Recruiting\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      MERGE_API_KEY: MERGE_API_KEY\n      MERGE_ACCOUNT_TOKEN: MERGE_ACCOUNT_TOKEN\n\ncapability:\n  consumes:\n    - import: merge-hris\n      location: ./shared/merge-hris-api.yaml\n    - import: merge-ats\n      location: ./shared/merge-ats-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: merge-talent-api\n      description: \"Unified REST API for talent management across HRIS and ATS.\"\n      resources:\n        - path: /v1/candidates\n          name: candidates\n         \
  \ description: \"Candidate pipeline management.\"\n          operations:\n            - method: GET\n              name: list-candidates\n              description: \"List all candidates.\"\n              call: \"merge-ats.list-candidates\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-candidate\n              description: \"Create a new candidate.\"\n              call: \"merge-ats.create-candidate\"\n              with:\n                model: \"rest.model\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/applications\n          name: applications\n          description: \"Application tracking.\"\n          operations:\n            - method: GET\n              name: list-applications\n              description: \"List all applications.\"\n              call: \"merge-ats.list-applications\"\n            \
  \  outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/jobs\n          name: jobs\n          description: \"Job postings.\"\n          operations:\n            - method: GET\n              name: list-jobs\n              description: \"List all job postings.\"\n              call: \"merge-ats.list-jobs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/employees\n          name: employees\n          description: \"Employee records.\"\n          operations:\n            - method: GET\n              name: list-employees\n              description: \"List all employees.\"\n              call: \"merge-hris.list-employees\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-employee\n              description: \"Create a new employee.\"\n              call: \"merge-hris.create-employee\"\
  \n              with:\n                model: \"rest.model\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/time-off\n          name: time-off\n          description: \"Time off management.\"\n          operations:\n            - method: GET\n              name: list-time-off\n              description: \"List time off requests.\"\n              call: \"merge-hris.list-time-off\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: merge-talent-mcp\n      transport: http\n      description: \"MCP server for AI-assisted talent management.\"\n      tools:\n        - name: ats-list-candidates\n          description: \"List candidates from the connected ATS.\"\n          hints:\n            readOnly: true\n          call: \"merge-ats.list-candidates\"\n          outputParameters:\n            - type: object\n       \
  \       mapping: \"$.\"\n        - name: ats-create-candidate\n          description: \"Create a new candidate in the ATS.\"\n          hints:\n            readOnly: false\n          call: \"merge-ats.create-candidate\"\n          with:\n            model: \"tools.model\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ats-list-applications\n          description: \"List all applications from the ATS.\"\n          hints:\n            readOnly: true\n          call: \"merge-ats.list-applications\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ats-list-jobs\n          description: \"List all open job postings.\"\n          hints:\n            readOnly: true\n          call: \"merge-ats.list-jobs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ats-list-interviews\n          description: \"List scheduled interviews.\"\
  \n          hints:\n            readOnly: true\n          call: \"merge-ats.list-interviews\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ats-list-offers\n          description: \"List all offers.\"\n          hints:\n            readOnly: true\n          call: \"merge-ats.list-offers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: hris-list-employees\n          description: \"List employees from the connected HRIS.\"\n          hints:\n            readOnly: true\n          call: \"merge-hris.list-employees\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: hris-create-employee\n          description: \"Create an employee in the HRIS.\"\n          hints:\n            readOnly: false\n          call: \"merge-hris.create-employee\"\n          with:\n            model: \"tools.model\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: hris-list-companies\n          description: \"List companies from the HRIS.\"\n          hints:\n            readOnly: true\n          call: \"merge-hris.list-companies\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: hris-list-time-off\n          description: \"List time off requests.\"\n          hints:\n            readOnly: true\n          call: \"merge-hris.list-time-off\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: hris-create-time-off\n          description: \"Create a time off request.\"\n          hints:\n            readOnly: false\n          call: \"merge-hris.create-time-off\"\n          with:\n            model: \"tools.model\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
