---
categories: []
consumed_apis: []
description: Workflow capability for spreadsheet data automation using Google Sheets API. Enables AI assistants and applications to read data from sheets, write and append new rows, batch update multiple ranges, clear data, and manage spreadsheet structure. Supports data pipeline, reporting, form collection, and content management workflows.
layout: capability
name: Spreadsheet Automation
operations:
- description: Get spreadsheet metadata including sheet names and structure
  method: GET
  name: get-spreadsheet
  path: /v1/spreadsheets/{spreadsheetId}
- description: Read values from a cell range
  method: GET
  name: get-values
  path: /v1/spreadsheets/{spreadsheetId}/values/{range}
- description: Write values to a cell range
  method: PUT
  name: update-values
  path: /v1/spreadsheets/{spreadsheetId}/values/{range}
- description: Append new rows to the end of a table
  method: POST
  name: append-values
  path: /v1/spreadsheets/{spreadsheetId}/values/{range}/append
- description: Read multiple ranges in one request
  method: GET
  name: batch-get-values
  path: /v1/spreadsheets/{spreadsheetId}/values/batch
- description: Write to multiple ranges in one request
  method: POST
  name: batch-update-values
  path: /v1/spreadsheets/{spreadsheetId}/values/batch
personas: []
provider_name: Spreadsheets
provider_slug: spreadsheets
search_terms:
- read multiple ranges in one request
- batch get values
- spreadsheets
- update values
- reporting
- write values to a cell range
- read cell values from a google sheets range using a1 notation (e.g., 'sheet1!a1:d10'). returns a 2d array of values.
- get information about a google spreadsheet including its title, sheets, and structure.
- append new rows to a google sheet. finds the last row of the existing table and inserts after it. perfect for adding new form submissions, log entries, or data records.
- write cell values to a google sheets range. use valueinputoption='user_entered' to parse values like a user would (including formulas), or 'raw' for literal string values.
- read multiple ranges from a google sheet in a single api call. more efficient than multiple individual reads.
- read spreadsheet range
- append new rows to the end of a table
- write to multiple ranges in one request
- automation
- productivity
- batch update values
- append rows to a spreadsheet
- get spreadsheet
- get spreadsheet info
- append to spreadsheet
- batch write spreadsheet
- write spreadsheet range
- read values from a cell range
- batch read spreadsheet
- get values
- spreadsheet metadata and structure
- get spreadsheet metadata including sheet names and structure
- google sheets
- data
- read and write cell values
- data automation
- write to multiple ranges in a google sheet in a single api call. efficient for updating several disjoint regions at once.
- append values
- batch read/write operations
- excel
slug: spreadsheet-automation
source_filename: spreadsheet-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Spreadsheet Automation\n  description: Workflow capability for spreadsheet data automation using Google Sheets API. Enables AI assistants and applications\n    to read data from sheets, write and append new rows, batch update multiple ranges, clear data, and manage spreadsheet\n    structure. Supports data pipeline, reporting, form collection, and content management workflows.\n  tags:\n  - Spreadsheets\n  - Google Sheets\n  - Data Automation\n  - Reporting\n  - Productivity\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_ACCESS_TOKEN: GOOGLE_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: google-sheets\n    baseUri: https://sheets.googleapis.com/v4\n    description: Google Sheets API v4 for reading and writing spreadsheet data\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_ACCESS_TOKEN}}'\n    resources:\n    - name: spreadsheet\n      path: /spreadsheets/{spreadsheetId}\n\
  \      description: Spreadsheet resource\n      operations:\n      - name: get-spreadsheet\n        method: GET\n        description: Get spreadsheet metadata and structure\n        inputParameters:\n        - name: spreadsheetId\n          in: path\n          type: string\n          required: true\n        - name: includeGridData\n          in: query\n          type: boolean\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: values\n      path: /spreadsheets/{spreadsheetId}/values/{range}\n      description: Cell values by range\n      operations:\n      - name: get-values\n        method: GET\n        description: Read cell values from a range\n        inputParameters:\n        - name: spreadsheetId\n          in: path\n          type: string\n          required: true\n        - name: range\n          in: path\n          type: string\n          required: true\n        -\
  \ name: majorDimension\n          in: query\n          type: string\n          required: false\n        - name: valueRenderOption\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: values\n          type: array\n          value: $.values\n        - name: range\n          type: string\n          value: $.range\n      - name: update-values\n        method: PUT\n        description: Write cell values to a range\n        inputParameters:\n        - name: spreadsheetId\n          in: path\n          type: string\n          required: true\n        - name: range\n          in: path\n          type: string\n          required: true\n        - name: valueInputOption\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n \
  \         data:\n            range: '{{tools.range}}'\n            values: '{{tools.values}}'\n    - name: values-append\n      path: /spreadsheets/{spreadsheetId}/values/{range}:append\n      description: Append values to a spreadsheet\n      operations:\n      - name: append-values\n        method: POST\n        description: Append rows to the end of an existing table\n        inputParameters:\n        - name: spreadsheetId\n          in: path\n          type: string\n          required: true\n        - name: range\n          in: path\n          type: string\n          required: true\n        - name: valueInputOption\n          in: query\n          type: string\n          required: true\n        - name: insertDataOption\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            values:\
  \ '{{tools.values}}'\n    - name: values-batch-get\n      path: /spreadsheets/{spreadsheetId}/values:batchGet\n      description: Batch read multiple ranges\n      operations:\n      - name: batch-get-values\n        method: GET\n        description: Read multiple ranges in a single API call\n        inputParameters:\n        - name: spreadsheetId\n          in: path\n          type: string\n          required: true\n        - name: ranges\n          in: query\n          type: array\n          required: true\n        - name: majorDimension\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: valueRanges\n          type: array\n          value: $.valueRanges\n    - name: values-batch-update\n      path: /spreadsheets/{spreadsheetId}/values:batchUpdate\n      description: Batch write multiple ranges\n      operations:\n      - name: batch-update-values\n        method: POST\n        description:\
  \ Write to multiple ranges in a single API call\n        inputParameters:\n        - name: spreadsheetId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            valueInputOption: '{{tools.valueInputOption}}'\n            data: '{{tools.data}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: spreadsheet-automation-api\n    description: Unified REST API for spreadsheet data automation workflows.\n    resources:\n    - path: /v1/spreadsheets/{spreadsheetId}\n      name: spreadsheet\n      description: Spreadsheet metadata and structure\n      operations:\n      - method: GET\n        name: get-spreadsheet\n        description: Get spreadsheet metadata including sheet names and structure\n        call: google-sheets.get-spreadsheet\n        with:\n          spreadsheetId: rest.spreadsheetId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/spreadsheets/{spreadsheetId}/values/{range}\n      name: values\n      description: Read and write cell values\n      operations:\n      - method: GET\n        name: get-values\n        description: Read values from a cell range\n        call: google-sheets.get-values\n        with:\n          spreadsheetId: rest.spreadsheetId\n          range: rest.range\n          majorDimension: rest.majorDimension\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-values\n        description: Write values to a cell range\n        call: google-sheets.update-values\n        with:\n          spreadsheetId: rest.spreadsheetId\n          range: rest.range\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/spreadsheets/{spreadsheetId}/values/{range}/append\n      name: values-append\n      description: Append rows\
  \ to a spreadsheet\n      operations:\n      - method: POST\n        name: append-values\n        description: Append new rows to the end of a table\n        call: google-sheets.append-values\n        with:\n          spreadsheetId: rest.spreadsheetId\n          range: rest.range\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/spreadsheets/{spreadsheetId}/values/batch\n      name: batch-values\n      description: Batch read/write operations\n      operations:\n      - method: GET\n        name: batch-get-values\n        description: Read multiple ranges in one request\n        call: google-sheets.batch-get-values\n        with:\n          spreadsheetId: rest.spreadsheetId\n          ranges: rest.ranges\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: batch-update-values\n        description: Write to multiple ranges in one request\n        call: google-sheets.batch-update-values\n \
  \       with:\n          spreadsheetId: rest.spreadsheetId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: spreadsheet-automation-mcp\n    transport: http\n    description: MCP server for AI-assisted spreadsheet reading, writing, and data management.\n    tools:\n    - name: get-spreadsheet-info\n      description: Get information about a Google Spreadsheet including its title, sheets, and structure.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: google-sheets.get-spreadsheet\n      with:\n        spreadsheetId: tools.spreadsheetId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: read-spreadsheet-range\n      description: Read cell values from a Google Sheets range using A1 notation (e.g., 'Sheet1!A1:D10'). Returns a 2D array\n        of values.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: google-sheets.get-values\n     \
  \ with:\n        spreadsheetId: tools.spreadsheetId\n        range: tools.range\n        majorDimension: tools.majorDimension\n        valueRenderOption: tools.valueRenderOption\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: write-spreadsheet-range\n      description: Write cell values to a Google Sheets range. Use valueInputOption='USER_ENTERED' to parse values like a\n        user would (including formulas), or 'RAW' for literal string values.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: google-sheets.update-values\n      with:\n        spreadsheetId: tools.spreadsheetId\n        range: tools.range\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: append-to-spreadsheet\n      description: Append new rows to a Google Sheet. Finds the last row of the existing table and inserts after it. Perfect\n        for adding new form submissions, log entries, or data records.\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-sheets.append-values\n      with:\n        spreadsheetId: tools.spreadsheetId\n        range: tools.range\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: batch-read-spreadsheet\n      description: Read multiple ranges from a Google Sheet in a single API call. More efficient than multiple individual\n        reads.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: google-sheets.batch-get-values\n      with:\n        spreadsheetId: tools.spreadsheetId\n        ranges: tools.ranges\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: batch-write-spreadsheet\n      description: Write to multiple ranges in a Google Sheet in a single API call. Efficient for updating several disjoint\n        regions at once.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ true\n      call: google-sheets.batch-update-values\n      with:\n        spreadsheetId: tools.spreadsheetId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/spreadsheets/refs/heads/main/capabilities/spreadsheet-automation.yaml
tags:
- Spreadsheets
- Google Sheets
- Data Automation
- Reporting
- Productivity
tools:
- description: Get information about a Google Spreadsheet including its title, sheets, and structure.
  hints:
    openWorld: false
    readOnly: true
  name: get-spreadsheet-info
- description: Read cell values from a Google Sheets range using A1 notation (e.g., 'Sheet1!A1:D10'). Returns a 2D array of values.
  hints:
    openWorld: false
    readOnly: true
  name: read-spreadsheet-range
- description: Write cell values to a Google Sheets range. Use valueInputOption='USER_ENTERED' to parse values like a user would (including formulas), or 'RAW' for literal string values.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: write-spreadsheet-range
- description: Append new rows to a Google Sheet. Finds the last row of the existing table and inserts after it. Perfect for adding new form submissions, log entries, or data records.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: append-to-spreadsheet
- description: Read multiple ranges from a Google Sheet in a single API call. More efficient than multiple individual reads.
  hints:
    openWorld: false
    readOnly: true
  name: batch-read-spreadsheet
- description: Write to multiple ranges in a Google Sheet in a single API call. Efficient for updating several disjoint regions at once.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: batch-write-spreadsheet
---
