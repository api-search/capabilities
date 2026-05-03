---
categories:
- analytics
consumed_apis:
- cr-reporting
description: Unified workflow for managing Crystal Reports including authentication, repository browsing, report viewing, data access, and export. Used by report developers, BI analysts, and application developers.
layout: capability
name: Crystal Reports Report Management
operations:
- description: ''
  method: POST
  name: logon
  path: /v1/auth
- description: ''
  method: GET
  name: browse-repository
  path: /v1/reports
- description: ''
  method: GET
  name: get-report-summary
  path: /v1/reports/{id}
- description: ''
  method: GET
  name: export-report
  path: /v1/reports/{id}/export
- description: ''
  method: GET
  name: get-rows
  path: /v1/reports/{id}/rows
personas: []
provider_name: Crystal Reports
provider_slug: crystal-reports
search_terms:
- authenticate to crystal reports server
- browse the bi platform report repository
- get report summary including name, author, and uris
- report management
- crystal reports
- create instance
- export report to pdf, excel, csv, word, xml, or other format
- list folder children
- get report structure
- logon
- post row
- business intelligence
- list contents of a repository folder
- export
- browse repository
- enterprise software
- export report
- data analytics
- get report grand totals and summaries
- sap
- reporting
- get rows
- get odata metadata
- create a transient report instance
- get edmx metadata describing the report data model
- get report data rows via odata with pagination and filtering
- get report metadata with datasources, fields, parameters, and formulas
- push data to a transient report instance
- get report summary
- get grand totals
slug: report-management
source_filename: report-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Crystal Reports Report Management\"\n  description: \"Unified workflow for managing Crystal Reports including authentication, repository browsing, report viewing, data access, and export. Used by report developers, BI analysts, and application developers.\"\n  tags:\n    - Crystal Reports\n    - Report Management\n    - Business Intelligence\n    - Export\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      CR_USERNAME: CR_USERNAME\n      CR_PASSWORD: CR_PASSWORD\n\ncapability:\n  consumes:\n    - import: cr-reporting\n      location: ./shared/reporting.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: cr-management-api\n      description: \"Unified REST API for Crystal Reports management.\"\n      resources:\n        - path: /v1/auth\n          name: authentication\n          operations:\n            - method: POST\n              name: logon\n           \
  \   call: \"cr-reporting.logon\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reports\n          name: reports\n          operations:\n            - method: GET\n              name: browse-repository\n              call: \"cr-reporting.browse-repository\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reports/{id}\n          name: report\n          operations:\n            - method: GET\n              name: get-report-summary\n              call: \"cr-reporting.get-report-summary\"\n              with:\n                reportId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reports/{id}/export\n          name: export\n          operations:\n            - method: GET\n              name: export-report\n              call: \"cr-reporting.export-report\"\n\
  \              with:\n                reportId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reports/{id}/rows\n          name: rows\n          operations:\n            - method: GET\n              name: get-rows\n              call: \"cr-reporting.get-rows\"\n              with:\n                reportId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: cr-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Crystal Reports management.\"\n      tools:\n        - name: logon\n          description: \"Authenticate to Crystal Reports server\"\n          hints: {readOnly: false}\n          call: \"cr-reporting.logon\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: browse-repository\n          description:\
  \ \"Browse the BI platform report repository\"\n          hints: {readOnly: true, idempotent: true}\n          call: \"cr-reporting.browse-repository\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-folder-children\n          description: \"List contents of a repository folder\"\n          hints: {readOnly: true, idempotent: true}\n          call: \"cr-reporting.list-folder-children\"\n          with:\n            folderId: \"tools.folderId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-report-summary\n          description: \"Get report summary including name, author, and URIs\"\n          hints: {readOnly: true, idempotent: true}\n          call: \"cr-reporting.get-report-summary\"\n          with:\n            reportId: \"tools.reportId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-report-structure\n\
  \          description: \"Get report metadata with datasources, fields, parameters, and formulas\"\n          hints: {readOnly: true, idempotent: true}\n          call: \"cr-reporting.get-report-structure\"\n          with:\n            reportId: \"tools.reportId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-instance\n          description: \"Create a transient report instance\"\n          hints: {readOnly: false}\n          call: \"cr-reporting.create-instance\"\n          with:\n            reportId: \"tools.reportId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: export-report\n          description: \"Export report to PDF, Excel, CSV, Word, XML, or other format\"\n          hints: {readOnly: true, idempotent: true}\n          call: \"cr-reporting.export-report\"\n          with:\n            reportId: \"tools.reportId\"\n            mime_type: \"tools.mime_type\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-rows\n          description: \"Get report data rows via OData with pagination and filtering\"\n          hints: {readOnly: true, idempotent: true}\n          call: \"cr-reporting.get-rows\"\n          with:\n            reportId: \"tools.reportId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: post-row\n          description: \"Push data to a transient report instance\"\n          hints: {readOnly: false}\n          call: \"cr-reporting.post-row\"\n          with:\n            reportId: \"tools.reportId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-grand-totals\n          description: \"Get report grand totals and summaries\"\n          hints: {readOnly: true, idempotent: true}\n          call: \"cr-reporting.get-grand-totals\"\n          with:\n         \
  \   reportId: \"tools.reportId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-odata-metadata\n          description: \"Get EDMX metadata describing the report data model\"\n          hints: {readOnly: true, idempotent: true}\n          call: \"cr-reporting.get-odata-metadata\"\n          with:\n            reportId: \"tools.reportId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/crystal-reports/refs/heads/main/capabilities/report-management.yaml
tags:
- Crystal Reports
- Report Management
- Business Intelligence
- Export
tools:
- description: Authenticate to Crystal Reports server
  hints:
    readOnly: false
  name: logon
- description: Browse the BI platform report repository
  hints:
    idempotent: true
    readOnly: true
  name: browse-repository
- description: List contents of a repository folder
  hints:
    idempotent: true
    readOnly: true
  name: list-folder-children
- description: Get report summary including name, author, and URIs
  hints:
    idempotent: true
    readOnly: true
  name: get-report-summary
- description: Get report metadata with datasources, fields, parameters, and formulas
  hints:
    idempotent: true
    readOnly: true
  name: get-report-structure
- description: Create a transient report instance
  hints:
    readOnly: false
  name: create-instance
- description: Export report to PDF, Excel, CSV, Word, XML, or other format
  hints:
    idempotent: true
    readOnly: true
  name: export-report
- description: Get report data rows via OData with pagination and filtering
  hints:
    idempotent: true
    readOnly: true
  name: get-rows
- description: Push data to a transient report instance
  hints:
    readOnly: false
  name: post-row
- description: Get report grand totals and summaries
  hints:
    idempotent: true
    readOnly: true
  name: get-grand-totals
- description: Get EDMX metadata describing the report data model
  hints:
    idempotent: true
    readOnly: true
  name: get-odata-metadata
---
