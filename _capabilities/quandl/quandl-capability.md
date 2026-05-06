---
categories: []
consumed_apis: []
description: Nasdaq Data Link REST API (formerly Quandl) provides access to financial and economic time-series datasets including stock prices, economic indicators, interest rates, and commodity data in JSON, XML, and CSV formats. Authenticated users receive up to 50,000 API calls per day.
layout: capability
name: Nasdaq Data Link Time-Series REST API
operations:
- description: Get a time-series dataset
  method: GET
  name: getdataset
  path: /datasets/{databaseCode}/{datasetCode}
- description: Get dataset metadata
  method: GET
  name: getdatasetmetadata
  path: /datasets/{databaseCode}/{datasetCode}/metadata
- description: List databases
  method: GET
  name: listdatabases
  path: /databases
- description: Get database metadata
  method: GET
  name: getdatabase
  path: /databases/{databaseCode}
- description: List datasets in a database
  method: GET
  name: listdatabasedatasets
  path: /databases/{databaseCode}/datasets
- description: Query a datatable
  method: GET
  name: getdatatable
  path: /datatables/{datatablesCode}
personas: []
provider_name: Quandl (Nasdaq Data Link)
provider_slug: quandl
search_terms:
- getdataset
- economic data
- market data
- quandl
- finance
- get a time-series dataset
- getdatasetmetadata
- list datasets in a database
- getdatabase
- time series
- getdatatable
- get database metadata
- api
- get dataset metadata
- listdatabasedatasets
- list databases
- listdatabases
- streaming
- query a datatable
slug: quandl-capability
source_filename: quandl-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Nasdaq Data Link Time-Series REST API\n  description: Nasdaq Data Link REST API (formerly Quandl) provides access to financial and economic time-series datasets\n    including stock prices, economic indicators, interest rates, and commodity data in JSON, XML, and CSV formats. Authenticated\n    users receive up to 50,000 API calls per day.\n  tags:\n  - Quandl\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: quandl\n    baseUri: https://data.nasdaq.com/api/v3\n    description: Nasdaq Data Link Time-Series REST API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: api_key\n      value: '{{QUANDL_TOKEN}}'\n    resources:\n    - name: datasets-databasecode-datasetcode\n      path: /datasets/{databaseCode}/{datasetCode}\n      operations:\n      - name: getdataset\n        method: GET\n        description: Get a time-series dataset\n       \
  \ inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          description: Number of rows to return (0 returns all)\n        - name: column_index\n          in: query\n          type: integer\n          description: Request a specific column (1-based index)\n        - name: start_date\n          in: query\n          type: string\n          description: Retrieve data rows on and after this date (YYYY-MM-DD)\n        - name: end_date\n          in: query\n          type: string\n          description: Retrieve data rows up to and including this date (YYYY-MM-DD)\n        - name: order\n          in: query\n          type: string\n          description: Return data in ascending or descending date order\n        - name: collapse\n          in: query\n          type: string\n          description: Frequency to collapse data to\n        - name: transform\n          in: query\n          type: string\n          description: Mathematical transformation to apply\
  \ to values\n        - name: api_key\n          in: query\n          type: string\n          description: Your Nasdaq Data Link API key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: datasets-databasecode-datasetcode-metadata\n      path: /datasets/{databaseCode}/{datasetCode}/metadata\n      operations:\n      - name: getdatasetmetadata\n        method: GET\n        description: Get dataset metadata\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: databases\n      path: /databases\n      operations:\n      - name: listdatabases\n        method: GET\n        description: List databases\n        inputParameters:\n        - name: per_page\n          in: query\n          type: integer\n        - name: page\n          in: query\n          type: integer\n        - name: query\n          in: query\n          type:\
  \ string\n          description: Search query for database name or description\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: databases-databasecode\n      path: /databases/{databaseCode}\n      operations:\n      - name: getdatabase\n        method: GET\n        description: Get database metadata\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: databases-databasecode-datasets\n      path: /databases/{databaseCode}/datasets\n      operations:\n      - name: listdatabasedatasets\n        method: GET\n        description: List datasets in a database\n        inputParameters:\n        - name: per_page\n          in: query\n          type: integer\n        - name: page\n          in: query\n          type: integer\n        - name: query\n          in: query\n          type: string\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: datatables-datatablescode\n      path: /datatables/{datatablesCode}\n      operations:\n      - name: getdatatable\n        method: GET\n        description: Query a datatable\n        inputParameters:\n        - name: datatablesCode\n          in: path\n          type: string\n          required: true\n          description: Database code and datatable code joined by slash (e.g. ZACKS/FC)\n        - name: qopts.columns\n          in: query\n          type: string\n          description: Comma-separated column names to return\n        - name: qopts.per_page\n          in: query\n          type: integer\n          description: Number of rows per page (max 10000)\n        - name: qopts.cursor_id\n          in: query\n          type: string\n          description: Cursor ID for pagination from previous response\n        - name: qopts.export\n          in: query\n          type: boolean\n\
  \          description: Set to true to get a download link for full dataset\n        - name: api_key\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: quandl-rest\n    description: REST adapter for Nasdaq Data Link Time-Series REST API.\n    resources:\n    - path: /datasets/{databaseCode}/{datasetCode}\n      name: getdataset\n      operations:\n      - method: GET\n        name: getdataset\n        description: Get a time-series dataset\n        call: quandl.getdataset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /datasets/{databaseCode}/{datasetCode}/metadata\n      name: getdatasetmetadata\n      operations:\n      - method: GET\n        name: getdatasetmetadata\n        description: Get dataset metadata\n        call: quandl.getdatasetmetadata\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /databases\n      name: listdatabases\n      operations:\n      - method: GET\n        name: listdatabases\n        description: List databases\n        call: quandl.listdatabases\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /databases/{databaseCode}\n      name: getdatabase\n      operations:\n      - method: GET\n        name: getdatabase\n        description: Get database metadata\n        call: quandl.getdatabase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /databases/{databaseCode}/datasets\n      name: listdatabasedatasets\n      operations:\n      - method: GET\n        name: listdatabasedatasets\n        description: List datasets in a database\n        call: quandl.listdatabasedatasets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /datatables/{datatablesCode}\n      name: getdatatable\n      operations:\n\
  \      - method: GET\n        name: getdatatable\n        description: Query a datatable\n        call: quandl.getdatatable\n        with:\n          datatablesCode: rest.datatablesCode\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: quandl-mcp\n    transport: http\n    description: MCP adapter for Nasdaq Data Link Time-Series REST API for AI agent use.\n    tools:\n    - name: getdataset\n      description: Get a time-series dataset\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quandl.getdataset\n      with:\n        limit: tools.limit\n        column_index: tools.column_index\n        start_date: tools.start_date\n        end_date: tools.end_date\n        order: tools.order\n        collapse: tools.collapse\n        transform: tools.transform\n        api_key: tools.api_key\n      inputParameters:\n      - name: limit\n        type: integer\n        description:\
  \ Number of rows to return (0 returns all)\n      - name: column_index\n        type: integer\n        description: Request a specific column (1-based index)\n      - name: start_date\n        type: string\n        description: Retrieve data rows on and after this date (YYYY-MM-DD)\n      - name: end_date\n        type: string\n        description: Retrieve data rows up to and including this date (YYYY-MM-DD)\n      - name: order\n        type: string\n        description: Return data in ascending or descending date order\n      - name: collapse\n        type: string\n        description: Frequency to collapse data to\n      - name: transform\n        type: string\n        description: Mathematical transformation to apply to values\n      - name: api_key\n        type: string\n        description: Your Nasdaq Data Link API key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdatasetmetadata\n      description: Get dataset metadata\n      hints:\n    \
  \    readOnly: true\n        destructive: false\n        idempotent: true\n      call: quandl.getdatasetmetadata\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdatabases\n      description: List databases\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quandl.listdatabases\n      with:\n        per_page: tools.per_page\n        page: tools.page\n        query: tools.query\n      inputParameters:\n      - name: per_page\n        type: integer\n        description: per_page\n      - name: page\n        type: integer\n        description: page\n      - name: query\n        type: string\n        description: Search query for database name or description\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdatabase\n      description: Get database metadata\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quandl.getdatabase\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdatabasedatasets\n      description: List datasets in a database\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quandl.listdatabasedatasets\n      with:\n        per_page: tools.per_page\n        page: tools.page\n        query: tools.query\n      inputParameters:\n      - name: per_page\n        type: integer\n        description: per_page\n      - name: page\n        type: integer\n        description: page\n      - name: query\n        type: string\n        description: query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdatatable\n      description: Query a datatable\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: quandl.getdatatable\n      with:\n        datatablesCode: tools.datatablesCode\n        qopts.columns: tools.qopts.columns\n        qopts.per_page:\
  \ tools.qopts.per_page\n        qopts.cursor_id: tools.qopts.cursor_id\n        qopts.export: tools.qopts.export\n        api_key: tools.api_key\n      inputParameters:\n      - name: datatablesCode\n        type: string\n        description: Database code and datatable code joined by slash (e.g. ZACKS/FC)\n        required: true\n      - name: qopts.columns\n        type: string\n        description: Comma-separated column names to return\n      - name: qopts.per_page\n        type: integer\n        description: Number of rows per page (max 10000)\n      - name: qopts.cursor_id\n        type: string\n        description: Cursor ID for pagination from previous response\n      - name: qopts.export\n        type: boolean\n        description: Set to true to get a download link for full dataset\n      - name: api_key\n        type: string\n        description: api_key\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    QUANDL_TOKEN:\
  \ QUANDL_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/quandl/refs/heads/main/capabilities/quandl-capability.yaml
tags:
- Quandl
- API
tools:
- description: Get a time-series dataset
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdataset
- description: Get dataset metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdatasetmetadata
- description: List databases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdatabases
- description: Get database metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdatabase
- description: List datasets in a database
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdatabasedatasets
- description: Query a datatable
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdatatable
---
