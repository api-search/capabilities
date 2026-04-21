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
- data management
- list worksheets
- add a row to a table.
- analysts working with excel workbooks for data processing.
- microsoft 365
- add table row
- list all charts in a worksheet.
- read cell values from a specified range.
- Business Analyst
- get a cell range.
- list table rows
- spreadsheet automation
- cell range operations.
- business users automating excel-based reporting.
- manage table rows.
- list all rows in an excel table.
- office
- spreadsheets
- list all worksheets in the workbook.
- list rows in a table.
- update cell values in a specified range.
- manage worksheets.
- microsoft excel
- list charts.
- create a new worksheet.
- list all worksheets.
- automate excel workbook operations.
- data analysis
- create worksheet
- create a new worksheet in the workbook.
- automation
- list charts
- microsoft
- update range
- Data Analyst
- chart operations.
- get range
- add a new data row to an excel table.
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
