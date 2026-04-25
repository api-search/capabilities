---
consumed_apis:
- agave-unified
description: Unified workflow capability for syncing construction project data across connected source systems via the Agave unified API. Enables project management, job costing, AP automation, and timesheet sync for construction software integrations.
layout: capability
name: Agave Construction Data Sync
operations:
- description: List construction projects.
  method: GET
  name: list-projects
  path: /v1/projects
- description: List budget items.
  method: GET
  name: list-budgets
  path: /v1/budgets
- description: List contracts.
  method: GET
  name: list-contracts
  path: /v1/contracts
- description: List vendors.
  method: GET
  name: list-vendors
  path: /v1/vendors
- description: List invoices.
  method: GET
  name: list-invoices
  path: /v1/invoices
- description: Create an invoice.
  method: POST
  name: create-invoice
  path: /v1/invoices
- description: List timesheets.
  method: GET
  name: list-timesheets
  path: /v1/timesheets
- description: List employees.
  method: GET
  name: list-employees
  path: /v1/employees
personas:
- description: Developer integrating a construction software platform with other systems via Agave's unified API.
  id: construction-software-engineer
  name: Construction Software Engineer
- description: Construction company admin using connected tools to sync financial and project data between systems.
  id: contractor-admin
  name: Contractor Administrator
provider_name: Agave
provider_slug: agave
search_terms:
- employee and timesheet management.
- prime contracts.
- list employee timesheets from a connected construction system.
- budget line items.
- list accounts payable invoices from a connected construction system.
- list invoices.
- full construction data synchronization covering projects, budgets, contracts, invoices, timesheets, and employees.
- agave
- employee timesheets.
- integration
- list construction projects from any connected source system via agave.
- create invoice
- budget, cost code, and cost tracking for construction jobs.
- invoices
- construction project tracking and management.
- job costing
- invoice processing and vendor payment management.
- contractor admin
- create an ap invoice in a connected construction source system.
- list employees
- construction project data.
- list construction projects.
- create an invoice.
- list project budget line items from a connected construction system.
- list budgets
- list invoices
- list prime contracts from a connected construction system.
- list employee records from a connected construction system.
- list timesheets.
- construction software engineer
- list budget items.
- list contracts.
- list contracts
- list vendors.
- list timesheets
- construction company admin using connected tools to sync financial and project data between systems.
- list projects
- construction
- list vendors
- employee records.
- ap invoices.
- vendor records.
- accounting
- developer integrating a construction software platform with other systems via agave's unified api.
- list employees.
- list vendors and subcontractors from a connected construction system.
slug: construction-data-sync
tags:
- Agave
- Construction
- Integration
- Job Costing
- Invoices
tools:
- description: List construction projects from any connected source system via Agave.
  hints:
    destructive: false
    readOnly: true
  name: list-projects
- description: List project budget line items from a connected construction system.
  hints:
    destructive: false
    readOnly: true
  name: list-budgets
- description: List prime contracts from a connected construction system.
  hints:
    destructive: false
    readOnly: true
  name: list-contracts
- description: List vendors and subcontractors from a connected construction system.
  hints:
    destructive: false
    readOnly: true
  name: list-vendors
- description: List accounts payable invoices from a connected construction system.
  hints:
    destructive: false
    readOnly: true
  name: list-invoices
- description: Create an AP invoice in a connected construction source system.
  hints:
    destructive: false
    readOnly: false
  name: create-invoice
- description: List employee timesheets from a connected construction system.
  hints:
    destructive: false
    readOnly: true
  name: list-timesheets
- description: List employee records from a connected construction system.
  hints:
    destructive: false
    readOnly: true
  name: list-employees
---
