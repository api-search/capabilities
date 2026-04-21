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
- time off management.
- create a time off request.
- talent management
- list all candidates.
- create a new candidate in the ats.
- list all employees.
- manages leads, opportunities, and crm activities.
- create a new employee.
- list all applications.
- ats list offers
- crm, leads, opportunities, and engagements.
- employee management, benefits, time off, and payroll.
- candidate pipeline management.
- HR Manager
- list time off
- ats list interviews
- hris list companies
- hris create time off
- file storage, sharing, and permissions.
- list all open job postings.
- ats
- list applications
- end-to-end talent management combining hris and ats.
- ats create candidate
- platform
- list candidates from the connected ats.
- list scheduled interviews.
- list time off requests.
- list companies from the hris.
- recruiting
- application tracking.
- list jobs
- merge
- ats list candidates
- list candidates
- employee records.
- list employees
- manages employee records, time off, and hr processes.
- ats list applications
- manages invoices, payments, and financial reporting.
- candidate sourcing, applications, interviews, and offers.
- list all applications from the ats.
- create candidate
- ats list jobs
- create a new candidate.
- create an employee in the hris.
- Recruiter
- manages candidate pipeline and hiring workflow.
- list all offers.
- job postings.
- list all job postings.
- hris list time off
- unified api
- create employee
- invoicing, payments, expenses, and financial reporting.
- integrations
- hris list employees
- manages tickets and customer support issues.
- hris
- hris create employee
- ticket management and customer communication.
- list employees from the connected hris.
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
