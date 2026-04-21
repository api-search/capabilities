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
- candidate pipeline management.
- unified api
- ats list offers
- candidate sourcing, applications, interviews, and offers.
- list scheduled interviews.
- create a new employee.
- manages leads, opportunities, and crm activities.
- hris
- list companies from the hris.
- list jobs
- employee records.
- time off management.
- list candidates
- ats list jobs
- end-to-end talent management combining hris and ats.
- HR Manager
- create a new candidate.
- ats list candidates
- invoicing, payments, expenses, and financial reporting.
- manages employee records, time off, and hr processes.
- list all applications from the ats.
- hris create time off
- employee management, benefits, time off, and payroll.
- talent management
- ats list applications
- list all open job postings.
- hris list time off
- ats create candidate
- application tracking.
- list time off requests.
- merge
- ats
- manages candidate pipeline and hiring workflow.
- hris create employee
- recruiting
- list all offers.
- list employees
- job postings.
- hris list employees
- list all applications.
- hris list companies
- manages tickets and customer support issues.
- integrations
- platform
- Recruiter
- list all job postings.
- ats list interviews
- create a time off request.
- crm, leads, opportunities, and engagements.
- manages invoices, payments, and financial reporting.
- list all employees.
- file storage, sharing, and permissions.
- list time off
- list all candidates.
- list employees from the connected hris.
- create a new candidate in the ats.
- create an employee in the hris.
- list candidates from the connected ats.
- create employee
- ticket management and customer communication.
- create candidate
- list applications
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
