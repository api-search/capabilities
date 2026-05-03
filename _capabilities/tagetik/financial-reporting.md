---
api_specs:
- filename: cch-tagetik-odata-openapi.yml
  format: yaml
  label: tagetik-odata
  slug: tagetik-odata
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/tagetik/refs/heads/main/openapi/cch-tagetik-odata-openapi.yml
categories: []
consumed_apis:
- tagetik-odata
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
- query financial consolidation data across entities, periods, and scenarios
- retrieve financial records filtered by year, period, scenario, and entity
- query cch tagetik analytical workspace data for budget, forecast, and planning scenarios
- analytics
- retrieve analytical workspace records
- financial consolidation
- retrieve available entity sets and their properties
- odata service metadata for entity discovery
- odata
- query analytical workspace data for planning and analysis
- financial planning
- query financial data
- esg
- financial close
- reporting
- corporate performance management
- get odata metadata
- query cch tagetik financial consolidation data with filters for year, period, scenario (actual/budget/forecast), entity, and account
- budgeting
- discover available cch tagetik entity sets, dimensions, and data models in a given database
- forecasting
- query analytical data
- financial reporting
slug: financial-reporting
source_filename: financial-reporting.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"CCH Tagetik Financial Reporting\"\n  description: >-\n    Workflow capability for finance teams and BI analysts to query CCH Tagetik\n    financial consolidation and analytical workspace data. Covers actual results,\n    budget comparisons, forecasts, and multi-dimensional financial analysis\n    for close, consolidation, and reporting workflows.\n  tags:\n    - Budgeting\n    - Corporate Performance Management\n    - Financial Close\n    - Financial Consolidation\n    - Financial Reporting\n    - Forecasting\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TAGETIK_ACCESS_TOKEN: TAGETIK_ACCESS_TOKEN\n      TAGETIK_BASE_URL: TAGETIK_BASE_URL\n\ncapability:\n  consumes:\n    - import: tagetik-odata\n      location: ./shared/cch-tagetik-odata.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: tagetik-reporting-api\n      description: \"Unified REST API for\
  \ CCH Tagetik financial reporting workflows.\"\n      resources:\n        - path: /v1/financial-data\n          name: financial-data\n          description: \"Query financial consolidation data across entities, periods, and scenarios\"\n          operations:\n            - method: GET\n              name: query-financial-data\n              description: \"Retrieve financial records filtered by year, period, scenario, and entity\"\n              call: \"tagetik-odata.query-financial-data\"\n              with:\n                database: \"rest.database\"\n                $filter: \"rest.filter\"\n                $select: \"rest.select\"\n                $top: \"rest.top\"\n                $skip: \"rest.skip\"\n                $orderby: \"rest.orderby\"\n                $count: \"rest.count\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/analytical-data\n          name: analytical-data\n          description: \"\
  Query analytical workspace data for planning and analysis\"\n          operations:\n            - method: GET\n              name: query-analytical-data\n              description: \"Retrieve analytical workspace records\"\n              call: \"tagetik-odata.query-analytical-data\"\n              with:\n                database: \"rest.database\"\n                workspace: \"rest.workspace\"\n                $filter: \"rest.filter\"\n                $top: \"rest.top\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/metadata\n          name: odata-metadata\n          description: \"OData service metadata for entity discovery\"\n          operations:\n            - method: GET\n              name: get-odata-metadata\n              description: \"Retrieve available entity sets and their properties\"\n              call: \"tagetik-odata.get-odata-metadata\"\n              with:\n                database: \"rest.database\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: tagetik-reporting-mcp\n      transport: http\n      description: \"MCP server for AI-assisted financial reporting and close analysis.\"\n      tools:\n        - name: query-financial-data\n          description: \"Query CCH Tagetik financial consolidation data with filters for year, period, scenario (Actual/Budget/Forecast), entity, and account\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tagetik-odata.query-financial-data\"\n          with:\n            database: \"tools.database\"\n            $filter: \"tools.filter\"\n            $select: \"tools.select\"\n            $top: \"tools.top\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: query-analytical-data\n          description: \"Query CCH Tagetik analytical workspace\
  \ data for budget, forecast, and planning scenarios\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tagetik-odata.query-analytical-data\"\n          with:\n            database: \"tools.database\"\n            workspace: \"tools.workspace\"\n            $filter: \"tools.filter\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-odata-metadata\n          description: \"Discover available CCH Tagetik entity sets, dimensions, and data models in a given database\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tagetik-odata.get-odata-metadata\"\n          with:\n            database: \"tools.database\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
