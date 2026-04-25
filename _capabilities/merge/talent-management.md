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
- ats list applications
- hris create employee
- create a time off request.
- integrations
- create employee
- list applications
- list employees from the connected hris.
- list candidates from the connected ats.
- candidate sourcing, applications, interviews, and offers.
- list companies from the hris.
- list all candidates.
- hris
- ats
- ats list offers
- create a new employee.
- manages leads, opportunities, and crm activities.
- employee management, benefits, time off, and payroll.
- create an employee in the hris.
- list all job postings.
- file storage, sharing, and permissions.
- list all open job postings.
- candidate pipeline management.
- list jobs
- create a new candidate.
- merge
- platform
- manages invoices, payments, and financial reporting.
- list all employees.
- invoicing, payments, expenses, and financial reporting.
- list all applications from the ats.
- hris list time off
- employee records.
- talent management
- create a new candidate in the ats.
- list time off
- manages tickets and customer support issues.
- list employees
- ticket management and customer communication.
- HR Manager
- list time off requests.
- unified api
- job postings.
- manages employee records, time off, and hr processes.
- hris list companies
- application tracking.
- hris list employees
- Recruiter
- ats list candidates
- hris create time off
- end-to-end talent management combining hris and ats.
- create candidate
- manages candidate pipeline and hiring workflow.
- ats create candidate
- crm, leads, opportunities, and engagements.
- list scheduled interviews.
- ats list interviews
- list all offers.
- ats list jobs
- recruiting
- time off management.
- list all applications.
- list candidates
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
