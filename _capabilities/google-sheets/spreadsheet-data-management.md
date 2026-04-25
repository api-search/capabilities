---
consumed_apis:
- google-sheets
description: Workflow for managing spreadsheet data including creating spreadsheets, reading and writing cell values, batch operations, and metadata management. Used by data analysts, developers, and automation engineers.
layout: capability
name: Google Sheets Spreadsheet Data Management
operations:
- description: Create a new spreadsheet
  method: POST
  name: create-spreadsheet
  path: /v1/spreadsheets
- description: Get spreadsheet details
  method: GET
  name: get-spreadsheet
  path: /v1/spreadsheets/{spreadsheetId}
- description: Read values from a range
  method: GET
  name: get-values
  path: /v1/spreadsheets/{spreadsheetId}/values/{range}
- description: Write values to a range
  method: PUT
  name: update-values
  path: /v1/spreadsheets/{spreadsheetId}/values/{range}
- description: Append values to a range
  method: POST
  name: append-values
  path: /v1/spreadsheets/{spreadsheetId}/values/{range}
- description: Clear values from a range
  method: DELETE
  name: clear-values
  path: /v1/spreadsheets/{spreadsheetId}/values/{range}
personas: []
provider_name: Google Sheets
provider_slug: google-sheets
search_terms:
- batch update spreadsheet
- search developer metadata matching filters
- apply batch updates to a spreadsheet
- append rows of data to a spreadsheet
- spreadsheets
- batch update values
- single spreadsheet operations
- read values from a spreadsheet range
- batch clear values
- clear values from a range
- clear values from a spreadsheet range
- write values to a range
- automation
- copy sheet
- productivity
- get spreadsheet
- create spreadsheet
- google sheets
- get spreadsheet details
- read values from a range
- get values
- data management
- write values to multiple ranges at once
- search developer metadata
- google workspace
- clear values
- get spreadsheet details by id
- clear values from multiple ranges
- read values from multiple ranges at once
- batch get values
- get developer metadata
- spreadsheet lifecycle operations
- create a new spreadsheet
- cell value read and write operations
- append values to a range
- copy a sheet to another spreadsheet
- get developer metadata by id
- update values
- write values to a spreadsheet range
- create a new google sheets spreadsheet
- append values
slug: spreadsheet-data-management
tags:
- Google Sheets
- Spreadsheets
- Data Management
- Automation
tools:
- description: Create a new Google Sheets spreadsheet
  hints:
    idempotent: false
    readOnly: false
  name: create-spreadsheet
- description: Get spreadsheet details by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-spreadsheet
- description: Apply batch updates to a spreadsheet
  hints:
    idempotent: false
    readOnly: false
  name: batch-update-spreadsheet
- description: Read values from a spreadsheet range
  hints:
    idempotent: true
    readOnly: true
  name: get-values
- description: Write values to a spreadsheet range
  hints:
    idempotent: true
    readOnly: false
  name: update-values
- description: Append rows of data to a spreadsheet
  hints:
    idempotent: false
    readOnly: false
  name: append-values
- description: Clear values from a spreadsheet range
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: clear-values
- description: Read values from multiple ranges at once
  hints:
    idempotent: true
    readOnly: true
  name: batch-get-values
- description: Write values to multiple ranges at once
  hints:
    idempotent: true
    readOnly: false
  name: batch-update-values
- description: Clear values from multiple ranges
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: batch-clear-values
- description: Copy a sheet to another spreadsheet
  hints:
    idempotent: false
    readOnly: false
  name: copy-sheet
- description: Get developer metadata by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-developer-metadata
- description: Search developer metadata matching filters
  hints:
    idempotent: true
    readOnly: true
  name: search-developer-metadata
---
