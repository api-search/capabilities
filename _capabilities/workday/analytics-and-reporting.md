---
consumed_apis:
- workday-prism
- workday-wql
- workday-raas
description: Unified analytics and reporting combining Prism Analytics, WQL, and Report-as-a-Service APIs for business analysts to query data, manage datasets, and access custom reports.
layout: capability
name: Workday Analytics and Reporting
operations:
- description: List datasets
  method: GET
  name: list-datasets
  path: /v1/datasets
- description: Execute a WQL query
  method: POST
  name: execute-query
  path: /v1/wql-query
personas: []
provider_name: Workday
provider_slug: workday
search_terms:
- prism create data change task
- wql list data sources
- get fields for a wql data source
- analytics
- create a data change task
- retrieve a custom workday report
- prism analytics datasets
- execute a wql query against workday data
- prism delete dataset
- wql query endpoint
- saas
- prism list data change tasks
- reporting
- workday
- prism create dataset
- financial management
- wql get data source
- enterprise software
- list data change tasks
- prism get dataset
- list datasets
- list all prism analytics datasets
- wql execute query
- business intelligence
- execute a wql query
- wql get data source fields
- create a new prism analytics dataset
- list available wql data sources
- raas get report
- delete a dataset
- prism list datasets
- execute query
- list all prism tables
- prism list tables
- get a wql data source by id
- get a dataset by id
- hcm
- cloud computing
slug: analytics-and-reporting
tags:
- Workday
- Analytics
- Reporting
- Business Intelligence
tools:
- description: List all Prism Analytics datasets
  hints:
    readOnly: true
  name: prism-list-datasets
- description: Create a new Prism Analytics dataset
  hints:
    readOnly: false
  name: prism-create-dataset
- description: Get a dataset by ID
  hints:
    readOnly: true
  name: prism-get-dataset
- description: Delete a dataset
  hints:
    destructive: true
    readOnly: false
  name: prism-delete-dataset
- description: List data change tasks
  hints:
    readOnly: true
  name: prism-list-data-change-tasks
- description: Create a data change task
  hints:
    readOnly: false
  name: prism-create-data-change-task
- description: List all Prism tables
  hints:
    readOnly: true
  name: prism-list-tables
- description: Execute a WQL query against Workday data
  hints:
    readOnly: true
  name: wql-execute-query
- description: List available WQL data sources
  hints:
    readOnly: true
  name: wql-list-data-sources
- description: Get a WQL data source by ID
  hints:
    readOnly: true
  name: wql-get-data-source
- description: Get fields for a WQL data source
  hints:
    readOnly: true
  name: wql-get-data-source-fields
- description: Retrieve a custom Workday report
  hints:
    readOnly: true
  name: raas-get-report
---
