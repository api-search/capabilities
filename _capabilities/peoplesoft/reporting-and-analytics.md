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
- peoplesoft
- search index operations
- execute a peoplesoft query by name and retrieve results.
- list analytics reports
- search
- retrieve available peoplesoft query definitions.
- query execution
- campus solutions
- pivot grid definitions
- erp
- execute query
- hcm
- list pivot grids
- supply chain management
- analytics
- retrieve data for a specific pivot grid.
- search content
- forecast data and projections
- peoplesoft query definitions
- retrieve data for a specific pivot grid with optional filters.
- retrieve budget definitions and data.
- retrieve available pivot grid definitions.
- retrieve forecast data and projections.
- execute a full-text search across peoplesoft indexed content.
- list forecasts
- list budgets
- retrieve performance analytics reports.
- financial and supply chain management.
- campus solutions.
- crm
- execute a peoplesoft query by name.
- pivot grid data
- performance analytics reports
- budget definitions and data
- enterprise software
- list queries
- financial management
- trigger a search index build or incremental update.
- human capital management.
- dashboards
- full-text search results
- trigger index build
- get pivot grid data
- peopletools platform services.
- reporting
- query
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
