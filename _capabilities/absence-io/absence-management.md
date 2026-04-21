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
- get details of a specific absence record by its id.
- get an absence by id.
- office locations.
- list all employees.
- list reason types
- organizational structure including departments, locations, and employees
- hr
- list employee leave allowances and remaining balances for the year.
- list all organizational departments.
- list employee leave allowances.
- create a new absence record for an employee.
- list employee absences. supports date range filtering and pagination.
- delete an absence.
- delete absence
- HR Manager
- get an employee by id.
- list absence types
- employees
- list leave allowances
- a specific absence record.
- developers building integrations between absence.io and erp/hris systems
- update absence
- get absence
- list all employee absences.
- absences
- get user
- create absence
- list all employees in the organization with their department and location assignments.
- get detailed information about a specific employee.
- employee absence records.
- list departments.
- list locations
- list locations.
- hr professionals managing employee leave requests and approvals
- list departments
- list users
- list allowances
- payroll
- list absence reason types.
- absence management
- get employee
- employee records.
- Integration Developer
- unified workflow for managing employee absences, leave balances, and org structure
- list employees
- list all absence reason types (vacation, sick leave, parental leave, etc.).
- create a new absence record.
- payroll teams using absence data to calculate leave deductions and entitlements
- leave management
- Payroll Processor
- employee absence tracking, approval workflows, and leave balance management
- list absences
- a specific employee record.
- employee leave allowances.
- absence reason types.
- update an existing absence record (change dates, reason, etc.).
- list all office locations.
- update an absence.
- delete an absence record permanently.
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
