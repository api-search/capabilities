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
- list applications
- job postings.
- create employee
- list employees from the connected hris.
- hris list employees
- ats create candidate
- create a time off request.
- create a new candidate in the ats.
- Recruiter
- candidate pipeline management.
- manages tickets and customer support issues.
- create a new employee.
- create a new candidate.
- time off management.
- recruiting
- list jobs
- manages employee records, time off, and hr processes.
- hris create employee
- list all applications.
- crm, leads, opportunities, and engagements.
- ats list offers
- merge
- ats
- application tracking.
- list time off requests.
- list all applications from the ats.
- file storage, sharing, and permissions.
- integrations
- list employees
- list all offers.
- manages invoices, payments, and financial reporting.
- manages leads, opportunities, and crm activities.
- list all employees.
- HR Manager
- list companies from the hris.
- list candidates
- invoicing, payments, expenses, and financial reporting.
- ats list interviews
- create candidate
- end-to-end talent management combining hris and ats.
- ticket management and customer communication.
- platform
- unified api
- hris
- candidate sourcing, applications, interviews, and offers.
- list time off
- list scheduled interviews.
- list candidates from the connected ats.
- ats list applications
- hris list companies
- hris create time off
- ats list candidates
- list all open job postings.
- employee records.
- manages candidate pipeline and hiring workflow.
- create an employee in the hris.
- hris list time off
- list all job postings.
- ats list jobs
- list all candidates.
- employee management, benefits, time off, and payroll.
- talent management
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
