---
api_specs:
- filename: query.yml
  format: yaml
  label: query
  slug: query
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/openapi/query.yml
- filename: pivot-grid.yml
  format: yaml
  label: pivot-grid
  slug: pivot-grid
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/openapi/pivot-grid.yml
- filename: search-framework.yml
  format: yaml
  label: search-framework
  slug: search-framework
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/openapi/search-framework.yml
- filename: enterprise-performance-management.yml
  format: yaml
  label: epm
  slug: epm
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/openapi/enterprise-performance-management.yml
categories:
- analytics
consumed_apis:
- query
- pivot-grid
- search-framework
- epm
description: Unified workflow for analysts combining query execution, pivot grid dashboards, full-text search, and performance analytics across PeopleSoft Query, Pivot Grid, Search Framework, and EPM APIs.
layout: capability
name: PeopleSoft Reporting And Analytics
operations:
- description: Retrieve available PeopleSoft Query definitions.
  method: GET
  name: list-queries
  path: /v1/queries
- description: Execute a PeopleSoft Query by name.
  method: GET
  name: execute-query
  path: /v1/queries/{queryName}
- description: Retrieve available pivot grid definitions.
  method: GET
  name: list-pivot-grids
  path: /v1/pivot-grids
- description: Retrieve data for a specific pivot grid.
  method: GET
  name: get-pivot-grid-data
  path: /v1/pivot-grids/{gridId}/data
- description: Execute a full-text search across PeopleSoft indexed content.
  method: GET
  name: search-content
  path: /v1/search-results
- description: Trigger a search index build or incremental update.
  method: POST
  name: trigger-index-build
  path: /v1/search-indexes
- description: Retrieve budget definitions and data.
  method: GET
  name: list-budgets
  path: /v1/budgets
- description: Retrieve forecast data and projections.
  method: GET
  name: list-forecasts
  path: /v1/forecasts
- description: Retrieve performance analytics reports.
  method: GET
  name: list-analytics-reports
  path: /v1/analytics-reports
personas: []
provider_name: PeopleSoft
provider_slug: peoplesoft
search_terms:
- crm
- pivot grid data
- retrieve data for a specific pivot grid.
- execute a full-text search across peoplesoft indexed content.
- supply chain management
- retrieve available peoplesoft query definitions.
- retrieve budget definitions and data.
- hcm
- search content
- forecast data and projections
- get pivot grid data
- list queries
- trigger index build
- full-text search results
- trigger a search index build or incremental update.
- pivot grid definitions
- search
- budget definitions and data
- analytics
- query execution
- performance analytics reports
- campus solutions
- peoplesoft
- list analytics reports
- peopletools platform services.
- list budgets
- reporting
- retrieve performance analytics reports.
- retrieve data for a specific pivot grid with optional filters.
- search index operations
- retrieve forecast data and projections.
- retrieve available pivot grid definitions.
- list forecasts
- execute a peoplesoft query by name and retrieve results.
- campus solutions.
- peoplesoft query definitions
- dashboards
- enterprise software
- list pivot grids
- query
- human capital management.
- financial management
- financial and supply chain management.
- execute a peoplesoft query by name.
- execute query
- erp
slug: reporting-and-analytics
source_filename: reporting-and-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"PeopleSoft Reporting And Analytics\"\n  description: \"Unified workflow for analysts combining query execution, pivot grid dashboards, full-text search, and performance analytics across PeopleSoft Query, Pivot Grid, Search Framework, and EPM APIs.\"\n  tags:\n    - PeopleSoft\n    - Reporting\n    - Analytics\n    - Dashboards\n    - Query\n    - Search\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      PEOPLESOFT_USERNAME: PEOPLESOFT_USERNAME\n      PEOPLESOFT_PASSWORD: PEOPLESOFT_PASSWORD\n\ncapability:\n  consumes:\n    - import: query\n      location: ./shared/query.yaml\n    - import: pivot-grid\n      location: ./shared/pivot-grid.yaml\n    - import: search-framework\n      location: ./shared/search-framework.yaml\n    - import: epm\n      location: ./shared/enterprise-performance-management.yaml\n\n  exposes:\n    - type: rest\n      port: 8086\n      namespace: reporting-api\n\
  \      description: \"Unified REST API for PeopleSoft reporting and analytics workflows.\"\n      resources:\n        - path: /v1/queries\n          name: queries\n          description: \"PeopleSoft Query definitions\"\n          operations:\n            - method: GET\n              name: list-queries\n              description: \"Retrieve available PeopleSoft Query definitions.\"\n              call: \"query.list-queries\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/queries/{queryName}\n          name: query-execution\n          description: \"Query execution\"\n          operations:\n            - method: GET\n              name: execute-query\n              description: \"Execute a PeopleSoft Query by name.\"\n              call: \"query.execute-query\"\n              with:\n                queryName: \"rest.queryName\"\n                isConnectedQuery: \"rest.isConnectedQuery\"\n                maxRows:\
  \ \"rest.maxRows\"\n                offset: \"rest.offset\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pivot-grids\n          name: pivot-grids\n          description: \"Pivot grid definitions\"\n          operations:\n            - method: GET\n              name: list-pivot-grids\n              description: \"Retrieve available pivot grid definitions.\"\n              call: \"pivot-grid.list-pivot-grids\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pivot-grids/{gridId}/data\n          name: pivot-grid-data\n          description: \"Pivot grid data\"\n          operations:\n            - method: GET\n              name: get-pivot-grid-data\n              description: \"Retrieve data for a specific pivot grid.\"\n              call: \"pivot-grid.get-pivot-grid-data\"\n              with:\n                gridId: \"rest.gridId\"\n   \
  \             filters: \"rest.filters\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/search-results\n          name: search-results\n          description: \"Full-text search results\"\n          operations:\n            - method: GET\n              name: search-content\n              description: \"Execute a full-text search across PeopleSoft indexed content.\"\n              call: \"search-framework.search-content\"\n              with:\n                q: \"rest.q\"\n                category: \"rest.category\"\n                maxResults: \"rest.maxResults\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/search-indexes\n          name: search-indexes\n          description: \"Search index operations\"\n          operations:\n            - method: POST\n              name: trigger-index-build\n              description: \"Trigger a search\
  \ index build or incremental update.\"\n              call: \"search-framework.trigger-index-build\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/budgets\n          name: budgets\n          description: \"Budget definitions and data\"\n          operations:\n            - method: GET\n              name: list-budgets\n              description: \"Retrieve budget definitions and data.\"\n              call: \"epm.list-budgets\"\n              with:\n                fiscalYear: \"rest.fiscalYear\"\n                businessUnit: \"rest.businessUnit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/forecasts\n          name: forecasts\n          description: \"Forecast data and projections\"\n          operations:\n            - method: GET\n              name: list-forecasts\n              description: \"Retrieve forecast data and projections.\"\
  \n              call: \"epm.list-forecasts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/analytics-reports\n          name: analytics-reports\n          description: \"Performance analytics reports\"\n          operations:\n            - method: GET\n              name: list-analytics-reports\n              description: \"Retrieve performance analytics reports.\"\n              call: \"epm.list-analytics-reports\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9096\n      namespace: reporting-mcp\n      transport: http\n      description: \"MCP server for AI-assisted PeopleSoft reporting and analytics workflows.\"\n      tools:\n        - name: list-queries\n          description: \"Retrieve available PeopleSoft Query definitions.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"\
  query.list-queries\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: execute-query\n          description: \"Execute a PeopleSoft Query by name and retrieve results.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"query.execute-query\"\n          with:\n            queryName: \"tools.queryName\"\n            isConnectedQuery: \"tools.isConnectedQuery\"\n            maxRows: \"tools.maxRows\"\n            offset: \"tools.offset\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-pivot-grids\n          description: \"Retrieve available pivot grid definitions.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"pivot-grid.list-pivot-grids\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-pivot-grid-data\n          description:\
  \ \"Retrieve data for a specific pivot grid with optional filters.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"pivot-grid.get-pivot-grid-data\"\n          with:\n            gridId: \"tools.gridId\"\n            filters: \"tools.filters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-content\n          description: \"Execute a full-text search across PeopleSoft indexed content.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"search-framework.search-content\"\n          with:\n            q: \"tools.q\"\n            category: \"tools.category\"\n            maxResults: \"tools.maxResults\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: trigger-index-build\n          description: \"Trigger a search index build or incremental update.\"\n          hints:\n            readOnly:\
  \ false\n            destructive: false\n            idempotent: false\n          call: \"search-framework.trigger-index-build\"\n          with:\n            indexName: \"tools.indexName\"\n            buildType: \"tools.buildType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-budgets\n          description: \"Retrieve budget definitions and data.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"epm.list-budgets\"\n          with:\n            fiscalYear: \"tools.fiscalYear\"\n            businessUnit: \"tools.businessUnit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-forecasts\n          description: \"Retrieve forecast data and projections.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"epm.list-forecasts\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: list-analytics-reports\n          description: \"Retrieve performance analytics reports.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"epm.list-analytics-reports\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/capabilities/reporting-and-analytics.yaml
tags:
- PeopleSoft
- Reporting
- Analytics
- Dashboards
- Query
- Search
tools:
- description: Retrieve available PeopleSoft Query definitions.
  hints:
    openWorld: true
    readOnly: true
  name: list-queries
- description: Execute a PeopleSoft Query by name and retrieve results.
  hints:
    openWorld: true
    readOnly: true
  name: execute-query
- description: Retrieve available pivot grid definitions.
  hints:
    openWorld: true
    readOnly: true
  name: list-pivot-grids
- description: Retrieve data for a specific pivot grid with optional filters.
  hints:
    openWorld: true
    readOnly: true
  name: get-pivot-grid-data
- description: Execute a full-text search across PeopleSoft indexed content.
  hints:
    openWorld: true
    readOnly: true
  name: search-content
- description: Trigger a search index build or incremental update.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: trigger-index-build
- description: Retrieve budget definitions and data.
  hints:
    openWorld: true
    readOnly: true
  name: list-budgets
- description: Retrieve forecast data and projections.
  hints:
    openWorld: true
    readOnly: true
  name: list-forecasts
- description: Retrieve performance analytics reports.
  hints:
    openWorld: true
    readOnly: true
  name: list-analytics-reports
---
