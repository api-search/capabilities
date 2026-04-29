---
api_specs:
- filename: hcm.yml
  format: yaml
  label: hcm
  slug: hcm
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/openapi/hcm.yml
- filename: recruiting-talent-management.yml
  format: yaml
  label: recruiting
  slug: recruiting
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/openapi/recruiting-talent-management.yml
- filename: approval-workflow-engine.yml
  format: yaml
  label: approval-workflow
  slug: approval-workflow
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/openapi/approval-workflow-engine.yml
categories:
- payroll-hr
consumed_apis:
- hcm
- recruiting
- approval-workflow
description: Unified workflow for HR administrators combining employee management, benefits, payroll, recruiting, talent management, and approval workflows across PeopleSoft HCM, Recruiting, and Approval Workflow Engine APIs.
layout: capability
name: PeopleSoft Human Resources
operations:
- description: Retrieve employee records with optional department and status filters.
  method: GET
  name: list-employees
  path: /v1/employees
- description: Retrieve details for a specific employee.
  method: GET
  name: get-employee
  path: /v1/employees/{employeeId}
- description: Retrieve benefit enrollment records.
  method: GET
  name: list-benefit-enrollments
  path: /v1/benefit-enrollments
- description: Retrieve payroll run history and status.
  method: GET
  name: list-payroll-runs
  path: /v1/payroll-runs
- description: Search available job postings.
  method: GET
  name: search-jobs
  path: /v1/jobs
- description: Retrieve details for a specific job posting.
  method: GET
  name: get-job-details
  path: /v1/jobs/{jobId}
- description: Submit a candidate application for a job posting.
  method: POST
  name: submit-application
  path: /v1/applications
- description: Retrieve pending HR approval requests.
  method: GET
  name: list-pending-approvals
  path: /v1/approvals
- description: Approve, deny, or push back an HR approval request.
  method: PUT
  name: process-approval
  path: /v1/approvals/{approvalId}
personas: []
provider_name: PeopleSoft
provider_slug: peoplesoft
search_terms:
- candidate applications
- job posting details
- list payroll runs
- campus solutions.
- retrieve employee records with optional department and status filters.
- list employees
- retrieve details for a specific employee.
- hr approval requests
- enterprise software
- crm
- individual approval operations
- search available job postings.
- human capital management.
- human resources
- hcm
- process approval
- employee records
- retrieve benefit enrollment records.
- recruiting
- retrieve payroll run history and status.
- erp
- benefit enrollment records
- get job details
- financial management
- retrieve details for a specific job posting.
- financial and supply chain management.
- list pending approvals
- supply chain management
- submit a candidate application for a job posting.
- retrieve pending hr approval requests.
- payroll
- individual employee details
- campus solutions
- payroll run history and status
- peopletools platform services.
- talent management
- approve, deny, or push back an hr approval request.
- list benefit enrollments
- job postings
- peoplesoft
- submit application
- get employee
- search jobs
slug: human-resources
source_filename: human-resources.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"PeopleSoft Human Resources\"\n  description: \"Unified workflow for HR administrators combining employee management, benefits, payroll, recruiting, talent management, and approval workflows across PeopleSoft HCM, Recruiting, and Approval Workflow Engine APIs.\"\n  tags:\n    - PeopleSoft\n    - Human Resources\n    - HCM\n    - Recruiting\n    - Talent Management\n    - Payroll\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      PEOPLESOFT_USERNAME: PEOPLESOFT_USERNAME\n      PEOPLESOFT_PASSWORD: PEOPLESOFT_PASSWORD\n\ncapability:\n  consumes:\n    - import: hcm\n      location: ./shared/hcm.yaml\n    - import: recruiting\n      location: ./shared/recruiting-talent-management.yaml\n    - import: approval-workflow\n      location: ./shared/approval-workflow-engine.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: hr-api\n      description: \"Unified REST API\
  \ for PeopleSoft human resources workflows.\"\n      resources:\n        - path: /v1/employees\n          name: employees\n          description: \"Employee records\"\n          operations:\n            - method: GET\n              name: list-employees\n              description: \"Retrieve employee records with optional department and status filters.\"\n              call: \"hcm.list-employees\"\n              with:\n                department: \"rest.department\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/employees/{employeeId}\n          name: employee-detail\n          description: \"Individual employee details\"\n          operations:\n            - method: GET\n              name: get-employee\n              description: \"Retrieve details for a specific employee.\"\n              call: \"hcm.get-employee\"\n              with:\n                employeeId: \"rest.employeeId\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/benefit-enrollments\n          name: benefit-enrollments\n          description: \"Benefit enrollment records\"\n          operations:\n            - method: GET\n              name: list-benefit-enrollments\n              description: \"Retrieve benefit enrollment records.\"\n              call: \"hcm.list-benefit-enrollments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/payroll-runs\n          name: payroll-runs\n          description: \"Payroll run history and status\"\n          operations:\n            - method: GET\n              name: list-payroll-runs\n              description: \"Retrieve payroll run history and status.\"\n              call: \"hcm.list-payroll-runs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path:\
  \ /v1/jobs\n          name: jobs\n          description: \"Job postings\"\n          operations:\n            - method: GET\n              name: search-jobs\n              description: \"Search available job postings.\"\n              call: \"recruiting.search-jobs\"\n              with:\n                keyword: \"rest.keyword\"\n                location: \"rest.location\"\n                department: \"rest.department\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/jobs/{jobId}\n          name: job-detail\n          description: \"Job posting details\"\n          operations:\n            - method: GET\n              name: get-job-details\n              description: \"Retrieve details for a specific job posting.\"\n              call: \"recruiting.get-job-details\"\n              with:\n                jobId: \"rest.jobId\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n        - path: /v1/applications\n          name: applications\n          description: \"Candidate applications\"\n          operations:\n            - method: POST\n              name: submit-application\n              description: \"Submit a candidate application for a job posting.\"\n              call: \"recruiting.submit-application\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/approvals\n          name: approvals\n          description: \"HR approval requests\"\n          operations:\n            - method: GET\n              name: list-pending-approvals\n              description: \"Retrieve pending HR approval requests.\"\n              call: \"approval-workflow.list-pending-approvals\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/approvals/{approvalId}\n          name: approval-detail\n          description: \"Individual\
  \ approval operations\"\n          operations:\n            - method: PUT\n              name: process-approval\n              description: \"Approve, deny, or push back an HR approval request.\"\n              call: \"approval-workflow.process-approval\"\n              with:\n                approvalId: \"rest.approvalId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: hr-mcp\n      transport: http\n      description: \"MCP server for AI-assisted PeopleSoft human resources workflows.\"\n      tools:\n        - name: list-employees\n          description: \"Retrieve employee records with optional department and status filters.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hcm.list-employees\"\n          with:\n            department: \"tools.department\"\n            status: \"tools.status\"\n          outputParameters:\n        \
  \    - type: object\n              mapping: \"$.\"\n        - name: get-employee\n          description: \"Retrieve details for a specific employee.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hcm.get-employee\"\n          with:\n            employeeId: \"tools.employeeId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-benefit-enrollments\n          description: \"Retrieve benefit enrollment records.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hcm.list-benefit-enrollments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-payroll-runs\n          description: \"Retrieve payroll run history and status.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hcm.list-payroll-runs\"\n          outputParameters:\n            -\
  \ type: object\n              mapping: \"$.\"\n        - name: search-jobs\n          description: \"Search available job postings.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"recruiting.search-jobs\"\n          with:\n            keyword: \"tools.keyword\"\n            location: \"tools.location\"\n            department: \"tools.department\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-job-details\n          description: \"Retrieve details for a specific job posting.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"recruiting.get-job-details\"\n          with:\n            jobId: \"tools.jobId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: submit-application\n          description: \"Submit a candidate application for a job posting.\"\n          hints:\n          \
  \  readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"recruiting.submit-application\"\n          with:\n            jobId: \"tools.jobId\"\n            candidateInfo: \"tools.candidateInfo\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-pending-approvals\n          description: \"Retrieve pending HR approval requests.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"approval-workflow.list-pending-approvals\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: process-approval\n          description: \"Approve, deny, or push back an HR approval request.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"approval-workflow.process-approval\"\n          with:\n            approvalId: \"tools.approvalId\"\n\
  \            action: \"tools.action\"\n            comments: \"tools.comments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/capabilities/human-resources.yaml
tags:
- PeopleSoft
- Human Resources
- HCM
- Recruiting
- Talent Management
- Payroll
tools:
- description: Retrieve employee records with optional department and status filters.
  hints:
    openWorld: true
    readOnly: true
  name: list-employees
- description: Retrieve details for a specific employee.
  hints:
    openWorld: true
    readOnly: true
  name: get-employee
- description: Retrieve benefit enrollment records.
  hints:
    openWorld: true
    readOnly: true
  name: list-benefit-enrollments
- description: Retrieve payroll run history and status.
  hints:
    openWorld: true
    readOnly: true
  name: list-payroll-runs
- description: Search available job postings.
  hints:
    openWorld: true
    readOnly: true
  name: search-jobs
- description: Retrieve details for a specific job posting.
  hints:
    openWorld: true
    readOnly: true
  name: get-job-details
- description: Submit a candidate application for a job posting.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submit-application
- description: Retrieve pending HR approval requests.
  hints:
    openWorld: true
    readOnly: true
  name: list-pending-approvals
- description: Approve, deny, or push back an HR approval request.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: process-approval
---
