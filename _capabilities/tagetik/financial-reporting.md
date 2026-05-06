---
categories: []
consumed_apis: []
description: Workflow capability for finance teams and BI analysts to query CCH Tagetik financial consolidation and analytical workspace data. Covers actual results, budget comparisons, forecasts, and multi-dimensional financial analysis for close, consolidation, and reporting workflows.
layout: capability
name: CCH Tagetik Financial Reporting
operations:
- description: Retrieve financial records filtered by year, period, scenario, and entity
  method: GET
  name: query-financial-data
  path: /v1/financial-data
- description: Retrieve analytical workspace records
  method: GET
  name: query-analytical-data
  path: /v1/analytical-data
- description: Retrieve available entity sets and their properties
  method: GET
  name: get-odata-metadata
  path: /v1/metadata
personas: []
provider_name: CCH Tagetik
provider_slug: tagetik
search_terms:
- corporate performance management
- financial reporting
- reporting
- analytics
- query financial consolidation data across entities, periods, and scenarios
- query analytical workspace data for planning and analysis
- query financial data
- financial consolidation
- financial close
- forecasting
- query cch tagetik financial consolidation data with filters for year, period, scenario (actual/budget/forecast), entity, and account
- esg
- query cch tagetik analytical workspace data for budget, forecast, and planning scenarios
- retrieve financial records filtered by year, period, scenario, and entity
- financial planning
- retrieve analytical workspace records
- retrieve available entity sets and their properties
- odata
- query analytical data
- discover available cch tagetik entity sets, dimensions, and data models in a given database
- budgeting
- odata service metadata for entity discovery
- get odata metadata
slug: financial-reporting
source_filename: financial-reporting.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: CCH Tagetik Financial Reporting\n  description: Workflow capability for finance teams and BI analysts to query CCH Tagetik financial consolidation and analytical\n    workspace data. Covers actual results, budget comparisons, forecasts, and multi-dimensional financial analysis for close,\n    consolidation, and reporting workflows.\n  tags:\n  - Budgeting\n  - Corporate Performance Management\n  - Financial Close\n  - Financial Consolidation\n  - Financial Reporting\n  - Forecasting\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TAGETIK_ACCESS_TOKEN: TAGETIK_ACCESS_TOKEN\n    TAGETIK_BASE_URL: TAGETIK_BASE_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: tagetik-odata\n    baseUri: '{{TAGETIK_BASE_URL}}'\n    description: CCH Tagetik OData v4 REST API\n    authentication:\n      type: bearer\n      token: '{{TAGETIK_ACCESS_TOKEN}}'\n    resources:\n    - name: metadata\n      path:\
  \ /$metadata\n      description: OData service metadata describing available entity sets\n      operations:\n      - name: get-odata-metadata\n        method: GET\n        description: Retrieve OData service metadata\n        inputParameters:\n        - name: database\n          in: query\n          type: string\n          required: true\n          description: CCH Tagetik database code\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: financial-data\n      path: /odata/{database}/FinancialData\n      description: Financial data from consolidated models\n      operations:\n      - name: query-financial-data\n        method: GET\n        description: Query financial data records with OData filters\n        inputParameters:\n        - name: database\n          in: path\n          type: string\n          required: true\n          description: Database code\n        - name: $filter\n          in: query\n\
  \          type: string\n          required: false\n          description: OData filter expression\n        - name: $select\n          in: query\n          type: string\n          required: false\n          description: Comma-separated fields to return\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Max rows to return\n        - name: $skip\n          in: query\n          type: integer\n          required: false\n          description: Rows to skip for pagination\n        - name: $orderby\n          in: query\n          type: string\n          required: false\n          description: Sort field and direction\n        - name: $count\n          in: query\n          type: boolean\n          required: false\n          description: Include total count\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.value\n    - name: analytical-data\n      path:\
  \ /odata/{database}/{workspace}\n      description: Analytical workspace data\n      operations:\n      - name: query-analytical-data\n        method: GET\n        description: Query analytical workspace dataset records\n        inputParameters:\n        - name: database\n          in: path\n          type: string\n          required: true\n          description: Database code\n        - name: workspace\n          in: path\n          type: string\n          required: true\n          description: Analytical workspace entity set name\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter expression\n        - name: $select\n          in: query\n          type: string\n          required: false\n          description: Fields to return\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Max rows\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.value\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: tagetik-reporting-api\n    description: Unified REST API for CCH Tagetik financial reporting workflows.\n    resources:\n    - path: /v1/financial-data\n      name: financial-data\n      description: Query financial consolidation data across entities, periods, and scenarios\n      operations:\n      - method: GET\n        name: query-financial-data\n        description: Retrieve financial records filtered by year, period, scenario, and entity\n        call: tagetik-odata.query-financial-data\n        with:\n          database: rest.database\n          $filter: rest.filter\n          $select: rest.select\n          $top: rest.top\n          $skip: rest.skip\n          $orderby: rest.orderby\n          $count: rest.count\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/analytical-data\n      name: analytical-data\n\
  \      description: Query analytical workspace data for planning and analysis\n      operations:\n      - method: GET\n        name: query-analytical-data\n        description: Retrieve analytical workspace records\n        call: tagetik-odata.query-analytical-data\n        with:\n          database: rest.database\n          workspace: rest.workspace\n          $filter: rest.filter\n          $top: rest.top\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/metadata\n      name: odata-metadata\n      description: OData service metadata for entity discovery\n      operations:\n      - method: GET\n        name: get-odata-metadata\n        description: Retrieve available entity sets and their properties\n        call: tagetik-odata.get-odata-metadata\n        with:\n          database: rest.database\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: tagetik-reporting-mcp\n    transport:\
  \ http\n    description: MCP server for AI-assisted financial reporting and close analysis.\n    tools:\n    - name: query-financial-data\n      description: Query CCH Tagetik financial consolidation data with filters for year, period, scenario (Actual/Budget/Forecast),\n        entity, and account\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tagetik-odata.query-financial-data\n      with:\n        database: tools.database\n        $filter: tools.filter\n        $select: tools.select\n        $top: tools.top\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-analytical-data\n      description: Query CCH Tagetik analytical workspace data for budget, forecast, and planning scenarios\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tagetik-odata.query-analytical-data\n      with:\n        database: tools.database\n        workspace: tools.workspace\n        $filter: tools.filter\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-odata-metadata\n      description: Discover available CCH Tagetik entity sets, dimensions, and data models in a given database\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tagetik-odata.get-odata-metadata\n      with:\n        database: tools.database\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tagetik/refs/heads/main/capabilities/financial-reporting.yaml
tags:
- Budgeting
- Corporate Performance Management
- Financial Close
- Financial Consolidation
- Financial Reporting
- Forecasting
tools:
- description: Query CCH Tagetik financial consolidation data with filters for year, period, scenario (Actual/Budget/Forecast), entity, and account
  hints:
    openWorld: false
    readOnly: true
  name: query-financial-data
- description: Query CCH Tagetik analytical workspace data for budget, forecast, and planning scenarios
  hints:
    openWorld: false
    readOnly: true
  name: query-analytical-data
- description: Discover available CCH Tagetik entity sets, dimensions, and data models in a given database
  hints:
    openWorld: false
    readOnly: true
  name: get-odata-metadata
---
