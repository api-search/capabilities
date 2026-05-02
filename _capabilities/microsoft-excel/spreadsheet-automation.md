---
categories: []
consumed_apis:
- excel-graph
description: Workflow capability for automating Excel spreadsheet operations including worksheet management, data manipulation, table operations, and chart generation via Microsoft Graph.
layout: capability
name: Microsoft Excel Spreadsheet Automation
operations:
- description: List all worksheets.
  method: GET
  name: list-worksheets
  path: /v1/worksheets
- description: Create a new worksheet.
  method: POST
  name: create-worksheet
  path: /v1/worksheets
- description: List rows in a table.
  method: GET
  name: list-table-rows
  path: /v1/tables/{table-id}/rows
- description: Add a row to a table.
  method: POST
  name: add-table-row
  path: /v1/tables/{table-id}/rows
- description: Get a cell range.
  method: GET
  name: get-range
  path: /v1/ranges
- description: List charts.
  method: GET
  name: list-charts
  path: /v1/charts
personas: []
provider_name: Microsoft Excel
provider_slug: microsoft-excel
search_terms:
- data management
- list all rows in an excel table.
- cell range operations.
- manage worksheets.
- add a new data row to an excel table.
- add table row
- business users automating excel-based reporting.
- get a cell range.
- read cell values from a specified range.
- list worksheets
- microsoft 365
- list all worksheets in the workbook.
- spreadsheet automation
- chart operations.
- microsoft
- microsoft excel
- get range
- update cell values in a specified range.
- create a new worksheet.
- list all charts in a worksheet.
- Data Analyst
- automate excel workbook operations.
- automation
- spreadsheets
- data analysis
- analysts working with excel workbooks for data processing.
- manage table rows.
- list table rows
- list all worksheets.
- office
- create worksheet
- list charts
- Business Analyst
- list rows in a table.
- add a row to a table.
- create a new worksheet in the workbook.
- list charts.
- update range
slug: spreadsheet-automation
source_filename: spreadsheet-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Microsoft Excel Spreadsheet Automation\"\n  description: \"Workflow capability for automating Excel spreadsheet operations including worksheet management, data manipulation, table operations, and chart generation via Microsoft Graph.\"\n  tags:\n    - Microsoft Excel\n    - Spreadsheet Automation\n    - Data Management\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      MICROSOFT_GRAPH_TOKEN: MICROSOFT_GRAPH_TOKEN\n\ncapability:\n  consumes:\n    - import: excel-graph\n      location: ./shared/excel-graph-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: spreadsheet-automation-api\n      description: \"Unified REST API for Excel spreadsheet automation.\"\n      resources:\n        - path: /v1/worksheets\n          name: worksheets\n          description: \"Manage worksheets.\"\n          operations:\n            - method: GET\n              name: list-worksheets\n\
  \              description: \"List all worksheets.\"\n              call: \"excel-graph.list-worksheets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-worksheet\n              description: \"Create a new worksheet.\"\n              call: \"excel-graph.create-worksheet\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tables/{table-id}/rows\n          name: table-rows\n          description: \"Manage table rows.\"\n          operations:\n            - method: GET\n              name: list-table-rows\n              description: \"List rows in a table.\"\n              call: \"excel-graph.list-table-rows\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: add-table-row\n              description: \"Add a row to\
  \ a table.\"\n              call: \"excel-graph.add-table-row\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/ranges\n          name: ranges\n          description: \"Cell range operations.\"\n          operations:\n            - method: GET\n              name: get-range\n              description: \"Get a cell range.\"\n              call: \"excel-graph.get-range\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/charts\n          name: charts\n          description: \"Chart operations.\"\n          operations:\n            - method: GET\n              name: list-charts\n              description: \"List charts.\"\n              call: \"excel-graph.list-charts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: spreadsheet-automation-mcp\n\
  \      transport: http\n      description: \"MCP server for AI-assisted spreadsheet automation.\"\n      tools:\n        - name: list-worksheets\n          description: \"List all worksheets in the workbook.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"excel-graph.list-worksheets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-worksheet\n          description: \"Create a new worksheet in the workbook.\"\n          hints:\n            readOnly: false\n          call: \"excel-graph.create-worksheet\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-table-rows\n          description: \"List all rows in an Excel table.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"excel-graph.list-table-rows\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: add-table-row\n          description: \"Add a new data row to an Excel table.\"\n          hints:\n            readOnly: false\n          call: \"excel-graph.add-table-row\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-range\n          description: \"Read cell values from a specified range.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"excel-graph.get-range\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-range\n          description: \"Update cell values in a specified range.\"\n          hints:\n            readOnly: false\n          call: \"excel-graph.update-range\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-charts\n          description: \"List all charts in a worksheet.\"\n          hints:\n            readOnly:\
  \ true\n            openWorld: true\n          call: \"excel-graph.list-charts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-excel/refs/heads/main/capabilities/spreadsheet-automation.yaml
tags:
- Microsoft Excel
- Spreadsheet Automation
- Data Management
tools:
- description: List all worksheets in the workbook.
  hints:
    openWorld: true
    readOnly: true
  name: list-worksheets
- description: Create a new worksheet in the workbook.
  hints:
    readOnly: false
  name: create-worksheet
- description: List all rows in an Excel table.
  hints:
    openWorld: true
    readOnly: true
  name: list-table-rows
- description: Add a new data row to an Excel table.
  hints:
    readOnly: false
  name: add-table-row
- description: Read cell values from a specified range.
  hints:
    openWorld: true
    readOnly: true
  name: get-range
- description: Update cell values in a specified range.
  hints:
    readOnly: false
  name: update-range
- description: List all charts in a worksheet.
  hints:
    openWorld: true
    readOnly: true
  name: list-charts
---
