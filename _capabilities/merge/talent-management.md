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
- manages invoices, payments, and financial reporting.
- employee management, benefits, time off, and payroll.
- ats list applications
- manages candidate pipeline and hiring workflow.
- list employees from the connected hris.
- recruiting
- employee records.
- list time off requests.
- file storage, sharing, and permissions.
- integrations
- list applications
- hris list time off
- platform
- list candidates
- invoicing, payments, expenses, and financial reporting.
- ats
- unified api
- list candidates from the connected ats.
- ats list jobs
- list all open job postings.
- create an employee in the hris.
- Recruiter
- manages tickets and customer support issues.
- ats list interviews
- HR Manager
- list all employees.
- ticket management and customer communication.
- end-to-end talent management combining hris and ats.
- list jobs
- application tracking.
- list all offers.
- list all job postings.
- job postings.
- list time off
- hris create time off
- create a new candidate.
- list employees
- ats create candidate
- crm, leads, opportunities, and engagements.
- list scheduled interviews.
- candidate sourcing, applications, interviews, and offers.
- ats list offers
- hris list companies
- list all candidates.
- talent management
- list all applications from the ats.
- time off management.
- create employee
- manages leads, opportunities, and crm activities.
- hris list employees
- list all applications.
- merge
- create candidate
- candidate pipeline management.
- manages employee records, time off, and hr processes.
- create a new candidate in the ats.
- hris create employee
- create a new employee.
- ats list candidates
- hris
- create a time off request.
- list companies from the hris.
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
