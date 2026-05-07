---
categories: []
consumed_apis: []
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
- prime contracts.
- list contracts.
- list employee timesheets from a connected construction system.
- budget line items.
- agave
- list employee records from a connected construction system.
- accounting
- budget, cost code, and cost tracking for construction jobs.
- list employees.
- invoices
- list project budget line items from a connected construction system.
- list accounts payable invoices from a connected construction system.
- employee records.
- construction
- invoice processing and vendor payment management.
- construction project data.
- integration
- job costing
- list budget items.
- list vendors.
- construction project tracking and management.
- contractor admin
- employee and timesheet management.
- create an invoice.
- list projects
- create invoice
- list contracts
- full construction data synchronization covering projects, budgets, contracts, invoices, timesheets, and employees.
- vendor records.
- employee timesheets.
- list employees
- list vendors and subcontractors from a connected construction system.
- list vendors
- list budgets
- list invoices.
- construction company admin using connected tools to sync financial and project data between systems.
- ap invoices.
- list construction projects from any connected source system via agave.
- list prime contracts from a connected construction system.
- construction software engineer
- list invoices
- list timesheets.
- list construction projects.
- list timesheets
- create an ap invoice in a connected construction source system.
- developer integrating a construction software platform with other systems via agave's unified api.
slug: construction-data-sync
source_filename: construction-data-sync.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Agave Construction Data Sync\n  description: Unified workflow capability for syncing construction project data across connected source systems via the Agave\n    unified API. Enables project management, job costing, AP automation, and timesheet sync for construction software integrations.\n  tags:\n  - Agave\n  - Construction\n  - Integration\n  - Job Costing\n  - Invoices\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AGAVE_API_KEY: AGAVE_API_KEY\n    AGAVE_SOURCE_SYSTEM_ID: AGAVE_SOURCE_SYSTEM_ID\ncapability:\n  consumes:\n  - type: http\n    namespace: agave-unified\n    baseUri: https://api.agaveapi.com/v1\n    description: Agave Unified Construction API.\n    authentication:\n      type: apikey\n      key: API-Key\n      value: '{{AGAVE_API_KEY}}'\n      placement: header\n    resources:\n    - name: projects\n      path: /projects\n      description: Construction project data.\n      operations:\n\
  \      - name: list-projects\n        method: GET\n        description: List construction projects.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: budgets\n      path: /budgets\n      description: Project budget line items.\n      operations:\n      - name: list-budgets\n        method: GET\n        description: List budget line items.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contracts\n      path: /contracts\n      description: Prime contracts.\n      operations:\n      - name: list-contracts\n        method: GET\n        description: List prime contracts.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vendors\n      path: /vendors\n      description: Vendor records.\n      operations:\n      - name: list-vendors\n\
  \        method: GET\n        description: List vendors.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invoices\n      path: /invoices\n      description: AP invoice management.\n      operations:\n      - name: list-invoices\n        method: GET\n        description: List invoices.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-invoice\n        method: POST\n        description: Create a new invoice.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: timesheets\n      path: /timesheets\n      description: Employee timesheets.\n      operations:\n      - name: list-timesheets\n        method: GET\n        description: List timesheets.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: employees\n      path: /employees\n      description: Employee records.\n      operations:\n      - name: list-employees\n        method: GET\n        description: List employees.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: agave-sync-api\n    description: Unified REST API for Agave construction data synchronization.\n    resources:\n    - path: /v1/projects\n      name: projects\n      description: Construction project data.\n      operations:\n      - method: GET\n        name: list-projects\n        description: List construction projects.\n        call: agave-unified.list-projects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/budgets\n      name: budgets\n      description: Budget line items.\n      operations:\n      - method: GET\n\
  \        name: list-budgets\n        description: List budget items.\n        call: agave-unified.list-budgets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/contracts\n      name: contracts\n      description: Prime contracts.\n      operations:\n      - method: GET\n        name: list-contracts\n        description: List contracts.\n        call: agave-unified.list-contracts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vendors\n      name: vendors\n      description: Vendor records.\n      operations:\n      - method: GET\n        name: list-vendors\n        description: List vendors.\n        call: agave-unified.list-vendors\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices\n      name: invoices\n      description: AP invoices.\n      operations:\n      - method: GET\n        name: list-invoices\n        description: List invoices.\n        call:\
  \ agave-unified.list-invoices\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-invoice\n        description: Create an invoice.\n        call: agave-unified.create-invoice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/timesheets\n      name: timesheets\n      description: Employee timesheets.\n      operations:\n      - method: GET\n        name: list-timesheets\n        description: List timesheets.\n        call: agave-unified.list-timesheets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/employees\n      name: employees\n      description: Employee records.\n      operations:\n      - method: GET\n        name: list-employees\n        description: List employees.\n        call: agave-unified.list-employees\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: agave-sync-mcp\n\
  \    transport: http\n    description: MCP server for AI-assisted construction data synchronization via Agave.\n    tools:\n    - name: list-projects\n      description: List construction projects from any connected source system via Agave.\n      hints:\n        readOnly: true\n        destructive: false\n      call: agave-unified.list-projects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-budgets\n      description: List project budget line items from a connected construction system.\n      hints:\n        readOnly: true\n        destructive: false\n      call: agave-unified.list-budgets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-contracts\n      description: List prime contracts from a connected construction system.\n      hints:\n        readOnly: true\n        destructive: false\n      call: agave-unified.list-contracts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ list-vendors\n      description: List vendors and subcontractors from a connected construction system.\n      hints:\n        readOnly: true\n        destructive: false\n      call: agave-unified.list-vendors\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-invoices\n      description: List accounts payable invoices from a connected construction system.\n      hints:\n        readOnly: true\n        destructive: false\n      call: agave-unified.list-invoices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-invoice\n      description: Create an AP invoice in a connected construction source system.\n      hints:\n        readOnly: false\n        destructive: false\n      call: agave-unified.create-invoice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-timesheets\n      description: List employee timesheets from a connected construction system.\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n      call: agave-unified.list-timesheets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-employees\n      description: List employee records from a connected construction system.\n      hints:\n        readOnly: true\n        destructive: false\n      call: agave-unified.list-employees\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/agave/refs/heads/main/capabilities/construction-data-sync.yaml
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
