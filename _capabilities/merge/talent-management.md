---
categories:
- recruiting-ats
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
- create a new candidate.
- list candidates from the connected ats.
- ats list applications
- list all job postings.
- unified api
- create employee
- hris
- list scheduled interviews.
- ats create candidate
- ats list interviews
- hris list companies
- end-to-end talent management combining hris and ats.
- crm, leads, opportunities, and engagements.
- candidate pipeline management.
- hris list employees
- candidate sourcing, applications, interviews, and offers.
- hris create employee
- create a time off request.
- HR Manager
- list all candidates.
- hris list time off
- Recruiter
- list time off
- platform
- manages tickets and customer support issues.
- application tracking.
- file storage, sharing, and permissions.
- create candidate
- employee records.
- ats
- list time off requests.
- list all applications.
- manages employee records, time off, and hr processes.
- invoicing, payments, expenses, and financial reporting.
- hris create time off
- merge
- recruiting
- manages candidate pipeline and hiring workflow.
- integrations
- manages leads, opportunities, and crm activities.
- list all open job postings.
- employee management, benefits, time off, and payroll.
- time off management.
- ticket management and customer communication.
- manages invoices, payments, and financial reporting.
- talent management
- job postings.
- list employees
- list all offers.
- list applications
- ats list candidates
- list all applications from the ats.
- list candidates
- list jobs
- ats list jobs
- ats list offers
- list all employees.
- create an employee in the hris.
- list companies from the hris.
- list employees from the connected hris.
- create a new candidate in the ats.
- create a new employee.
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
