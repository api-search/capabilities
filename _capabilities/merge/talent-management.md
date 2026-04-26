---
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
- ticket management and customer communication.
- create employee
- list jobs
- ats
- create a new candidate.
- list time off
- invoicing, payments, expenses, and financial reporting.
- integrations
- list candidates
- ats create candidate
- list employees
- employee management, benefits, time off, and payroll.
- ats list jobs
- HR Manager
- candidate sourcing, applications, interviews, and offers.
- candidate pipeline management.
- ats list interviews
- create candidate
- job postings.
- list scheduled interviews.
- manages invoices, payments, and financial reporting.
- ats list candidates
- list time off requests.
- crm, leads, opportunities, and engagements.
- create a time off request.
- Recruiter
- list all applications from the ats.
- list all offers.
- manages employee records, time off, and hr processes.
- hris
- platform
- list all applications.
- list all employees.
- create an employee in the hris.
- unified api
- manages candidate pipeline and hiring workflow.
- hris create employee
- manages tickets and customer support issues.
- list all open job postings.
- hris list time off
- application tracking.
- create a new employee.
- merge
- list employees from the connected hris.
- ats list applications
- hris list employees
- list all candidates.
- end-to-end talent management combining hris and ats.
- list candidates from the connected ats.
- time off management.
- manages leads, opportunities, and crm activities.
- ats list offers
- list applications
- hris list companies
- talent management
- list all job postings.
- list companies from the hris.
- file storage, sharing, and permissions.
- hris create time off
- employee records.
- recruiting
- create a new candidate in the ats.
slug: talent-management
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
