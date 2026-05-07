---
categories:
- analytics
consumed_apis: []
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
- report management
- enterprise software
- post row
- list contents of a repository folder
- crystal reports
- get report data rows via odata with pagination and filtering
- authenticate to crystal reports server
- list folder children
- data analytics
- get edmx metadata describing the report data model
- get rows
- export report to pdf, excel, csv, word, xml, or other format
- get odata metadata
- sap
- business intelligence
- get report structure
- browse repository
- create a transient report instance
- get grand totals
- get report summary including name, author, and uris
- push data to a transient report instance
- get report summary
- get report grand totals and summaries
- create instance
- export
- reporting
- logon
- export report
- get report metadata with datasources, fields, parameters, and formulas
- browse the bi platform report repository
slug: report-management
source_filename: report-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Crystal Reports Report Management\n  description: Unified workflow for managing Crystal Reports including authentication, repository browsing, report viewing,\n    data access, and export. Used by report developers, BI analysts, and application developers.\n  tags:\n  - Crystal Reports\n  - Report Management\n  - Business Intelligence\n  - Export\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    CR_USERNAME: CR_USERNAME\n    CR_PASSWORD: CR_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: cr-reporting\n    baseUri: https://{server}:{port}/biprws\n    description: Crystal Reports RESTful Web Services API.\n    authentication:\n      type: apikey\n      key: X-SAP-LogonToken\n      value: '{{CR_LOGON_TOKEN}}'\n      placement: header\n    resources:\n    - name: authentication\n      path: /logon\n      description: Authentication and session management.\n      operations:\n    \
  \  - name: logon\n        method: POST\n        path: /logon/long\n        description: Authenticate with username and password.\n        body:\n          type: json\n          data:\n            userName: '{{tools.userName}}'\n            password: '{{tools.password}}'\n            auth: '{{tools.auth}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reports\n      path: /infostore\n      description: Repository navigation and report access.\n      operations:\n      - name: browse-repository\n        method: GET\n        path: /infostore\n        description: Browse the BI platform repository.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-folder-children\n        method: GET\n        path: /infostore/{folderId}/children\n        description: List contents of a folder.\n        inputParameters:\n\
  \        - name: folderId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-report-summary\n        method: GET\n        path: /infostore/{reportId}/rpt\n        description: Get report summary information.\n        inputParameters:\n        - name: reportId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-report-structure\n        method: GET\n        path: /infostore/{reportId}/rpt/structure\n        description: Get report metadata structure.\n        inputParameters:\n        - name: reportId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: create-instance\n        method: POST\n        path: /infostore/{reportId}/rpt/instance\n        description: Create a transient report instance.\n        inputParameters:\n        - name: reportId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: export-report\n        method: GET\n        path: /infostore/{reportId}/rpt/export\n        description: Export report to PDF, Excel, CSV, Word, or other format.\n        inputParameters:\n        - name: reportId\n          in: path\n          type: string\n          required: true\n        - name: mime_type\n          in: query\n          type: string\n          required: true\n          description: Export MIME type.\n        outputRawFormat: binary\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: odata\n      path: /infostore\n      description: OData data access for report rows and grand totals.\n      operations:\n      - name: get-odata-service\n        method: GET\n        path: /infostore/{reportId}/rpt/data.svc\n        description: Get OData service document.\n        inputParameters:\n        - name: reportId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-odata-metadata\n        method: GET\n        path: /infostore/{reportId}/rpt/data.svc/$metadata\n        description: Get EDMX metadata document.\n        inputParameters:\n        - name: reportId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-rows\n        method: GET\n\
  \        path: /infostore/{reportId}/rpt/data.svc/Rows\n        description: Get report data rows.\n        inputParameters:\n        - name: reportId\n          in: path\n          type: string\n          required: true\n        - name: $skip\n          in: query\n          type: integer\n          required: false\n        - name: $top\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-row\n        method: POST\n        path: /infostore/{reportId}/rpt/data.svc/Rows\n        description: Push a row of data to a transient instance.\n        inputParameters:\n        - name: reportId\n          in: path\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            fields: '{{tools.fields}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: get-grand-totals\n        method: GET\n        path: /infostore/{reportId}/rpt/data.svc/GrandTotals\n        description: Get report grand totals.\n        inputParameters:\n        - name: reportId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: cr-management-api\n    description: Unified REST API for Crystal Reports management.\n    resources:\n    - path: /v1/auth\n      name: authentication\n      operations:\n      - method: POST\n        name: logon\n        call: cr-reporting.logon\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports\n      name: reports\n      operations:\n      - method: GET\n        name: browse-repository\n        call: cr-reporting.browse-repository\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports/{id}\n      name: report\n      operations:\n      - method: GET\n        name: get-report-summary\n        call: cr-reporting.get-report-summary\n        with:\n          reportId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports/{id}/export\n      name: export\n      operations:\n      - method: GET\n        name: export-report\n        call: cr-reporting.export-report\n        with:\n          reportId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports/{id}/rows\n      name: rows\n      operations:\n      - method: GET\n        name: get-rows\n        call: cr-reporting.get-rows\n        with:\n          reportId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: cr-management-mcp\n    transport:\
  \ http\n    description: MCP server for AI-assisted Crystal Reports management.\n    tools:\n    - name: logon\n      description: Authenticate to Crystal Reports server\n      hints:\n        readOnly: false\n      call: cr-reporting.logon\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: browse-repository\n      description: Browse the BI platform report repository\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cr-reporting.browse-repository\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-folder-children\n      description: List contents of a repository folder\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cr-reporting.list-folder-children\n      with:\n        folderId: tools.folderId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-report-summary\n      description: Get report summary including name, author, and URIs\n\
  \      hints:\n        readOnly: true\n        idempotent: true\n      call: cr-reporting.get-report-summary\n      with:\n        reportId: tools.reportId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-report-structure\n      description: Get report metadata with datasources, fields, parameters, and formulas\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cr-reporting.get-report-structure\n      with:\n        reportId: tools.reportId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-instance\n      description: Create a transient report instance\n      hints:\n        readOnly: false\n      call: cr-reporting.create-instance\n      with:\n        reportId: tools.reportId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: export-report\n      description: Export report to PDF, Excel, CSV, Word, XML, or other format\n      hints:\n        readOnly: true\n\
  \        idempotent: true\n      call: cr-reporting.export-report\n      with:\n        reportId: tools.reportId\n        mime_type: tools.mime_type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-rows\n      description: Get report data rows via OData with pagination and filtering\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cr-reporting.get-rows\n      with:\n        reportId: tools.reportId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-row\n      description: Push data to a transient report instance\n      hints:\n        readOnly: false\n      call: cr-reporting.post-row\n      with:\n        reportId: tools.reportId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-grand-totals\n      description: Get report grand totals and summaries\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cr-reporting.get-grand-totals\n\
  \      with:\n        reportId: tools.reportId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-odata-metadata\n      description: Get EDMX metadata describing the report data model\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cr-reporting.get-odata-metadata\n      with:\n        reportId: tools.reportId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
