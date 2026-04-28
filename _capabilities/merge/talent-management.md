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
- recruiting
- create a new candidate in the ats.
- create a time off request.
- Recruiter
- candidate sourcing, applications, interviews, and offers.
- hris list companies
- list employees from the connected hris.
- list all candidates.
- ats list offers
- employee management, benefits, time off, and payroll.
- ticket management and customer communication.
- ats list applications
- list all offers.
- list all applications.
- hris list employees
- end-to-end talent management combining hris and ats.
- create a new employee.
- create an employee in the hris.
- ats create candidate
- manages employee records, time off, and hr processes.
- manages candidate pipeline and hiring workflow.
- crm, leads, opportunities, and engagements.
- hris create time off
- talent management
- list time off requests.
- list companies from the hris.
- ats
- list employees
- list all applications from the ats.
- hris create employee
- time off management.
- create a new candidate.
- application tracking.
- list jobs
- ats list jobs
- integrations
- list time off
- unified api
- manages tickets and customer support issues.
- list scheduled interviews.
- manages leads, opportunities, and crm activities.
- hris list time off
- job postings.
- ats list candidates
- create candidate
- file storage, sharing, and permissions.
- list all open job postings.
- list candidates
- invoicing, payments, expenses, and financial reporting.
- list candidates from the connected ats.
- list all job postings.
- ats list interviews
- list applications
- platform
- candidate pipeline management.
- hris
- employee records.
- list all employees.
- merge
- HR Manager
- manages invoices, payments, and financial reporting.
- create employee
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
