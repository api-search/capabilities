---
categories:
- payroll-hr
consumed_apis: []
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
- enterprise software
- talent management
- submit application
- job posting details
- retrieve pending hr approval requests.
- list pending approvals
- search available job postings.
- get job details
- retrieve details for a specific employee.
- individual approval operations
- job postings
- hcm
- individual employee details
- hr approval requests
- get employee
- crm
- retrieve payroll run history and status.
- human capital management.
- payroll
- financial management
- campus solutions.
- recruiting
- retrieve benefit enrollment records.
- candidate applications
- list payroll runs
- approve, deny, or push back an hr approval request.
- list benefit enrollments
- human resources
- retrieve details for a specific job posting.
- list employees
- search jobs
- peoplesoft
- campus solutions
- financial and supply chain management.
- payroll run history and status
- employee records
- benefit enrollment records
- erp
- peopletools platform services.
- supply chain management
- process approval
- submit a candidate application for a job posting.
- retrieve employee records with optional department and status filters.
slug: human-resources
source_filename: human-resources.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: PeopleSoft Human Resources\n  description: Unified workflow for HR administrators combining employee management, benefits, payroll, recruiting, talent\n    management, and approval workflows across PeopleSoft HCM, Recruiting, and Approval Workflow Engine APIs.\n  tags:\n  - PeopleSoft\n  - Human Resources\n  - HCM\n  - Recruiting\n  - Talent Management\n  - Payroll\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    PEOPLESOFT_USERNAME: PEOPLESOFT_USERNAME\n    PEOPLESOFT_PASSWORD: PEOPLESOFT_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: hcm\n    baseUri: https://${PEOPLESOFT_HOST}:${PEOPLESOFT_PORT}/psft/api/hcm/v1\n    description: PeopleSoft HCM API\n    authentication:\n      type: basic\n      username: '{{PEOPLESOFT_USERNAME}}'\n      password: '{{PEOPLESOFT_PASSWORD}}'\n    resources:\n    - name: employees\n      path: /employees\n      description: Employee data operations\n\
  \      operations:\n      - name: list-employees\n        method: GET\n        description: Retrieve a list of employee records.\n        inputParameters:\n        - name: department\n          in: query\n          type: string\n          required: false\n          description: Filter by department\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by employment status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-employee\n        method: GET\n        description: Retrieve details for a specific employee.\n        inputParameters:\n        - name: employeeId\n          in: path\n          type: string\n          required: true\n          description: The employee identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ benefits\n      path: /benefits\n      description: Benefits administration operations\n      operations:\n      - name: list-benefit-enrollments\n        method: GET\n        description: Retrieve benefit enrollment records.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payroll\n      path: /payroll\n      description: Payroll operations\n      operations:\n      - name: list-payroll-runs\n        method: GET\n        description: Retrieve payroll run history and status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: recruiting\n    baseUri: https://${PEOPLESOFT_HOST}:${PEOPLESOFT_PORT}/psft/api/hcm/recruiting/v1\n    description: PeopleSoft Recruiting and Talent Management API\n    authentication:\n      type: basic\n      username: '{{PEOPLESOFT_USERNAME}}'\n      password: '{{PEOPLESOFT_PASSWORD}}'\n\
  \    resources:\n    - name: jobs\n      path: /jobs\n      description: Job posting and search operations\n      operations:\n      - name: search-jobs\n        method: GET\n        description: Search available job postings.\n        inputParameters:\n        - name: keyword\n          in: query\n          type: string\n          required: false\n          description: Keyword search term\n        - name: location\n          in: query\n          type: string\n          required: false\n          description: Job location filter\n        - name: department\n          in: query\n          type: string\n          required: false\n          description: Department filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-job-details\n        method: GET\n        description: Retrieve details for a specific job posting.\n        inputParameters:\n        - name: jobId\n          in: path\n     \
  \     type: string\n          required: true\n          description: The job posting identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidates\n      path: /candidates\n      description: Candidate and application operations\n      operations:\n      - name: submit-application\n        method: POST\n        description: Submit a candidate application for a job posting.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            jobId: '{{tools.jobId}}'\n            candidateInfo: '{{tools.candidateInfo}}'\n  - type: http\n    namespace: approval-workflow\n    baseUri: https://${PEOPLESOFT_HOST}:${PEOPLESOFT_PORT}/psft/api/approvals/v1\n    description: PeopleSoft Approval Workflow Engine API\n    authentication:\n      type: basic\n      username: '{{PEOPLESOFT_USERNAME}}'\n\
  \      password: '{{PEOPLESOFT_PASSWORD}}'\n    resources:\n    - name: approvals\n      path: /approvals\n      description: Approval workflow operations\n      operations:\n      - name: list-pending-approvals\n        method: GET\n        description: Retrieve a list of pending approval requests for the current user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: process-approval\n        method: PUT\n        description: Approve, deny, or push back an approval request.\n        inputParameters:\n        - name: approvalId\n          in: path\n          type: string\n          required: true\n          description: The approval request identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            action: '{{tools.action}}'\n            comments: '{{tools.comments}}'\n\
  \  exposes:\n  - type: rest\n    port: 8080\n    namespace: hr-api\n    description: Unified REST API for PeopleSoft human resources workflows.\n    resources:\n    - path: /v1/employees\n      name: employees\n      description: Employee records\n      operations:\n      - method: GET\n        name: list-employees\n        description: Retrieve employee records with optional department and status filters.\n        call: hcm.list-employees\n        with:\n          department: rest.department\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/employees/{employeeId}\n      name: employee-detail\n      description: Individual employee details\n      operations:\n      - method: GET\n        name: get-employee\n        description: Retrieve details for a specific employee.\n        call: hcm.get-employee\n        with:\n          employeeId: rest.employeeId\n        outputParameters:\n        - type: object\n         \
  \ mapping: $.\n    - path: /v1/benefit-enrollments\n      name: benefit-enrollments\n      description: Benefit enrollment records\n      operations:\n      - method: GET\n        name: list-benefit-enrollments\n        description: Retrieve benefit enrollment records.\n        call: hcm.list-benefit-enrollments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payroll-runs\n      name: payroll-runs\n      description: Payroll run history and status\n      operations:\n      - method: GET\n        name: list-payroll-runs\n        description: Retrieve payroll run history and status.\n        call: hcm.list-payroll-runs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobs\n      name: jobs\n      description: Job postings\n      operations:\n      - method: GET\n        name: search-jobs\n        description: Search available job postings.\n        call: recruiting.search-jobs\n        with:\n          keyword:\
  \ rest.keyword\n          location: rest.location\n          department: rest.department\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobs/{jobId}\n      name: job-detail\n      description: Job posting details\n      operations:\n      - method: GET\n        name: get-job-details\n        description: Retrieve details for a specific job posting.\n        call: recruiting.get-job-details\n        with:\n          jobId: rest.jobId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications\n      name: applications\n      description: Candidate applications\n      operations:\n      - method: POST\n        name: submit-application\n        description: Submit a candidate application for a job posting.\n        call: recruiting.submit-application\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/approvals\n      name: approvals\n      description: HR approval\
  \ requests\n      operations:\n      - method: GET\n        name: list-pending-approvals\n        description: Retrieve pending HR approval requests.\n        call: approval-workflow.list-pending-approvals\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/approvals/{approvalId}\n      name: approval-detail\n      description: Individual approval operations\n      operations:\n      - method: PUT\n        name: process-approval\n        description: Approve, deny, or push back an HR approval request.\n        call: approval-workflow.process-approval\n        with:\n          approvalId: rest.approvalId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: hr-mcp\n    transport: http\n    description: MCP server for AI-assisted PeopleSoft human resources workflows.\n    tools:\n    - name: list-employees\n      description: Retrieve employee records with optional department and status\
  \ filters.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hcm.list-employees\n      with:\n        department: tools.department\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-employee\n      description: Retrieve details for a specific employee.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hcm.get-employee\n      with:\n        employeeId: tools.employeeId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-benefit-enrollments\n      description: Retrieve benefit enrollment records.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hcm.list-benefit-enrollments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-payroll-runs\n      description: Retrieve payroll run history and status.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hcm.list-payroll-runs\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-jobs\n      description: Search available job postings.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: recruiting.search-jobs\n      with:\n        keyword: tools.keyword\n        location: tools.location\n        department: tools.department\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-job-details\n      description: Retrieve details for a specific job posting.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: recruiting.get-job-details\n      with:\n        jobId: tools.jobId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-application\n      description: Submit a candidate application for a job posting.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: recruiting.submit-application\n      with:\n        jobId:\
  \ tools.jobId\n        candidateInfo: tools.candidateInfo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-pending-approvals\n      description: Retrieve pending HR approval requests.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: approval-workflow.list-pending-approvals\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: process-approval\n      description: Approve, deny, or push back an HR approval request.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: approval-workflow.process-approval\n      with:\n        approvalId: tools.approvalId\n        action: tools.action\n        comments: tools.comments\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
