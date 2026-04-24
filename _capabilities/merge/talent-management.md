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
- list all job postings.
- list scheduled interviews.
- list employees
- file storage, sharing, and permissions.
- create an employee in the hris.
- HR Manager
- job postings.
- create a new candidate.
- create candidate
- list time off requests.
- ats create candidate
- manages invoices, payments, and financial reporting.
- create employee
- ticket management and customer communication.
- unified api
- list time off
- ats list interviews
- list all open job postings.
- create a new employee.
- manages candidate pipeline and hiring workflow.
- ats
- list applications
- list companies from the hris.
- recruiting
- ats list offers
- hris list time off
- create a time off request.
- time off management.
- ats list candidates
- invoicing, payments, expenses, and financial reporting.
- hris
- list employees from the connected hris.
- list jobs
- list all applications.
- ats list jobs
- list all applications from the ats.
- candidate pipeline management.
- hris list companies
- employee records.
- list all candidates.
- list all employees.
- create a new candidate in the ats.
- end-to-end talent management combining hris and ats.
- Recruiter
- integrations
- list candidates
- candidate sourcing, applications, interviews, and offers.
- hris create employee
- application tracking.
- ats list applications
- hris list employees
- manages tickets and customer support issues.
- platform
- talent management
- manages leads, opportunities, and crm activities.
- crm, leads, opportunities, and engagements.
- list candidates from the connected ats.
- hris create time off
- manages employee records, time off, and hr processes.
- list all offers.
- employee management, benefits, time off, and payroll.
- merge
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
