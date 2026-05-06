---
categories: []
consumed_apis: []
description: Unified capability for the financial close process combining general ledger management, journal entries, account reconciliation, period management, and financial reporting. Supports the record-to-report workflow for finance teams.
layout: capability
name: Workday Financials Financial Close
operations:
- description: List ledger accounts
  method: GET
  name: list-ledger-accounts
  path: /v1/ledger-accounts
- description: List journal entries
  method: GET
  name: list-journal-entries
  path: /v1/journal-entries
- description: Create a journal entry
  method: POST
  name: create-journal-entry
  path: /v1/journal-entries
- description: List supplier invoices
  method: GET
  name: list-supplier-invoices
  path: /v1/supplier-invoices
- description: List cost centers
  method: GET
  name: list-cost-centers
  path: /v1/cost-centers
- description: List available reports
  method: GET
  name: list-reports
  path: /v1/reports
personas: []
provider_name: Workday Financials
provider_slug: workday-financials
search_terms:
- list journal entries
- record to report
- execute a custom workday financials report
- list journal entries in workday financials
- reporting
- list cost center organizations
- execute report
- accounting
- financials
- financial close
- execute a standard financial report and retrieve results
- list general ledger accounts in workday financials
- general ledger account management
- workday
- list reports
- execute custom report
- general ledger
- financial management
- create journal entry
- list cost centers
- list accounts payable supplier invoices
- list ledger accounts
- create a new journal entry in workday financials
- cloud erp
- list available reports
- cost center management
- supplier invoice management
- list supplier invoices
- list available financial reports
- journal entry management
- financial report management
- create a journal entry
- procurement
slug: financial-close
source_filename: financial-close.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Workday Financials Financial Close\n  description: Unified capability for the financial close process combining general ledger management, journal entries, account\n    reconciliation, period management, and financial reporting. Supports the record-to-report workflow for finance teams.\n  tags:\n  - Workday\n  - Financials\n  - Financial Close\n  - General Ledger\n  - Reporting\n  - Record To Report\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WORKDAY_FINANCIALS_ACCESS_TOKEN: WORKDAY_FINANCIALS_ACCESS_TOKEN\n    WORKDAY_TENANT: WORKDAY_TENANT\ncapability:\n  consumes:\n  - type: http\n    namespace: financials-core\n    baseUri: https://{tenant}.workday.com/api/financialManagement/v38.2\n    description: Workday Financials core financial management API\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_FINANCIALS_ACCESS_TOKEN}}'\n    resources:\n    - name: ledger-accounts\n\
  \      path: /ledgerAccounts\n      description: General ledger account management\n      operations:\n      - name: list-ledger-accounts\n        method: GET\n        description: List ledger accounts\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-ledger-account\n        method: GET\n        description: Get a ledger account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: Ledger account identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: journal-entries\n      path: /journalEntries\n      description: Journal entry management\n      operations:\n\
  \      - name: list-journal-entries\n        method: GET\n        description: List journal entries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-journal-entry\n        method: POST\n        description: Create a journal entry\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            period: '{{tools.period}}'\n            lines: '{{tools.lines}}'\n    - name: supplier-invoices\n      path: /supplierInvoices\n      description: Supplier invoice management\n      operations:\n      - name: list-supplier-invoices\n        method: GET\n        description: List supplier invoices\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-supplier-invoice\n        method:\
  \ GET\n        description: Get a supplier invoice\n        inputParameters:\n        - name: invoiceId\n          in: path\n          type: string\n          required: true\n          description: Invoice identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customer-invoices\n      path: /customerInvoices\n      description: Customer invoice management\n      operations:\n      - name: list-customer-invoices\n        method: GET\n        description: List customer invoices\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cost-centers\n      path: /costCenters\n      description: Cost center management\n      operations:\n      - name: list-cost-centers\n        method: GET\n        description: List cost centers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n    \
  \      type: object\n          value: $.\n    - name: companies\n      path: /companies\n      description: Company entity management\n      operations:\n      - name: list-companies\n        method: GET\n        description: List companies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: financials-reporting\n    baseUri: https://{tenant}.workday.com/api/reporting/v38.2\n    description: Workday Financials reporting and analytics API\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_FINANCIALS_ACCESS_TOKEN}}'\n    resources:\n    - name: reports\n      path: /reports\n      description: Standard report management\n      operations:\n      - name: list-reports\n        method: GET\n        description: List available reports\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ get-report\n        method: GET\n        description: Get a report definition\n        inputParameters:\n        - name: reportId\n          in: path\n          type: string\n          required: true\n          description: Report identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: execute-report\n        method: POST\n        description: Execute a report\n        inputParameters:\n        - name: reportId\n          in: path\n          type: string\n          required: true\n          description: Report identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            parameters: '{{tools.parameters}}'\n    - name: custom-reports\n      path: /customReports\n      description: Custom report execution\n      operations:\n      - name: list-custom-reports\n\
  \        method: GET\n        description: List custom reports\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: execute-custom-report\n        method: POST\n        description: Execute a custom report\n        inputParameters:\n        - name: reportId\n          in: path\n          type: string\n          required: true\n          description: Custom report identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            parameters: '{{tools.parameters}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: workday-financials-close-api\n    description: Unified REST API for Workday Financials financial close and reporting.\n    resources:\n    - path: /v1/ledger-accounts\n      name: ledger-accounts\n      description: General ledger account management\n\
  \      operations:\n      - method: GET\n        name: list-ledger-accounts\n        description: List ledger accounts\n        call: financials-core.list-ledger-accounts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/journal-entries\n      name: journal-entries\n      description: Journal entry management\n      operations:\n      - method: GET\n        name: list-journal-entries\n        description: List journal entries\n        call: financials-core.list-journal-entries\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-journal-entry\n        description: Create a journal entry\n        call: financials-core.create-journal-entry\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/supplier-invoices\n      name: supplier-invoices\n      description: Supplier invoice management\n      operations:\n      - method: GET\n        name: list-supplier-invoices\n\
  \        description: List supplier invoices\n        call: financials-core.list-supplier-invoices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cost-centers\n      name: cost-centers\n      description: Cost center management\n      operations:\n      - method: GET\n        name: list-cost-centers\n        description: List cost centers\n        call: financials-core.list-cost-centers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports\n      name: reports\n      description: Financial report management\n      operations:\n      - method: GET\n        name: list-reports\n        description: List available reports\n        call: financials-reporting.list-reports\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: workday-financials-close-mcp\n    transport: http\n    description: MCP server for AI-assisted Workday Financials financial\
  \ close process.\n    tools:\n    - name: list-ledger-accounts\n      description: List general ledger accounts in Workday Financials\n      hints:\n        readOnly: true\n        openWorld: true\n      call: financials-core.list-ledger-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-journal-entries\n      description: List journal entries in Workday Financials\n      hints:\n        readOnly: true\n        openWorld: true\n      call: financials-core.list-journal-entries\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-journal-entry\n      description: Create a new journal entry in Workday Financials\n      hints:\n        readOnly: false\n        destructive: false\n      call: financials-core.create-journal-entry\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-supplier-invoices\n      description: List accounts payable supplier invoices\n      hints:\n       \
  \ readOnly: true\n        openWorld: true\n      call: financials-core.list-supplier-invoices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-cost-centers\n      description: List cost center organizations\n      hints:\n        readOnly: true\n        openWorld: true\n      call: financials-core.list-cost-centers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-reports\n      description: List available financial reports\n      hints:\n        readOnly: true\n        openWorld: true\n      call: financials-reporting.list-reports\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: execute-report\n      description: Execute a standard financial report and retrieve results\n      hints:\n        readOnly: true\n        openWorld: false\n      call: financials-reporting.execute-report\n      with:\n        reportId: tools.reportId\n      outputParameters:\n      - type: object\n       \
  \ mapping: $.\n    - name: execute-custom-report\n      description: Execute a custom Workday Financials report\n      hints:\n        readOnly: true\n        openWorld: false\n      call: financials-reporting.execute-custom-report\n      with:\n        reportId: tools.reportId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/workday-financials/refs/heads/main/capabilities/financial-close.yaml
tags:
- Workday
- Financials
- Financial Close
- General Ledger
- Reporting
- Record To Report
tools:
- description: List general ledger accounts in Workday Financials
  hints:
    openWorld: true
    readOnly: true
  name: list-ledger-accounts
- description: List journal entries in Workday Financials
  hints:
    openWorld: true
    readOnly: true
  name: list-journal-entries
- description: Create a new journal entry in Workday Financials
  hints:
    destructive: false
    readOnly: false
  name: create-journal-entry
- description: List accounts payable supplier invoices
  hints:
    openWorld: true
    readOnly: true
  name: list-supplier-invoices
- description: List cost center organizations
  hints:
    openWorld: true
    readOnly: true
  name: list-cost-centers
- description: List available financial reports
  hints:
    openWorld: true
    readOnly: true
  name: list-reports
- description: Execute a standard financial report and retrieve results
  hints:
    openWorld: false
    readOnly: true
  name: execute-report
- description: Execute a custom Workday Financials report
  hints:
    openWorld: false
    readOnly: true
  name: execute-custom-report
---
