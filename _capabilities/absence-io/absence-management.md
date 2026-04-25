---
consumed_apis:
- absence-io
description: Unified workflow for managing employee absences, tracking leave balances, and administering organizational structure in Absence.io. Designed for HR managers, payroll teams, and integration developers building absence management workflows.
layout: capability
name: Absence.io Absence Management
operations:
- description: List all employee absences.
  method: GET
  name: list-absences
  path: /v1/absences
- description: Create a new absence record.
  method: POST
  name: create-absence
  path: /v1/absences
- description: Get an absence by ID.
  method: GET
  name: get-absence
  path: /v1/absences/{id}
- description: Update an absence.
  method: PUT
  name: update-absence
  path: /v1/absences/{id}
- description: Delete an absence.
  method: DELETE
  name: delete-absence
  path: /v1/absences/{id}
- description: List all employees.
  method: GET
  name: list-users
  path: /v1/employees
- description: Get an employee by ID.
  method: GET
  name: get-user
  path: /v1/employees/{id}
- description: List employee leave allowances.
  method: GET
  name: list-allowances
  path: /v1/allowances
- description: List departments.
  method: GET
  name: list-departments
  path: /v1/departments
- description: List locations.
  method: GET
  name: list-locations
  path: /v1/locations
- description: List absence reason types.
  method: GET
  name: list-reason-types
  path: /v1/absence-types
personas: []
provider_name: Absence.io
provider_slug: absence-io
search_terms:
- organizational departments.
- list allowances
- update an absence.
- Integration Developer
- hr
- list departments
- list locations
- list all employees in the organization with their department and location assignments.
- organizational structure including departments, locations, and employees
- employee leave allowances.
- payroll teams using absence data to calculate leave deductions and entitlements
- create a new absence record.
- get an employee by id.
- delete an absence record permanently.
- hr professionals managing employee leave requests and approvals
- unified workflow for managing employee absences, leave balances, and org structure
- get an absence by id.
- a specific absence record.
- list all office locations.
- list absence types
- update an existing absence record (change dates, reason, etc.).
- delete absence
- list all organizational departments.
- developers building integrations between absence.io and erp/hris systems
- get user
- create absence
- office locations.
- payroll
- create a new absence record for an employee.
- list all employees.
- list absences
- leave management
- employee records.
- list leave allowances
- list all absence reason types (vacation, sick leave, parental leave, etc.).
- employee absence records.
- list users
- delete an absence.
- absence management
- list employees
- get detailed information about a specific employee.
- HR Manager
- list employee leave allowances.
- list employee absences. supports date range filtering and pagination.
- absences
- employee absence tracking, approval workflows, and leave balance management
- get absence
- list employee leave allowances and remaining balances for the year.
- Payroll Processor
- get employee
- a specific employee record.
- get details of a specific absence record by its id.
- employees
- list reason types
- update absence
- list departments.
- list all employee absences.
- list locations.
- list absence reason types.
- absence reason types.
slug: absence-management
tags:
- Absence Management
- HR
- Leave Management
- Payroll
tools:
- description: List employee absences. Supports date range filtering and pagination.
  hints:
    openWorld: false
    readOnly: true
  name: list-absences
- description: Get details of a specific absence record by its ID.
  hints:
    openWorld: false
    readOnly: true
  name: get-absence
- description: Create a new absence record for an employee.
  hints:
    openWorld: false
    readOnly: false
  name: create-absence
- description: Update an existing absence record (change dates, reason, etc.).
  hints:
    idempotent: true
    openWorld: false
    readOnly: false
  name: update-absence
- description: Delete an absence record permanently.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-absence
- description: List all employees in the organization with their department and location assignments.
  hints:
    openWorld: false
    readOnly: true
  name: list-employees
- description: Get detailed information about a specific employee.
  hints:
    openWorld: false
    readOnly: true
  name: get-employee
- description: List employee leave allowances and remaining balances for the year.
  hints:
    openWorld: false
    readOnly: true
  name: list-leave-allowances
- description: List all organizational departments.
  hints:
    openWorld: false
    readOnly: true
  name: list-departments
- description: List all office locations.
  hints:
    openWorld: false
    readOnly: true
  name: list-locations
- description: List all absence reason types (vacation, sick leave, parental leave, etc.).
  hints:
    openWorld: false
    readOnly: true
  name: list-absence-types
---
