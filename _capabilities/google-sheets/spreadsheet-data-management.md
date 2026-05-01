---
api_specs:
- filename: google-sheets-openapi.yml
  format: yaml
  label: google-sheets
  slug: google-sheets
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/google-sheets/refs/heads/main/openapi/google-sheets-openapi.yml
categories:
- automation
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
- write values to multiple ranges at once
- append values
- spreadsheet lifecycle operations
- clear values from multiple ranges
- google sheets
- update values
- get values
- clear values
- append rows of data to a spreadsheet
- read values from multiple ranges at once
- single spreadsheet operations
- search developer metadata
- batch update spreadsheet
- create a new google sheets spreadsheet
- copy a sheet to another spreadsheet
- automation
- batch get values
- cell value read and write operations
- write values to a spreadsheet range
- google workspace
- apply batch updates to a spreadsheet
- get spreadsheet
- write values to a range
- create a new spreadsheet
- get developer metadata by id
- clear values from a range
- get spreadsheet details
- batch clear values
- productivity
- read values from a spreadsheet range
- clear values from a spreadsheet range
- batch update values
- get developer metadata
- read values from a range
- data management
- copy sheet
- spreadsheets
- create spreadsheet
- get spreadsheet details by id
- search developer metadata matching filters
- append values to a range
slug: spreadsheet-data-management
source_filename: spreadsheet-data-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Google Sheets Spreadsheet Data Management\"\n  description: \"Workflow for managing spreadsheet data including creating spreadsheets, reading and writing cell values, batch operations, and metadata management. Used by data analysts, developers, and automation engineers.\"\n  tags:\n    - Google Sheets\n    - Spreadsheets\n    - Data Management\n    - Automation\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      GOOGLE_OAUTH_TOKEN: GOOGLE_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: google-sheets\n      location: ./shared/google-sheets.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sheets-data-api\n      description: \"Unified REST API for Google Sheets data management.\"\n      resources:\n        - path: /v1/spreadsheets\n          name: spreadsheets\n          description: \"Spreadsheet lifecycle operations\"\n          operations:\n     \
  \       - method: POST\n              name: create-spreadsheet\n              description: \"Create a new spreadsheet\"\n              call: \"google-sheets.create-spreadsheet\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/spreadsheets/{spreadsheetId}\n          name: spreadsheet\n          description: \"Single spreadsheet operations\"\n          operations:\n            - method: GET\n              name: get-spreadsheet\n              description: \"Get spreadsheet details\"\n              call: \"google-sheets.get-spreadsheet\"\n              with:\n                spreadsheetId: \"rest.spreadsheetId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/spreadsheets/{spreadsheetId}/values/{range}\n          name: values\n          description: \"Cell value read and write operations\"\n          operations:\n            - method: GET\n     \
  \         name: get-values\n              description: \"Read values from a range\"\n              call: \"google-sheets.get-values\"\n              with:\n                spreadsheetId: \"rest.spreadsheetId\"\n                range: \"rest.range\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-values\n              description: \"Write values to a range\"\n              call: \"google-sheets.update-values\"\n              with:\n                spreadsheetId: \"rest.spreadsheetId\"\n                range: \"rest.range\"\n                valueInputOption: \"rest.valueInputOption\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: append-values\n              description: \"Append values to a range\"\n              call: \"google-sheets.append-values\"\n              with:\n        \
  \        spreadsheetId: \"rest.spreadsheetId\"\n                range: \"rest.range\"\n                valueInputOption: \"rest.valueInputOption\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: clear-values\n              description: \"Clear values from a range\"\n              call: \"google-sheets.clear-values\"\n              with:\n                spreadsheetId: \"rest.spreadsheetId\"\n                range: \"rest.range\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: sheets-data-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Google Sheets data management.\"\n      tools:\n        - name: create-spreadsheet\n          description: \"Create a new Google Sheets spreadsheet\"\n          hints:\n            readOnly: false\n            idempotent:\
  \ false\n          call: \"google-sheets.create-spreadsheet\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-spreadsheet\n          description: \"Get spreadsheet details by ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"google-sheets.get-spreadsheet\"\n          with:\n            spreadsheetId: \"tools.spreadsheetId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: batch-update-spreadsheet\n          description: \"Apply batch updates to a spreadsheet\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"google-sheets.batch-update-spreadsheet\"\n          with:\n            spreadsheetId: \"tools.spreadsheetId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-values\n          description: \"Read values from a\
  \ spreadsheet range\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"google-sheets.get-values\"\n          with:\n            spreadsheetId: \"tools.spreadsheetId\"\n            range: \"tools.range\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-values\n          description: \"Write values to a spreadsheet range\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"google-sheets.update-values\"\n          with:\n            spreadsheetId: \"tools.spreadsheetId\"\n            range: \"tools.range\"\n            valueInputOption: \"tools.valueInputOption\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: append-values\n          description: \"Append rows of data to a spreadsheet\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call:\
  \ \"google-sheets.append-values\"\n          with:\n            spreadsheetId: \"tools.spreadsheetId\"\n            range: \"tools.range\"\n            valueInputOption: \"tools.valueInputOption\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: clear-values\n          description: \"Clear values from a spreadsheet range\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"google-sheets.clear-values\"\n          with:\n            spreadsheetId: \"tools.spreadsheetId\"\n            range: \"tools.range\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: batch-get-values\n          description: \"Read values from multiple ranges at once\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"google-sheets.batch-get-values\"\n          with:\n            spreadsheetId:\
  \ \"tools.spreadsheetId\"\n            ranges: \"tools.ranges\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: batch-update-values\n          description: \"Write values to multiple ranges at once\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"google-sheets.batch-update-values\"\n          with:\n            spreadsheetId: \"tools.spreadsheetId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: batch-clear-values\n          description: \"Clear values from multiple ranges\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"google-sheets.batch-clear-values\"\n          with:\n            spreadsheetId: \"tools.spreadsheetId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: copy-sheet\n       \
  \   description: \"Copy a sheet to another spreadsheet\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"google-sheets.copy-sheet\"\n          with:\n            spreadsheetId: \"tools.spreadsheetId\"\n            sheetId: \"tools.sheetId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-developer-metadata\n          description: \"Get developer metadata by ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"google-sheets.get-developer-metadata\"\n          with:\n            spreadsheetId: \"tools.spreadsheetId\"\n            metadataId: \"tools.metadataId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-developer-metadata\n          description: \"Search developer metadata matching filters\"\n          hints:\n            readOnly: true\n            idempotent: true\n\
  \          call: \"google-sheets.search-developer-metadata\"\n          with:\n            spreadsheetId: \"tools.spreadsheetId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
