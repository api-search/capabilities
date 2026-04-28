---
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
- peoplesoft
- forecast data and projections
- peopletools platform services.
- reporting
- retrieve available pivot grid definitions.
- retrieve performance analytics reports.
- list queries
- trigger a search index build or incremental update.
- list pivot grids
- list forecasts
- search
- budget definitions and data
- retrieve available peoplesoft query definitions.
- pivot grid definitions
- campus solutions
- search index operations
- query
- full-text search results
- performance analytics reports
- campus solutions.
- trigger index build
- human capital management.
- retrieve data for a specific pivot grid with optional filters.
- peoplesoft query definitions
- retrieve budget definitions and data.
- get pivot grid data
- enterprise software
- financial management
- search content
- execute a peoplesoft query by name and retrieve results.
- supply chain management
- pivot grid data
- execute query
- execute a peoplesoft query by name.
- analytics
- list analytics reports
- crm
- list budgets
- erp
- hcm
- financial and supply chain management.
- dashboards
- query execution
- retrieve forecast data and projections.
- execute a full-text search across peoplesoft indexed content.
- retrieve data for a specific pivot grid.
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
