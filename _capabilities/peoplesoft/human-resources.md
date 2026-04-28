---
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
- recruiting
- peoplesoft
- peopletools platform services.
- retrieve employee records with optional department and status filters.
- search available job postings.
- process approval
- benefit enrollment records
- list benefit enrollments
- retrieve details for a specific job posting.
- approve, deny, or push back an hr approval request.
- campus solutions
- candidate applications
- payroll run history and status
- talent management
- search jobs
- list employees
- retrieve details for a specific employee.
- retrieve pending hr approval requests.
- campus solutions.
- get job details
- human capital management.
- human resources
- job postings
- submit a candidate application for a job posting.
- enterprise software
- individual employee details
- financial management
- retrieve payroll run history and status.
- list pending approvals
- supply chain management
- hr approval requests
- payroll
- submit application
- employee records
- hcm
- retrieve benefit enrollment records.
- job posting details
- list payroll runs
- individual approval operations
- financial and supply chain management.
- crm
- erp
- get employee
slug: human-resources
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
