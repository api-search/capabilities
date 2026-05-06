---
categories: []
consumed_apis: []
description: The Microsoft Graph Excel API provides REST access to Excel workbooks stored in OneDrive, SharePoint, or Teams. Supports reading and writing cell values, executing formulas, managing worksheets, creating charts and tables, and running workbook sessions for transactional batch operations on Excel files.
layout: capability
name: Microsoft Graph Excel API
operations:
- description: Microsoft Excel List Worksheets
  method: GET
  name: listworksheets
  path: /me/drive/items/{driveItemId}/workbook/worksheets
- description: Microsoft Excel Add Worksheet
  method: POST
  name: addworksheet
  path: /me/drive/items/{driveItemId}/workbook/worksheets
- description: Microsoft Excel Get Cell Range Values
  method: GET
  name: getrange
  path: /me/drive/items/{driveItemId}/workbook/worksheets/{worksheetId}/range(address='{address}')
- description: Microsoft Excel Update Cell Range Values
  method: PATCH
  name: updaterange
  path: /me/drive/items/{driveItemId}/workbook/worksheets/{worksheetId}/range(address='{address}')
- description: Microsoft Excel List Worksheet Tables
  method: GET
  name: listtables
  path: /me/drive/items/{driveItemId}/workbook/worksheets/{worksheetId}/tables
- description: Microsoft Excel List Worksheet Charts
  method: GET
  name: listcharts
  path: /me/drive/items/{driveItemId}/workbook/worksheets/{worksheetId}/charts
- description: Microsoft Excel Add Chart to Worksheet
  method: POST
  name: addchart
  path: /me/drive/items/{driveItemId}/workbook/worksheets/{worksheetId}/charts
- description: Microsoft Excel Create Workbook Session
  method: POST
  name: createworkbooksession
  path: /me/drive/items/{driveItemId}/workbook/createSession
personas: []
provider_name: Advanced Excel
provider_slug: advanced-excel
search_terms:
- createworkbooksession
- data analysis
- spreadsheets
- microsoft excel add worksheet
- microsoft excel add chart to worksheet
- microsoft excel update cell range values
- listworksheets
- addchart
- developer building automated excel-based business workflows
- microsoft excel list worksheets
- advanced
- automation
- listcharts
- getrange
- api
- microsoft excel get cell range values
- microsoft excel create workbook session
- microsoft excel list worksheet tables
- data processing
- analyst who reads and writes excel data for reporting and analytics
- business intelligence
- updaterange
- microsoft excel list worksheet charts
- microsoft
- listtables
- addworksheet
- bi engineer integrating excel data with data warehouses and dashboards
- excel
slug: advanced-excel-capability
source_filename: advanced-excel-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Microsoft Graph Excel API\n  description: The Microsoft Graph Excel API provides REST access to Excel workbooks stored in OneDrive, SharePoint, or Teams.\n    Supports reading and writing cell values, executing formulas, managing worksheets, creating charts and tables, and running\n    workbook sessions for transactional batch operations on Excel files.\n  tags:\n  - Advanced\n  - Excel\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: advanced-excel\n    baseUri: https://graph.microsoft.com/v1.0\n    description: Microsoft Graph Excel API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{ADVANCED_EXCEL_TOKEN}}'\n    resources:\n    - name: me-drive-items-driveitemid-workbook-worksheets\n      path: /me/drive/items/{driveItemId}/workbook/worksheets\n      operations:\n      - name: listworksheets\n        method: GET\n        description: Microsoft Excel\
  \ List Worksheets\n        inputParameters:\n        - name: driveItemId\n          in: path\n          type: string\n          required: true\n          description: OneDrive item ID of the Excel workbook.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addworksheet\n        method: POST\n        description: Microsoft Excel Add Worksheet\n        inputParameters:\n        - name: driveItemId\n          in: path\n          type: string\n          required: true\n          description: OneDrive item ID of the Excel workbook.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: me-drive-items-driveitemid-workbook-worksheets-w\n      path: /me/drive/items/{driveItemId}/workbook/worksheets/{worksheetId}/range(address='{address}')\n      operations:\n      - name: getrange\n        method: GET\n        description:\
  \ Microsoft Excel Get Cell Range Values\n        inputParameters:\n        - name: driveItemId\n          in: path\n          type: string\n          required: true\n          description: OneDrive item ID of the Excel workbook.\n        - name: worksheetId\n          in: path\n          type: string\n          required: true\n          description: Worksheet ID or name.\n        - name: address\n          in: path\n          type: string\n          required: true\n          description: Cell range address (e.g., A1:D10).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updaterange\n        method: PATCH\n        description: Microsoft Excel Update Cell Range Values\n        inputParameters:\n        - name: driveItemId\n          in: path\n          type: string\n          required: true\n          description: OneDrive item ID of the Excel workbook.\n        - name: worksheetId\n          in:\
  \ path\n          type: string\n          required: true\n          description: Worksheet ID or name.\n        - name: address\n          in: path\n          type: string\n          required: true\n          description: Cell range address (e.g., A1:D10).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: me-drive-items-driveitemid-workbook-worksheets-w\n      path: /me/drive/items/{driveItemId}/workbook/worksheets/{worksheetId}/tables\n      operations:\n      - name: listtables\n        method: GET\n        description: Microsoft Excel List Worksheet Tables\n        inputParameters:\n        - name: driveItemId\n          in: path\n          type: string\n          required: true\n          description: OneDrive item ID of the Excel workbook.\n        - name: worksheetId\n          in: path\n          type: string\n          required: true\n          description: Worksheet ID or name.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: me-drive-items-driveitemid-workbook-worksheets-w\n      path: /me/drive/items/{driveItemId}/workbook/worksheets/{worksheetId}/charts\n      operations:\n      - name: listcharts\n        method: GET\n        description: Microsoft Excel List Worksheet Charts\n        inputParameters:\n        - name: driveItemId\n          in: path\n          type: string\n          required: true\n          description: OneDrive item ID of the Excel workbook.\n        - name: worksheetId\n          in: path\n          type: string\n          required: true\n          description: Worksheet ID or name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addchart\n        method: POST\n        description: Microsoft Excel Add Chart to Worksheet\n        inputParameters:\n        - name: driveItemId\n\
  \          in: path\n          type: string\n          required: true\n          description: OneDrive item ID of the Excel workbook.\n        - name: worksheetId\n          in: path\n          type: string\n          required: true\n          description: Worksheet ID or name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: me-drive-items-driveitemid-workbook-createsessio\n      path: /me/drive/items/{driveItemId}/workbook/createSession\n      operations:\n      - name: createworkbooksession\n        method: POST\n        description: Microsoft Excel Create Workbook Session\n        inputParameters:\n        - name: driveItemId\n          in: path\n          type: string\n          required: true\n          description: OneDrive item ID of the Excel workbook.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n\
  \  - type: rest\n    port: 8080\n    namespace: advanced-excel-rest\n    description: REST adapter for Microsoft Graph Excel API.\n    resources:\n    - path: /me/drive/items/{driveItemId}/workbook/worksheets\n      name: listworksheets\n      operations:\n      - method: GET\n        name: listworksheets\n        description: Microsoft Excel List Worksheets\n        call: advanced-excel.listworksheets\n        with:\n          driveItemId: rest.driveItemId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /me/drive/items/{driveItemId}/workbook/worksheets\n      name: addworksheet\n      operations:\n      - method: POST\n        name: addworksheet\n        description: Microsoft Excel Add Worksheet\n        call: advanced-excel.addworksheet\n        with:\n          driveItemId: rest.driveItemId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /me/drive/items/{driveItemId}/workbook/worksheets/{worksheetId}/range(address='{address}')\n\
  \      name: getrange\n      operations:\n      - method: GET\n        name: getrange\n        description: Microsoft Excel Get Cell Range Values\n        call: advanced-excel.getrange\n        with:\n          driveItemId: rest.driveItemId\n          worksheetId: rest.worksheetId\n          address: rest.address\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /me/drive/items/{driveItemId}/workbook/worksheets/{worksheetId}/range(address='{address}')\n      name: updaterange\n      operations:\n      - method: PATCH\n        name: updaterange\n        description: Microsoft Excel Update Cell Range Values\n        call: advanced-excel.updaterange\n        with:\n          driveItemId: rest.driveItemId\n          worksheetId: rest.worksheetId\n          address: rest.address\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /me/drive/items/{driveItemId}/workbook/worksheets/{worksheetId}/tables\n      name: listtables\n\
  \      operations:\n      - method: GET\n        name: listtables\n        description: Microsoft Excel List Worksheet Tables\n        call: advanced-excel.listtables\n        with:\n          driveItemId: rest.driveItemId\n          worksheetId: rest.worksheetId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /me/drive/items/{driveItemId}/workbook/worksheets/{worksheetId}/charts\n      name: listcharts\n      operations:\n      - method: GET\n        name: listcharts\n        description: Microsoft Excel List Worksheet Charts\n        call: advanced-excel.listcharts\n        with:\n          driveItemId: rest.driveItemId\n          worksheetId: rest.worksheetId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /me/drive/items/{driveItemId}/workbook/worksheets/{worksheetId}/charts\n      name: addchart\n      operations:\n      - method: POST\n        name: addchart\n        description: Microsoft Excel Add Chart\
  \ to Worksheet\n        call: advanced-excel.addchart\n        with:\n          driveItemId: rest.driveItemId\n          worksheetId: rest.worksheetId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /me/drive/items/{driveItemId}/workbook/createSession\n      name: createworkbooksession\n      operations:\n      - method: POST\n        name: createworkbooksession\n        description: Microsoft Excel Create Workbook Session\n        call: advanced-excel.createworkbooksession\n        with:\n          driveItemId: rest.driveItemId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: advanced-excel-mcp\n    transport: http\n    description: MCP adapter for Microsoft Graph Excel API for AI agent use.\n    tools:\n    - name: listworksheets\n      description: Microsoft Excel List Worksheets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n \
  \     call: advanced-excel.listworksheets\n      with:\n        driveItemId: tools.driveItemId\n      inputParameters:\n      - name: driveItemId\n        type: string\n        description: OneDrive item ID of the Excel workbook.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: addworksheet\n      description: Microsoft Excel Add Worksheet\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: advanced-excel.addworksheet\n      with:\n        driveItemId: tools.driveItemId\n      inputParameters:\n      - name: driveItemId\n        type: string\n        description: OneDrive item ID of the Excel workbook.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrange\n      description: Microsoft Excel Get Cell Range Values\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: advanced-excel.getrange\n\
  \      with:\n        driveItemId: tools.driveItemId\n        worksheetId: tools.worksheetId\n        address: tools.address\n      inputParameters:\n      - name: driveItemId\n        type: string\n        description: OneDrive item ID of the Excel workbook.\n        required: true\n      - name: worksheetId\n        type: string\n        description: Worksheet ID or name.\n        required: true\n      - name: address\n        type: string\n        description: Cell range address (e.g., A1:D10).\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updaterange\n      description: Microsoft Excel Update Cell Range Values\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: advanced-excel.updaterange\n      with:\n        driveItemId: tools.driveItemId\n        worksheetId: tools.worksheetId\n        address: tools.address\n      inputParameters:\n      - name: driveItemId\n       \
  \ type: string\n        description: OneDrive item ID of the Excel workbook.\n        required: true\n      - name: worksheetId\n        type: string\n        description: Worksheet ID or name.\n        required: true\n      - name: address\n        type: string\n        description: Cell range address (e.g., A1:D10).\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtables\n      description: Microsoft Excel List Worksheet Tables\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: advanced-excel.listtables\n      with:\n        driveItemId: tools.driveItemId\n        worksheetId: tools.worksheetId\n      inputParameters:\n      - name: driveItemId\n        type: string\n        description: OneDrive item ID of the Excel workbook.\n        required: true\n      - name: worksheetId\n        type: string\n        description: Worksheet ID or name.\n        required: true\n    \
  \  outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcharts\n      description: Microsoft Excel List Worksheet Charts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: advanced-excel.listcharts\n      with:\n        driveItemId: tools.driveItemId\n        worksheetId: tools.worksheetId\n      inputParameters:\n      - name: driveItemId\n        type: string\n        description: OneDrive item ID of the Excel workbook.\n        required: true\n      - name: worksheetId\n        type: string\n        description: Worksheet ID or name.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: addchart\n      description: Microsoft Excel Add Chart to Worksheet\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: advanced-excel.addchart\n      with:\n        driveItemId: tools.driveItemId\n        worksheetId:\
  \ tools.worksheetId\n      inputParameters:\n      - name: driveItemId\n        type: string\n        description: OneDrive item ID of the Excel workbook.\n        required: true\n      - name: worksheetId\n        type: string\n        description: Worksheet ID or name.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createworkbooksession\n      description: Microsoft Excel Create Workbook Session\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: advanced-excel.createworkbooksession\n      with:\n        driveItemId: tools.driveItemId\n      inputParameters:\n      - name: driveItemId\n        type: string\n        description: OneDrive item ID of the Excel workbook.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ADVANCED_EXCEL_TOKEN: ADVANCED_EXCEL_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/advanced-excel/refs/heads/main/capabilities/advanced-excel-capability.yaml
tags:
- Advanced
- Excel
- API
tools:
- description: Microsoft Excel List Worksheets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listworksheets
- description: Microsoft Excel Add Worksheet
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addworksheet
- description: Microsoft Excel Get Cell Range Values
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrange
- description: Microsoft Excel Update Cell Range Values
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updaterange
- description: Microsoft Excel List Worksheet Tables
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtables
- description: Microsoft Excel List Worksheet Charts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcharts
- description: Microsoft Excel Add Chart to Worksheet
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addchart
- description: Microsoft Excel Create Workbook Session
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createworkbooksession
---
