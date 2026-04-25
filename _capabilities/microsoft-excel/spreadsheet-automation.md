---
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
- list worksheets
- analysts working with excel workbooks for data processing.
- automation
- manage worksheets.
- update range
- list table rows
- spreadsheets
- create a new worksheet.
- list charts
- add a row to a table.
- microsoft excel
- chart operations.
- list all charts in a worksheet.
- list charts.
- Business Analyst
- update cell values in a specified range.
- microsoft
- microsoft 365
- create a new worksheet in the workbook.
- get range
- add a new data row to an excel table.
- list rows in a table.
- office
- data management
- list all rows in an excel table.
- Data Analyst
- automate excel workbook operations.
- create worksheet
- cell range operations.
- business users automating excel-based reporting.
- list all worksheets in the workbook.
- get a cell range.
- manage table rows.
- spreadsheet automation
- add table row
- read cell values from a specified range.
- data analysis
- list all worksheets.
slug: spreadsheet-automation
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
