---
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
- peoplesoft query definitions
- campus solutions
- financial management
- retrieve forecast data and projections.
- list queries
- erp
- execute a peoplesoft query by name.
- retrieve data for a specific pivot grid.
- list forecasts
- search
- enterprise software
- query execution
- pivot grid data
- hcm
- full-text search results
- reporting
- retrieve performance analytics reports.
- campus solutions.
- trigger a search index build or incremental update.
- budget definitions and data
- search index operations
- search content
- list pivot grids
- query
- retrieve available pivot grid definitions.
- execute a full-text search across peoplesoft indexed content.
- pivot grid definitions
- retrieve available peoplesoft query definitions.
- forecast data and projections
- trigger index build
- retrieve data for a specific pivot grid with optional filters.
- execute a peoplesoft query by name and retrieve results.
- crm
- retrieve budget definitions and data.
- list analytics reports
- peopletools platform services.
- human capital management.
- supply chain management
- analytics
- get pivot grid data
- peoplesoft
- financial and supply chain management.
- dashboards
- performance analytics reports
- execute query
- list budgets
slug: reporting-and-analytics
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
