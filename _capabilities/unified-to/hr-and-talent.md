---
categories: []
consumed_apis:
- unified-hris
- unified-ats
description: Unified HR and talent acquisition workflow combining employee management, payroll, and applicant tracking across 223 HRIS and 73 ATS integrations. Used by HR technology developers, people operations teams, and talent acquisition platforms building cross-system workforce management tools.
layout: capability
name: Unified.to HR and Talent
operations:
- description: List employees from an HRIS integration
  method: GET
  name: list-hris-employees
  path: /v1/hris/{connection_id}/employees
- description: Create a new employee record
  method: POST
  name: create-hris-employee
  path: /v1/hris/{connection_id}/employees
- description: List HR groups and departments
  method: GET
  name: list-hris-groups
  path: /v1/hris/{connection_id}/groups
- description: List employee payslips
  method: GET
  name: list-hris-payslips
  path: /v1/hris/{connection_id}/payslips
- description: List open job postings
  method: GET
  name: list-ats-jobs
  path: /v1/ats/{connection_id}/jobs
- description: List candidates
  method: GET
  name: list-ats-candidates
  path: /v1/ats/{connection_id}/candidates
- description: Create a new candidate
  method: POST
  name: create-ats-candidate
  path: /v1/ats/{connection_id}/candidates
- description: List job applications
  method: GET
  name: list-ats-applications
  path: /v1/ats/{connection_id}/applications
personas: []
provider_name: Unified.to
provider_slug: unified-to
search_terms:
- hris
- create a new candidate
- list hris payslips
- create a new candidate in a connected ats integration
- list ats jobs
- list hr groups and departments from a connected hris integration
- Finance Operations Engineer
- candidate profiles from ats integrations
- list job applications from a connected ats integration
- create a new employee record
- integrations
- hr
- list ats applications
- list ats interviews
- developers building invoicing automation, expense management, and accounting sync
- unified.to
- Revenue Operations Developer
- CRM Integrator
- unified api
- crm contact, company, and deal management across 47+ integrations
- list candidates
- create ats candidate
- HR Technology Developer
- list hris employees
- hris and ats management across 296+ hr and recruiting integrations
- developers building sales tools, crm sync, and revenue reporting integrations
- People Operations Engineer
- recruiting
- list open job postings from a connected ats integration (greenhouse, lever, etc.)
- list hris groups
- list open job postings
- list employees from a connected hris integration (workday, bamboohr, adp, etc.)
- job applications from ats integrations
- job postings from ats integrations
- list candidates from a connected ats integration
- Fintech Developer
- list hr groups and departments
- create hris employee
- list ats candidates
- list employees from an hris integration
- ats
- accounting, invoicing, and payment management across 41+ integrations
- create a new employee record in a connected hris integration
- list employee payslips
- employee data across hris integrations
- employee payslip data
- list job applications
- employees
- list employee payslips from a connected hris integration
- developers building hr workflows, employee onboarding, and recruiting automation
- hr groups and departments
- list scheduled interviews from a connected ats integration
slug: hr-and-talent
source_filename: hr-and-talent.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Unified.to HR and Talent\"\n  description: >-\n    Unified HR and talent acquisition workflow combining employee management, payroll,\n    and applicant tracking across 223 HRIS and 73 ATS integrations. Used by HR technology\n    developers, people operations teams, and talent acquisition platforms building\n    cross-system workforce management tools.\n  tags:\n    - Unified.to\n    - HRIS\n    - ATS\n    - HR\n    - Recruiting\n    - Employees\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      UNIFIED_TO_API_KEY: UNIFIED_TO_API_KEY\n\ncapability:\n  consumes:\n    - import: unified-hris\n      location: ./shared/hris-api.yaml\n    - import: unified-ats\n      location: ./shared/ats-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: unified-hr-talent-api\n      description: \"Unified REST API for HR and talent management across 296+ integrations.\"\n\
  \      resources:\n        - path: /v1/hris/{connection_id}/employees\n          name: employees\n          description: \"Employee data across HRIS integrations\"\n          operations:\n            - method: GET\n              name: list-hris-employees\n              description: \"List employees from an HRIS integration\"\n              call: \"unified-hris.list-hris-employees\"\n              with:\n                connection_id: \"rest.connection_id\"\n                query: \"rest.query\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-hris-employee\n              description: \"Create a new employee record\"\n              call: \"unified-hris.create-hris-employee\"\n              with:\n                connection_id: \"rest.connection_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"\
  $.\"\n\n        - path: /v1/hris/{connection_id}/groups\n          name: groups\n          description: \"HR groups and departments\"\n          operations:\n            - method: GET\n              name: list-hris-groups\n              description: \"List HR groups and departments\"\n              call: \"unified-hris.list-hris-groups\"\n              with:\n                connection_id: \"rest.connection_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/hris/{connection_id}/payslips\n          name: payslips\n          description: \"Employee payslip data\"\n          operations:\n            - method: GET\n              name: list-hris-payslips\n              description: \"List employee payslips\"\n              call: \"unified-hris.list-hris-payslips\"\n              with:\n                connection_id: \"rest.connection_id\"\n              outputParameters:\n                - type: object\n          \
  \        mapping: \"$.\"\n\n        - path: /v1/ats/{connection_id}/jobs\n          name: jobs\n          description: \"Job postings from ATS integrations\"\n          operations:\n            - method: GET\n              name: list-ats-jobs\n              description: \"List open job postings\"\n              call: \"unified-ats.list-ats-jobs\"\n              with:\n                connection_id: \"rest.connection_id\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/ats/{connection_id}/candidates\n          name: candidates\n          description: \"Candidate profiles from ATS integrations\"\n          operations:\n            - method: GET\n              name: list-ats-candidates\n              description: \"List candidates\"\n              call: \"unified-ats.list-ats-candidates\"\n              with:\n                connection_id: \"rest.connection_id\"\n           \
  \     query: \"rest.query\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-ats-candidate\n              description: \"Create a new candidate\"\n              call: \"unified-ats.create-ats-candidate\"\n              with:\n                connection_id: \"rest.connection_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/ats/{connection_id}/applications\n          name: applications\n          description: \"Job applications from ATS integrations\"\n          operations:\n            - method: GET\n              name: list-ats-applications\n              description: \"List job applications\"\n              call: \"unified-ats.list-ats-applications\"\n              with:\n                connection_id: \"rest.connection_id\"\n              outputParameters:\n    \
  \            - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: unified-hr-talent-mcp\n      transport: http\n      description: \"MCP server for AI-assisted HR and talent operations across 296+ integrations.\"\n      tools:\n        - name: list-hris-employees\n          description: \"List employees from a connected HRIS integration (Workday, BambooHR, ADP, etc.)\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unified-hris.list-hris-employees\"\n          with:\n            connection_id: \"tools.connection_id\"\n            query: \"tools.query\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-hris-employee\n          description: \"Create a new employee record in a connected HRIS integration\"\n          hints:\n            readOnly: false\n            destructive: false\n       \
  \     idempotent: false\n          call: \"unified-hris.create-hris-employee\"\n          with:\n            connection_id: \"tools.connection_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-hris-groups\n          description: \"List HR groups and departments from a connected HRIS integration\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unified-hris.list-hris-groups\"\n          with:\n            connection_id: \"tools.connection_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-hris-payslips\n          description: \"List employee payslips from a connected HRIS integration\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unified-hris.list-hris-payslips\"\n          with:\n            connection_id: \"tools.connection_id\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: list-ats-jobs\n          description: \"List open job postings from a connected ATS integration (Greenhouse, Lever, etc.)\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unified-ats.list-ats-jobs\"\n          with:\n            connection_id: \"tools.connection_id\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-ats-candidates\n          description: \"List candidates from a connected ATS integration\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unified-ats.list-ats-candidates\"\n          with:\n            connection_id: \"tools.connection_id\"\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-ats-candidate\n  \
  \        description: \"Create a new candidate in a connected ATS integration\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"unified-ats.create-ats-candidate\"\n          with:\n            connection_id: \"tools.connection_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-ats-applications\n          description: \"List job applications from a connected ATS integration\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unified-ats.list-ats-applications\"\n          with:\n            connection_id: \"tools.connection_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-ats-interviews\n          description: \"List scheduled interviews from a connected ATS integration\"\n          hints:\n            readOnly: true\n            openWorld:\
  \ false\n          call: \"unified-ats.list-ats-interviews\"\n          with:\n            connection_id: \"tools.connection_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/unified-to/refs/heads/main/capabilities/hr-and-talent.yaml
tags:
- Unified.to
- HRIS
- ATS
- HR
- Recruiting
- Employees
tools:
- description: List employees from a connected HRIS integration (Workday, BambooHR, ADP, etc.)
  hints:
    openWorld: false
    readOnly: true
  name: list-hris-employees
- description: Create a new employee record in a connected HRIS integration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-hris-employee
- description: List HR groups and departments from a connected HRIS integration
  hints:
    openWorld: false
    readOnly: true
  name: list-hris-groups
- description: List employee payslips from a connected HRIS integration
  hints:
    openWorld: false
    readOnly: true
  name: list-hris-payslips
- description: List open job postings from a connected ATS integration (Greenhouse, Lever, etc.)
  hints:
    openWorld: false
    readOnly: true
  name: list-ats-jobs
- description: List candidates from a connected ATS integration
  hints:
    openWorld: false
    readOnly: true
  name: list-ats-candidates
- description: Create a new candidate in a connected ATS integration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-ats-candidate
- description: List job applications from a connected ATS integration
  hints:
    openWorld: false
    readOnly: true
  name: list-ats-applications
- description: List scheduled interviews from a connected ATS integration
  hints:
    openWorld: false
    readOnly: true
  name: list-ats-interviews
---
