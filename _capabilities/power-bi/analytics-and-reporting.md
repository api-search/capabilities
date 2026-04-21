---
consumed_apis:
- power-bi
description: Unified workflow for Power BI analytics operations including dataset management, report creation and distribution, dashboard monitoring, workspace administration, and gateway configuration. Used by BI analysts, report developers, and Power BI administrators.
layout: capability
name: Power BI Analytics and Reporting
operations:
- description: List all datasets
  method: GET
  name: list-datasets
  path: /v1/datasets
- description: Create a dataset
  method: POST
  name: create-dataset
  path: /v1/datasets
- description: Get dataset details
  method: GET
  name: get-dataset
  path: /v1/datasets/{datasetId}
- description: Delete a dataset
  method: DELETE
  name: delete-dataset
  path: /v1/datasets/{datasetId}
- description: List all reports
  method: GET
  name: list-reports
  path: /v1/reports
- description: List all dashboards
  method: GET
  name: list-dashboards
  path: /v1/dashboards
- description: Create a dashboard
  method: POST
  name: create-dashboard
  path: /v1/dashboards
- description: List workspaces
  method: GET
  name: list-workspaces
  path: /v1/workspaces
- description: List gateways
  method: GET
  name: list-gateways
  path: /v1/gateways
personas: []
provider_name: Power BI
provider_slug: power-bi
search_terms:
- list all power bi datasets
- get datasources for a dataset
- gateway management
- get workspace users
- create dataset
- export report
- delete dataset
- clone a report
- get dashboard details
- list dashboards
- list all reports
- get refresh history
- list workspaces
- get dataset refresh history
- refresh dataset
- delete a dataset
- get gateway
- get dataset details
- get dashboard tiles
- get pages for a report
- export a report
- list all power bi reports
- create workspace
- create a new dashboard
- get dataset details by id
- workspace management
- clone report
- dataset management
- visualization
- list data gateways
- create dashboard
- list all dashboards
- get gateway details
- get tiles for a dashboard
- reporting
- get dataset
- list reports
- dashboard management
- create a dashboard
- power bi
- get report details by id
- get report pages
- trigger a dataset refresh
- create a new dataset
- get gateway datasources
- get report
- create a dataset
- business intelligence
- list gateways
- get datasources
- get dashboard
- create a new workspace
- list all workspaces
- list all datasets
- individual dataset operations
- list workspace users
- analytics
- list datasets
- dashboards
- report management
- data analysis
slug: analytics-and-reporting
tags:
- Power BI
- Analytics
- Business Intelligence
- Reporting
tools:
- description: List all Power BI datasets
  hints:
    openWorld: true
    readOnly: true
  name: list-datasets
- description: Get dataset details by ID
  hints:
    readOnly: true
  name: get-dataset
- description: Create a new dataset
  hints:
    readOnly: false
  name: create-dataset
- description: Delete a dataset
  hints:
    destructive: true
    idempotent: true
  name: delete-dataset
- description: Trigger a dataset refresh
  hints:
    readOnly: false
  name: refresh-dataset
- description: Get dataset refresh history
  hints:
    readOnly: true
  name: get-refresh-history
- description: Get datasources for a dataset
  hints:
    readOnly: true
  name: get-datasources
- description: List all Power BI reports
  hints:
    openWorld: true
    readOnly: true
  name: list-reports
- description: Get report details by ID
  hints:
    readOnly: true
  name: get-report
- description: Clone a report
  hints:
    readOnly: false
  name: clone-report
- description: Export a report
  hints:
    readOnly: true
  name: export-report
- description: Get pages for a report
  hints:
    readOnly: true
  name: get-report-pages
- description: List all dashboards
  hints:
    openWorld: true
    readOnly: true
  name: list-dashboards
- description: Get dashboard details
  hints:
    readOnly: true
  name: get-dashboard
- description: Create a new dashboard
  hints:
    readOnly: false
  name: create-dashboard
- description: Get tiles for a dashboard
  hints:
    readOnly: true
  name: get-dashboard-tiles
- description: List all workspaces
  hints:
    openWorld: true
    readOnly: true
  name: list-workspaces
- description: Create a new workspace
  hints:
    readOnly: false
  name: create-workspace
- description: List workspace users
  hints:
    readOnly: true
  name: get-workspace-users
- description: List data gateways
  hints:
    readOnly: true
  name: list-gateways
- description: Get gateway details
  hints:
    readOnly: true
  name: get-gateway
- description: Get gateway datasources
  hints:
    readOnly: true
  name: get-gateway-datasources
---
