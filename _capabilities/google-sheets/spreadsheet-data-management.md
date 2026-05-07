---
categories:
- automation
consumed_apis: []
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
- clear values from multiple ranges
- automation
- read values from multiple ranges at once
- search developer metadata
- clear values from a range
- search developer metadata matching filters
- spreadsheets
- get values
- apply batch updates to a spreadsheet
- batch update spreadsheet
- append rows of data to a spreadsheet
- cell value read and write operations
- copy sheet
- create a new google sheets spreadsheet
- create spreadsheet
- clear values
- spreadsheet lifecycle operations
- data management
- productivity
- read values from a spreadsheet range
- single spreadsheet operations
- batch get values
- append values
- read values from a range
- append values to a range
- create a new spreadsheet
- get spreadsheet
- write values to multiple ranges at once
- google sheets
- batch clear values
- update values
- get developer metadata by id
- write values to a spreadsheet range
- clear values from a spreadsheet range
- write values to a range
- google workspace
- batch update values
- get spreadsheet details by id
- copy a sheet to another spreadsheet
- get spreadsheet details
- get developer metadata
slug: spreadsheet-data-management
source_filename: spreadsheet-data-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Sheets Spreadsheet Data Management\n  description: Workflow for managing spreadsheet data including creating spreadsheets, reading and writing cell values, batch\n    operations, and metadata management. Used by data analysts, developers, and automation engineers.\n  tags:\n  - Google Sheets\n  - Spreadsheets\n  - Data Management\n  - Automation\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_OAUTH_TOKEN: GOOGLE_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: google-sheets\n    baseUri: https://sheets.googleapis.com/v4\n    description: Google Sheets API v4 for reading, writing, and formatting spreadsheet data.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_OAUTH_TOKEN}}'\n    resources:\n    - name: spreadsheets\n      path: /spreadsheets\n      description: Spreadsheet lifecycle and batch operations.\n      operations:\n      - name: create-spreadsheet\n\
  \        method: POST\n        description: Creates a new spreadsheet.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            properties:\n              title: '{{tools.title}}'\n      - name: get-spreadsheet\n        method: GET\n        description: Returns the spreadsheet at the given ID.\n        inputParameters:\n        - name: spreadsheetId\n          in: path\n          type: string\n          required: true\n          description: The spreadsheet to request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: batch-update-spreadsheet\n        method: POST\n        description: Applies one or more updates to the spreadsheet.\n        inputParameters:\n        - name: spreadsheetId\n          in: path\n          type: string\n\
  \          required: true\n          description: The spreadsheet to apply the updates to.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            requests: '{{tools.requests}}'\n    - name: values\n      path: /spreadsheets/{spreadsheetId}/values\n      description: Read and write cell values.\n      operations:\n      - name: get-values\n        method: GET\n        description: Returns a range of values from a spreadsheet.\n        inputParameters:\n        - name: spreadsheetId\n          in: path\n          type: string\n          required: true\n          description: The ID of the spreadsheet to retrieve data from.\n        - name: range\n          in: path\n          type: string\n          required: true\n          description: The A1 notation of the values to retrieve.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: update-values\n        method: PUT\n        description: Sets values in a range of a spreadsheet.\n        inputParameters:\n        - name: spreadsheetId\n          in: path\n          type: string\n          required: true\n          description: The ID of the spreadsheet to update.\n        - name: range\n          in: path\n          type: string\n          required: true\n          description: The A1 notation of the values to update.\n        - name: valueInputOption\n          in: query\n          type: string\n          required: true\n          description: How the input data should be interpreted.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            values: '{{tools.values}}'\n      - name: append-values\n        method: POST\n        description: Appends values to a spreadsheet.\n\
  \        inputParameters:\n        - name: spreadsheetId\n          in: path\n          type: string\n          required: true\n          description: The ID of the spreadsheet to update.\n        - name: range\n          in: path\n          type: string\n          required: true\n          description: The A1 notation of a range to search for a logical table of data.\n        - name: valueInputOption\n          in: query\n          type: string\n          required: true\n          description: How the input data should be interpreted.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            values: '{{tools.values}}'\n      - name: clear-values\n        method: POST\n        description: Clears values from a spreadsheet.\n        inputParameters:\n        - name: spreadsheetId\n          in: path\n          type: string\n          required: true\n  \
  \        description: The ID of the spreadsheet to update.\n        - name: range\n          in: path\n          type: string\n          required: true\n          description: The A1 notation of the values to clear.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: batch-get-values\n        method: GET\n        description: Returns one or more ranges of values from a spreadsheet.\n        inputParameters:\n        - name: spreadsheetId\n          in: path\n          type: string\n          required: true\n          description: The ID of the spreadsheet to retrieve data from.\n        - name: ranges\n          in: query\n          type: array\n          required: true\n          description: The A1 notation of the values to retrieve.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: batch-update-values\n\
  \        method: POST\n        description: Sets values in one or more ranges of a spreadsheet.\n        inputParameters:\n        - name: spreadsheetId\n          in: path\n          type: string\n          required: true\n          description: The ID of the spreadsheet to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            data: '{{tools.data}}'\n            valueInputOption: '{{tools.valueInputOption}}'\n      - name: batch-clear-values\n        method: POST\n        description: Clears one or more ranges of values from a spreadsheet.\n        inputParameters:\n        - name: spreadsheetId\n          in: path\n          type: string\n          required: true\n          description: The ID of the spreadsheet to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n         \
  \ value: $.\n        body:\n          type: json\n          data:\n            ranges: '{{tools.ranges}}'\n    - name: sheets\n      path: /spreadsheets/{spreadsheetId}\n      description: Sheet management operations.\n      operations:\n      - name: copy-sheet\n        method: POST\n        description: Copies a single sheet from a spreadsheet to another spreadsheet.\n        inputParameters:\n        - name: spreadsheetId\n          in: path\n          type: string\n          required: true\n          description: The ID of the spreadsheet containing the sheet to copy.\n        - name: sheetId\n          in: path\n          type: integer\n          required: true\n          description: The ID of the sheet to copy.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            destinationSpreadsheetId: '{{tools.destinationSpreadsheetId}}'\n    - name: developer-metadata\n\
  \      path: /spreadsheets/{spreadsheetId}/developerMetadata\n      description: Developer metadata operations.\n      operations:\n      - name: get-developer-metadata\n        method: GET\n        description: Returns the developer metadata with the specified ID.\n        inputParameters:\n        - name: spreadsheetId\n          in: path\n          type: string\n          required: true\n          description: The ID of the spreadsheet.\n        - name: metadataId\n          in: path\n          type: integer\n          required: true\n          description: The ID of the developer metadata to retrieve.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: search-developer-metadata\n        method: POST\n        description: Returns all developer metadata matching the specified DataFilter.\n        inputParameters:\n        - name: spreadsheetId\n          in: path\n          type: string\n      \
  \    required: true\n          description: The ID of the spreadsheet.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            dataFilters: '{{tools.dataFilters}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sheets-data-api\n    description: Unified REST API for Google Sheets data management.\n    resources:\n    - path: /v1/spreadsheets\n      name: spreadsheets\n      description: Spreadsheet lifecycle operations\n      operations:\n      - method: POST\n        name: create-spreadsheet\n        description: Create a new spreadsheet\n        call: google-sheets.create-spreadsheet\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/spreadsheets/{spreadsheetId}\n      name: spreadsheet\n      description: Single spreadsheet operations\n      operations:\n      - method: GET\n        name: get-spreadsheet\n\
  \        description: Get spreadsheet details\n        call: google-sheets.get-spreadsheet\n        with:\n          spreadsheetId: rest.spreadsheetId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/spreadsheets/{spreadsheetId}/values/{range}\n      name: values\n      description: Cell value read and write operations\n      operations:\n      - method: GET\n        name: get-values\n        description: Read values from a range\n        call: google-sheets.get-values\n        with:\n          spreadsheetId: rest.spreadsheetId\n          range: rest.range\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-values\n        description: Write values to a range\n        call: google-sheets.update-values\n        with:\n          spreadsheetId: rest.spreadsheetId\n          range: rest.range\n          valueInputOption: rest.valueInputOption\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n      - method: POST\n        name: append-values\n        description: Append values to a range\n        call: google-sheets.append-values\n        with:\n          spreadsheetId: rest.spreadsheetId\n          range: rest.range\n          valueInputOption: rest.valueInputOption\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: clear-values\n        description: Clear values from a range\n        call: google-sheets.clear-values\n        with:\n          spreadsheetId: rest.spreadsheetId\n          range: rest.range\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: sheets-data-mcp\n    transport: http\n    description: MCP server for AI-assisted Google Sheets data management.\n    tools:\n    - name: create-spreadsheet\n      description: Create a new Google Sheets spreadsheet\n      hints:\n        readOnly: false\n    \
  \    idempotent: false\n      call: google-sheets.create-spreadsheet\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-spreadsheet\n      description: Get spreadsheet details by ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: google-sheets.get-spreadsheet\n      with:\n        spreadsheetId: tools.spreadsheetId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: batch-update-spreadsheet\n      description: Apply batch updates to a spreadsheet\n      hints:\n        readOnly: false\n        idempotent: false\n      call: google-sheets.batch-update-spreadsheet\n      with:\n        spreadsheetId: tools.spreadsheetId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-values\n      description: Read values from a spreadsheet range\n      hints:\n        readOnly: true\n        idempotent: true\n      call: google-sheets.get-values\n      with:\n        spreadsheetId:\
  \ tools.spreadsheetId\n        range: tools.range\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-values\n      description: Write values to a spreadsheet range\n      hints:\n        readOnly: false\n        idempotent: true\n      call: google-sheets.update-values\n      with:\n        spreadsheetId: tools.spreadsheetId\n        range: tools.range\n        valueInputOption: tools.valueInputOption\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: append-values\n      description: Append rows of data to a spreadsheet\n      hints:\n        readOnly: false\n        idempotent: false\n      call: google-sheets.append-values\n      with:\n        spreadsheetId: tools.spreadsheetId\n        range: tools.range\n        valueInputOption: tools.valueInputOption\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: clear-values\n      description: Clear values from a spreadsheet range\n      hints:\n\
  \        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-sheets.clear-values\n      with:\n        spreadsheetId: tools.spreadsheetId\n        range: tools.range\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: batch-get-values\n      description: Read values from multiple ranges at once\n      hints:\n        readOnly: true\n        idempotent: true\n      call: google-sheets.batch-get-values\n      with:\n        spreadsheetId: tools.spreadsheetId\n        ranges: tools.ranges\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: batch-update-values\n      description: Write values to multiple ranges at once\n      hints:\n        readOnly: false\n        idempotent: true\n      call: google-sheets.batch-update-values\n      with:\n        spreadsheetId: tools.spreadsheetId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: batch-clear-values\n      description:\
  \ Clear values from multiple ranges\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-sheets.batch-clear-values\n      with:\n        spreadsheetId: tools.spreadsheetId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: copy-sheet\n      description: Copy a sheet to another spreadsheet\n      hints:\n        readOnly: false\n        idempotent: false\n      call: google-sheets.copy-sheet\n      with:\n        spreadsheetId: tools.spreadsheetId\n        sheetId: tools.sheetId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-developer-metadata\n      description: Get developer metadata by ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: google-sheets.get-developer-metadata\n      with:\n        spreadsheetId: tools.spreadsheetId\n        metadataId: tools.metadataId\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: search-developer-metadata\n      description: Search developer metadata matching filters\n      hints:\n        readOnly: true\n        idempotent: true\n      call: google-sheets.search-developer-metadata\n      with:\n        spreadsheetId: tools.spreadsheetId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-sheets/refs/heads/main/capabilities/spreadsheet-data-management.yaml
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
