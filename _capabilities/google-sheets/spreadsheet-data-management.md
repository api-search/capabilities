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
- batch update values
- append rows of data to a spreadsheet
- get developer metadata
- batch update spreadsheet
- google sheets
- clear values from a range
- data management
- read values from a spreadsheet range
- single spreadsheet operations
- automation
- write values to multiple ranges at once
- get spreadsheet details
- write values to a spreadsheet range
- batch get values
- write values to a range
- copy sheet
- productivity
- clear values from a spreadsheet range
- clear values
- update values
- google workspace
- get spreadsheet
- read values from a range
- append values to a range
- cell value read and write operations
- create spreadsheet
- create a new google sheets spreadsheet
- read values from multiple ranges at once
- create a new spreadsheet
- spreadsheets
- append values
- get values
- batch clear values
- copy a sheet to another spreadsheet
- get developer metadata by id
- apply batch updates to a spreadsheet
- clear values from multiple ranges
- search developer metadata
- search developer metadata matching filters
- spreadsheet lifecycle operations
- get spreadsheet details by id
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
