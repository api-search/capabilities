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
- list departments
- unified workflow for managing employee absences, leave balances, and org structure
- list allowances
- organizational structure including departments, locations, and employees
- absence management
- employee leave allowances.
- delete an absence.
- list all employees in the organization with their department and location assignments.
- list locations.
- delete absence
- list users
- hr
- Payroll Processor
- employee records.
- Integration Developer
- list departments.
- list all absence reason types (vacation, sick leave, parental leave, etc.).
- update an absence.
- list absences
- HR Manager
- get employee
- get an employee by id.
- office locations.
- list reason types
- create absence
- get an absence by id.
- a specific employee record.
- payroll teams using absence data to calculate leave deductions and entitlements
- list absence reason types.
- absence reason types.
- list leave allowances
- list all office locations.
- employee absence records.
- employees
- payroll
- get user
- create a new absence record.
- get detailed information about a specific employee.
- list all organizational departments.
- list employees
- leave management
- list employee leave allowances.
- list locations
- hr professionals managing employee leave requests and approvals
- list employee leave allowances and remaining balances for the year.
- employee absence tracking, approval workflows, and leave balance management
- developers building integrations between absence.io and erp/hris systems
- update absence
- organizational departments.
- list all employees.
- list employee absences. supports date range filtering and pagination.
- list absence types
- get details of a specific absence record by its id.
- a specific absence record.
- update an existing absence record (change dates, reason, etc.).
- delete an absence record permanently.
- create a new absence record for an employee.
- get absence
- absences
- list all employee absences.
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
